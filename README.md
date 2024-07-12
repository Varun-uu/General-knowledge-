# General-knowledge-
import java.util.ArrayList;
import java.util.Collections;
import java.util.HashMap;
import java.util.List;
import java.util.Map;
import java.util.Scanner;

public class KnowledgeGame {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Create a map to store questions and answers
        Map<String, String> questionsAndAnswers = new HashMap<>();
        questionsAndAnswers.put("What is the capital of France?", "Paris");
        questionsAndAnswers.put("What is the highest mountain in the world?", "Mount Everest");
        questionsAndAnswers.put("Who painted the Mona Lisa?", "Leonardo da Vinci");
        questionsAndAnswers.put("What is the smallest country in the world?", "Vatican City");
        questionsAndAnswers.put("What is the largest ocean on Earth?", "Pacific Ocean");

        // Create a list to store the questions in random order
        List<String> questions = new ArrayList<>(questionsAndAnswers.keySet());
        Collections.shuffle(questions);

        int score = 0;
        for (String question : questions) {
            System.out.println(question);
            System.out.print("Your answer: ");
            String userAnswer = scanner.nextLine();

            if (userAnswer.equalsIgnoreCase(questionsAndAnswers.get(question))) {
                System.out.println("Correct!");
                score++;
            } else {
                System.out.println("Incorrect. The correct answer is: " + questionsAndAnswers.get(question));
            }
            System.out.println();
        }

        System.out.println("Your final score is: " + score + " out of " + questions.size());
    }
}
