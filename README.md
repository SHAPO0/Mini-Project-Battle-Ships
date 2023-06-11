# BattleShipGame.java - Battle Ships Game Java Program Coding Project Assignment 

Visit java source code link to download: 
- <a href="https://github.com/Joshua-Ho-Gwok-Hin/Mini-Project-Battle-Ships/blob/main/BattleShipGame.java">BattleShipGame.java</a>
- <a href="https://github.com/Joshua-Ho-Gwok-Hin/Mini-Project-Battle-Ships/blob/main/BattleShipGame.java">Battle Ship Game Java</a>



This project will help you get more familiar with arrays. You will be recreating the game of battleships. A player will place 5 of their ships on a 10 by 10 grid. The computer player will deploy five ships on the same grid. Once the game starts the player and computer take turns, trying to sink each other's ships by guessing the coordinates to "attack". The game ends when either the player or computer has no ships left.

- Step 1 - Create the ocean map (Line 7 to 20 & Line 45 to 75)
- Step 2 - Deploy player's ships (Line 77 to 104)
- Step 3 - Deploy computer's ships (Line 106 to 119)
- Step 4 - Battle (Line 29 to 35 & Line 121 to 190)
- Step 5 - Game Over (Line 37 to 42)

IMPORTANT NOTICE! THIS CODE USES JAVA SWITCH EXPRESSIONS. SWITCH EXPRESSIONS IS A NEW FEATURE COMPATIBLE WITH JDK 13 AND ABOVE. (RECOMMEND LTS JDK 17 or 21.) IF YOU ARE USING JDK 12 AND BELOW, YOU'LL NEED TO CONVERT THE SWITCH EXPRESSIONS TO SWITCH STATEMENTS. COMPARE THESE EXAMPLES:

```
// This is a switch expression on line 50 to 53 (JDK 13 and above)

switch (location) {
    case PLAYER_SHIP -> System.out.print('@' + " ");
    case EMPTY, COMPUTER_MISSED -> System.out.print(' ' + " "); // add COMPUTER_SHIP after testing
    default -> System.out.print(location + " "); // PLAYER_MISSED, PLAYER_SUNKEN, COMPUTER_SUNKEN
}


// This switch statement can replace the switch expression on line 50 to 53.

 switch (location) {
      case PLAYER_SHIP: {
          System.out.print('@' + " ");
          break;    // This break here is required.
      }
      case EMPTY, COMPUTER_MISSED:  { 
          System.out.print(' ' + " "); 
          break;    // This break here is required.
      }
      default: { 
          System.out.print(location + " "); 
          break:    // This break here is optional, not required in default.
      }
  }
```

Step 1 - CREATE THE OCEAN MAP (Line 7 to 20 & Line 45 to 75)

Line 7 to 13
Giving meaningful names to variables. Variables declared final and be given a value (initialised) because it is a requirement when a variable name is used in Switch statements & expressions. 

Line 11 can be '\u0000' or '\000'. Why? Because in line 17, a new char[][] (2D char array) was created. The default value for char is '\u0000' or '\000'. EMPTY is a meaningful name (subjectively) for the unassigned. So we can refer any unassigned char (in the 2D array) with the name EMPTY.

Line 62 to 75 are hardcoded. 
Line 45 to 60 uses a combination of a for-loop, for-each loop and switch expressions to print out each char. I've added +  " " for aesthetic purposes. " " is a string with a space. The for-loop is neccessary because of the index used for the left and right sides. The inner loop and also be rewriten with another for-loop (int j = 0; j < oceanMap[i] ;  j++). If using 2 for-loops, the switch becomes switch ( oceanMap[i][j]).



Step 2 - DEPLOY PLAYER'S SHIPS (Line 77 to 104)

Line 77 to 92 is to check the player's input to prevent wrong data type entered. Without this method, the program will stop when a non number is entered. 
Line 78 uses a technique similar to a boolean flag. It wil exit the while-loop (continue out of the loop)only if a proper number is entered. 
Line 82 (input.nextLine();) is important. Line 81 is asking if input is not a number (means its a string), put an "Enter" so that the program can continue. Line 83 means the input is a number and then assigning variable i with the number entered on line 84. Line 85 to 87 basically modify i to become -1 if the number is wrong and then the user have to key in another number again.
Line 94 to 104 assign local variables x and y as indexes/indices. The JVM then uses the numbers to change the value of oceanMap[x][y] to char '1' (PLAYER_SHIP = '1') if it is not already assigned. Line 95 let this repeat untill 5 ships are deployed.


Step 3 - DEPLOY COMPUTER'S SHIPS (Line 106 to 119)

Line 108, similar to previous while-loop, computer keeps generating random numbers until properly assigned 5 ships. The result of computer selected are displayed for testing purposes. To remove the char number '2' for the program simply change line 52.
Line 110 & 111 has a .nextInt(origin, bound) method. This nextInt() and the previous one on line 84 are different methods but has same return types. In Java you'll see many methods having similar names and method signatures. It'll be very helpful to remember which is which and the data types so as to understand the behaviour.


Step 4 - BATTLE (Line 29 to 35 & Line 121 to 190)

Line 29 to 35 basically is a while-loop that continues until either playerDeployed or computerDeployed is 0. Line 29 is written in negatives of "either playerDeployed or computerDeployed is 0". The complete opposite is (playerDeployed == 0 || computerDeployed == 0). Line 32 prevents the computer from attacking, possibly changing the output by putting a stop once the player successfully caused computerDeployed to 0. 
Line 121 to 136 attack(char) is like a "helper method" similar to the assign(char) method on line 77. Infact, both are the same method except for the println() message on line 80 and 124. Purpose is to validate the player's input.
Line 138 to 158 changes the value of individual characters in oceanMap 2D char array. Either playerDeployed or computerDeployed gotten -1 or it's a missed. For player's case, a '-' is printed (Line 53).
Line 160 to 189 is almost identical to the playerAttack() except that instead of using the attack(char) as validation, It is using a Random to generate defined numbers (0, 1, 2, 3, 4, 5, 6, 7, 8 & 9). 


Step 5 - GAME OVER (Line 37 to 42)

Finally, once the program exit the while-loop at line 29, the Game Over message is printed along with the announcement of the winner.

P.S: I've not created any variable name or method signature as Battle() or GameOver(). You can try create your method to make it look neater.

<a href="https://github.com/Joshua-Ho-Gwok-Hin/Mini-Project-Battle-Ships/tree/main">Battle Ships Game Java Program - Coding Project Assignment</a>
