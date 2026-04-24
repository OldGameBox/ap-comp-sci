### Part A
##### Wheels and Axles
```java
public int getPossibleAssemblies() {
	int totalNumWheels = 0;
	int totalNumAxles = 0;
    
    for (Shelf shelf: shelfArray) {
    	totalNumWheels += shelf.getNumWheels();
        totalNumAxles += shelf.getNumAxles();
    }
    
    return Math.min(totalNumAxles, totalNumWheels / 2);
}
```
##### Surfaces and Paint
```java
public boolean hasEnoughPaint(int numGallons) {
	double totalArea = 0;
    
    for (Surface surface: surfaceArray) {
    	totalArea += surface.getWidth() * surface.getLength()
    }
    
    return ((double) numGallons) * 400.0 >= totalArea;
}
```
### Part B
##### Average Teen Age
```java
public double avgTeenAccounts() {
	double totalAge = 0;
    double totalNumTeens = 0;
    
    for (GameAccount player: allPlayers) {
    	if (player.getAge() >= 13 && player.getAge() <= 19) {
        	totalAge += player.getAge();
            totalNumTeens++;
        }
    }
    
    return totalAge / totalNumTeens;
}
```
##### Game Streak
```java
public int getLongestHomeWinStreak() {
	int longestStreak = 0;
    int currentStreak = 0;
    for (Game game: allGames) {
    	if (game.getHomeScore() > game.getAwayScore()) {
        	currentStreak++;
        } else {
        	currentStreak = 0;
        }
        
        if (longestStreak < currentStreak) {
        	longestStreak = currentStreak;
        }
    }
    
    return longestStreak;
}

```