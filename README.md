# Quiz-Game
I have made a quiz game in which given some question and option type Answer 


import java.util.Scanner;

public class QuizeGame {
    private static final String[] questions = {
            "class {\n"+
                    "    final public void show() {\n" +
                    "       System.out.println(\"Base::show() called\");\n" +
                    "    }\n" +
                    "}\n" +
                    "  \n" +
                    "class Derived extends Base {\n" +
                    "    public void show() {\n" +
                    "       System.out.println(\"Derived::show() called\");\n" +
                    "    }\n" +
                    "}\n" +
                    "  \n" +
                    "class Main {\n" +
                    "    public static void main(String[] args) {\n" +
                    "        Base b = new Derived();;\n" +
                    "        b.show();\n" +
                    "    }\n" +
                    "}?",
            "  Which the following is the process of inserting an element in the stack ?",
            "  Quick sort algorithm is an example of ?",
            "  Which of the following data structures finds its use in recursion?",
            "  Which of the following uses FIFO methods?",
            "  Stack is used for?",
            "  Maximum degree of any vertex in a simple graph of vertices n is ?"
    };

    private static final String[][] options = {
            {"A. Base::show() called ", "B.  Derived :: show() called  ", "C.  Compiler Error ", "D.  Runtime Error "},
            {"A. Insert", "B. Push", "C. Add", "D. none of the above"},
            {"A. Greedy approach ", "B.  Improved banary search ", "C. Dynamic Programing",  "D.  Divide and Conquer "},
            {"A. Stack", "B. Array", "C. Linklist", "D. Queue"},
            {"A. Queue", "B. Stack",  " C.  Hash table", "D. Binary search tree"},
            {"A. CPU Resource Allocation", "B. Breath First Traversal",  "C.  Recursion",  "D. None of the above"},
            {"A. 2n-1", "B. n",  "C. n+1", "D. n-1"}
    };

    private static final char[] answers = {'C', 'B', 'D', 'A' , 'A' , 'C' , 'D'};

    private static int currentQuestion = 0;
    private static int score = 0;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the Quiz Game!");
        System.out.println("Please answer the following questions:");

        while (currentQuestion < questions.length) {
            displayQuestion();
            System.out.print("Enter your answer (A, B, C, or D): ");
            char userAnswer = scanner.next().toUpperCase().charAt(0);

            if (userAnswer == answers[currentQuestion]) {
                System.out.println("Correct!");
                score++;
            } else {
                System.out.println("Incorrect. The correct answer is " + answers[currentQuestion]);
            }

            currentQuestion++;
        }

        System.out.println("\nQuiz completed!");
        System.out.println("Your score: " + score + "/" + questions.length);

        scanner.close();
    }

   private static void displayQuestion() {
        System.out.println("\nQuestion " + (currentQuestion + 1) + ": " + questions[currentQuestion]);
        for (String option : options[currentQuestion]) {
            System.out.println(option);


        }
    }


}
