# -RockPaperScissorsByIliya
This is a simple console game. Everyone knows the game "Rock, paper and scissors".


import java.util.Random;
import java.util.Scanner;

public class RockPaperScissors {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        final String ROCK = "Rock";
        final String PAPER = "Paper";
        final String SCISSORS = "Scissors";


        System.out.println("Choose rock, paper or scissors: ");

        String playerMove = scanner.nextLine();


        if (playerMove.equals("r") || playerMove.equals("rock")) {
            playerMove = ROCK;
        }else if (playerMove.equals("p") || playerMove.equals("paper")) {
            playerMove = PAPER;
        }else if (playerMove.equals("s") || playerMove.equals("scissors")) {
            playerMove = SCISSORS;
        }else {
            System.out.println("Invalid Input. Try Again...");
            return;
        }

        Random random = new Random();
        int computerRandomNumber = random.nextInt(4);
        String computerMove = switch (computerRandomNumber) {
            case 0 -> ROCK;
            case 1 -> PAPER;
            case 2 -> SCISSORS;
            default -> "";
        };

        System.out.printf("The computer chose %s.%n", computerMove);

        if ((playerMove.equals(ROCK)) && computerMove.equals(SCISSORS) ||
                (playerMove.equals(PAPER)) && (computerMove.equals(ROCK)) ||
                (playerMove.equals(SCISSORS)) && (computerMove.equals(PAPER))) {
            System.out.println("You win.");
        } else if (playerMove.equals(SCISSORS) && computerMove.equals(ROCK)) {
            System.out.println("You lose.");
        }else {
            System.out.println("This game is a draw");
        }
    }
}
