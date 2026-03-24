import java.util.Random;
import java.util.Scanner;

public class GuessingGame {
    public static void main(String[] args) {
        // Define the range (1 to 100)
        int min = 1;
        int max = 100;
        
        // Generate a random number
        Random rand = new Random();
        int computerNumber = rand.nextInt(max - min + 1) + min;
        
        Scanner scanner = new Scanner(System.in);
        int userAnswer = 0;
        int count = 0;

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("I'm thinking of a number between " + min + " and " + max);

        // Game loop
        while (userAnswer != computerNumber) {
            System.out.print("Enter your guess: ");
            userAnswer = scanner.nextInt();
            count++;

            if (userAnswer < min || userAnswer > max) {
                System.out.println("Your guess is invalid or outside the range, try again.");
            } else if (userAnswer == computerNumber) {
                System.out.println("Correct! You guessed it in " + count + " attempts.");
            } else if (userAnswer > computerNumber) {
                System.out.println("Your guess is too high, try again.");
            } else {
                System.out.println("Your guess is too low, try again.");
            }
        }
        scanner.close();
    }
}
