## Verbal Prototype
This program simulates a student's daily life over five simulated days. Users manage energy and study points to maintain a high GPA while avoiding exhaustion. You choose to study, sleep, or eat through a text-based menu system. Each action changes your stats and triggers unpredictable random events like pop quizzes. The game ends after five days or immediately if your energy hits zero.

You win by maintaining a GPA of 3.0 or higher by the end. Falling below this threshold results in academic probation and a loss. Burning out from zero energy leads to an immediate failing grade. Success requires balancing your health with your study habits throughout the week.
## Pseudocode Prototype
```java
// Initialize variables
String studentName = input "Name"
int energy = 100
int points = 0
int day = 1
double gpa = 0.0

WHILE day <= 5 AND energy > 0
    printMenu()
    int choice = input "Select"
    
    // Update stats
    points = applyChoice(energy, points, choice)
    IF choice == 1 THEN energy -= 25
    ELSE IF choice == 2 THEN energy += 30
    
    // Random event
    IF Math.random() < 0.2 THEN energy -= 10
    
    gpa = calculateGpaEstimate(points, day)
    day++
END WHILE

// Ending conditions
IF energy <= 0 THEN
    PRINT "You collapsed from exhaustion! Game Over."
ELSE IF gpa >= 3.0 THEN
    PRINT "You passed with a " + gpa + "! You win."
ELSE
    PRINT "GPA too low. You failed the semester."
```

---

## Java Program Implementation
```java
import java.util.Scanner;

public class StudentSimulator {
    // Controls game flow and final results
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int energy = 100;
        int points = 0;
        int day = 1;
        double gpa = 0.0;

        System.out.print("Enter student name: ");
        String name = input.nextLine();

        while (day <= 5 && energy > 0) {
            System.out.println("\n--- Day " + day + " ---");
            System.out.println("Energy: " + energy + " | Points: " + points);
            
            printMenu();
            int choice = input.nextInt();

            points = applyChoice(energy, points, choice);
            
            // Adjust energy based on choice
            if (choice == 1) energy -= 25;
            else if (choice == 2) energy += 30;
            else if (choice == 3) energy += 10;

            // Random event logic
            if (Math.random() < 0.3) {
                System.out.println("EVENT: Sudden burnout! -15 energy.");
                energy -= 15;
            }

            gpa = calculateGpaEstimate(points, day);
            day++;
        }

        // Final ending conditions
        System.out.println("\n--- Final Results ---");
        if (energy <= 0) {
            System.out.println("Status: " + name + " collapsed! You lose.");
        } else if (gpa >= 3.0) {
            System.out.printf("Status: Success! Final GPA: %.2f\n", gpa);
        } else {
            System.out.printf("Status: Failed. Final GPA %.2f is too low.\n", gpa);
        }
    }

    // Prints options for the user
    public static void printMenu() {
        System.out.println("1. Study (-25 energy) | 2. Sleep (+30 energy) | 3. Eat (+10 energy)");
        System.out.print("Action: ");
    }

    // Logic to update student points
    public static int applyChoice(int energy, int points, int choice) {
        if (choice == 1) return points + 40;
        if (choice == 2) return points + 2;
        return points;
    }

    // Returns the estimated GPA
    public static double calculateGpaEstimate(int points, int days) {
        double result = (double) points / (days * 10);
        return Math.min(result, 4.0);
    }
}
```
# Running Code
## Winning example
![[Pasted image 20260226095614.png]]
## Losing example
![[Pasted image 20260226095744.png]]