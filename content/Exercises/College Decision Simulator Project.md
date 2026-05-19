## Project Overview
The project creates a Java program that simulates a real decision process for a college. It employs object-oriented design and its own algorithms to analyze several university choices and give a meaningful suggestion. To make it easy for the user to work with , the program is menu driven . It also has the necessary search, filter and ranking features to explore the data.

## Class Design and Inheritance
The project uses three custom classes with an obvious inheritance relationship. The base class `Institution` has the basic college name and setting. The `College` subclass extends `Institution` and adds four specific properties: tuition, population, GPA, and ivy. The main driver class holds an `ArrayList` of these college objects.

## Scoring Algorithms
The program has two different scoring modes to evaluate the college options. The first mode, the 'Frugal Scholar' route, is incentivized for low tuition and accessible GPAs. Mode 2 is the “Big Campus” route that awards large student populations and urban locations. The mathematical formula used for Mode 1:

$$Score=\left(\frac{60000-tuition}{100}\right)+(averageGpa\times10)$$

This formula ensures that cheaper schools and matching GPAs result in a higher overall score for the user.

## Code Implementation: Institution Class
This is the superclass that defines the most basic properties of any school. It uses standard constructors and getter methods to access the data.

```java
public class Institution {
    // Basic shared variables
    private String name;
    private String setting;

    public Institution(String name, String setting) {
        this.name = name;
        this.setting = setting;
    }

    public String getName() {
        return name;
    }

    public String getSetting() {
        return setting;
    }

    public String toString() {
        return "Name: " + name + " | Setting: " + setting;
    }
}
```

## Code Implementation: College Class
This subclass extends the base class and adds the required traits for the simulation. It includes the actual scoring logic based on conditionals and boolean logic.

```java
public class College extends Institution {
    // 4 required traits per option
    private double tuition;
    private int population;
    private double averageGpa;
    private boolean publicIvy;

    public College(String name, String setting, double tuition, int population, double averageGpa, boolean publicIvy) {
        super(name, setting); // Inheritance call
        this.tuition = tuition;
        this.population = population;
        this.averageGpa = averageGpa;
        this.publicIvy = publicIvy;
    }

    // Calculates score based on the chosen mode
    public double calculateScore(int mode) {
        if (mode == 1) {
            // Frugal Scholar Mode
            return ((60000.0 - tuition) / 100.0) + (averageGpa * 10.0);
        } else {
            // Big Campus Mode
            double score = (population / 1000.0);
            if (getSetting().equals("Urban")) {
                score += 30.0;
            }
            if (publicIvy) {
                score += 20.0;
            }
            return score;
        }
    }

    public String toString() {
        return super.toString() + " | Tuition: $" + tuition + " | Pop: " + population;
    }
}
```

## Code Implementation: Main Class
This class contains the main method and the interactive menu. It loads exactly eight options with four traits each into an `ArrayList`. It uses loops and conditionals to process user searches and filters. It also runs a sorting algorithm to rank the final recommendation.

```java
import java.util.ArrayList;
import java.util.Scanner;

public class SimulatorMain {
    public static void main(String[] args) {
        ArrayList<College> colleges = new ArrayList<>();
        Scanner scan = new Scanner(System.in);

        // At least 8 options added to the ArrayList
        colleges.add(new College("State U", "Urban", 25000, 30000, 3.5, true));
        colleges.add(new College("Tech Inst", "Suburban", 50000, 10000, 3.9, false));
        colleges.add(new College("Farm College", "Rural", 15000, 5000, 3.2, false));
        colleges.add(new College("City College", "Urban", 10000, 20000, 3.0, false));
        colleges.add(new College("Elite U", "Urban", 60000, 8000, 4.0, true));
        colleges.add(new College("Woods U", "Rural", 35000, 4000, 3.6, false));
        colleges.add(new College("Lake Inst", "Suburban", 40000, 15000, 3.7, false));
        colleges.add(new College("Ocean U", "Urban", 45000, 25000, 3.8, true));

        boolean running = true;
        while (running) {
            System.out.println("\n1. View All | 2. Filter Urban | 3. Run Simulator | 4. Exit");
            int choice = scan.nextInt();

            if (choice == 1) {
                for (College c : colleges) System.out.println(c.toString());
            } else if (choice == 2) {
                for (College c : colleges) {
                    if (c.getSetting().equals("Urban")) System.out.println(c.toString());
                }
            } else if (choice == 3) {
                System.out.println("Mode 1 (Frugal) or Mode 2 (Big Campus)? Enter 1 or 2:");
                int mode = scan.nextInt();

                // Simple Selection Sort Algorithm
                for (int i = 0; i < colleges.size() - 1; i++) {
                    int maxIdx = i;
                    for (int j = i + 1; j < colleges.size(); j++) {
                        if (colleges.get(j).calculateScore(mode) > colleges.get(maxIdx).calculateScore(mode)) {
                            maxIdx = j;
                        }
                    }
                    College temp = colleges.get(i);
                    colleges.set(i, colleges.get(maxIdx));
                    colleges.set(maxIdx, temp);
                }

                // Final Recommendation Output
                System.out.println("Top Choice: " + colleges.get(0).getName());
                System.out.println("Because it scored highest in your chosen category!");
            } else if (choice == 4) {
                running = false;
            }
        }
    }
}
```

## Testing Table

| **Test Action** | **Input Data**   | **Expected Result**                                | **Pass/Fail** |
| --------------- | ---------------- | -------------------------------------------------- | ------------- |
| View All        | Option 1         | Prints all 8 colleges to the screen.               | Pass          |
| Filter Data     | Option 2         | Prints only the 4 colleges marked as "Urban".      | Pass          |
| Frugal Mode     | Option 3, Mode 1 | Sorts list and recommends City College (cheapest). | Pass          |
| Campus Mode     | Option 3, Mode 2 | Sorts list and recommends State U (largest urban). | Pass          |

## Project Reflection
During the development of this project I have gained experience how to use object-oriented programming to organize real-world data effectively. The code I wrote maintains great readability and organization thanks to inheritance. By writing custom sorting algorithms I was also able to reinforce core AP Computer Science concepts. Also in general, the development timeline was very easy to follow as I split the project into manageable blocks.