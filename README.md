import java.util.Scanner;
import java.util.Random;

public class RockPaperScissors {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        String[] rps = {"Rock", "Paper", "Scissors"};

        System.out.println("Game of Rock, Paper, Scissors!");
        System.out.println("Enter your move (Rock, Paper, Scissors). To exit the game, type 'exit'.");

        while (true) {
            System.out.print("Your move: ");
            String playerMove = scanner.nextLine();

            if (playerMove.equalsIgnoreCase("exit")) {
                break;
            }

            if (!playerMove.equalsIgnoreCase("Rock") &&
                !playerMove.equalsIgnoreCase("Paper") &&
                !playerMove.equalsIgnoreCase("Scissors")) {
                System.out.println("Invalid input. Please enter Rock, Paper, or Scissors.");
                continue;
            }

            int randomIndex = random.nextInt(rps.length);
            String computerMove = rps[randomIndex];

            System.out.println("Computer move: " + computerMove);

            if (playerMove.equalsIgnoreCase(computerMove)) {
                System.out.println("It's a tie!");
            } else if ((playerMove.equalsIgnoreCase("Rock") && computerMove.equalsIgnoreCase("Scissors")) ||
                       (playerMove.equalsIgnoreCase("Paper") && computerMove.equalsIgnoreCase("Rock")) ||
                       (playerMove.equalsIgnoreCase("Scissors") && computerMove.equalsIgnoreCase("Paper"))) {
                System.out.println("You win!");
            } else {
                System.out.println("You lose!");
            }
        }

        scanner.close();
        System.out.println("Thanks for playing Rock, Paper, Scissors!");
    }
}
