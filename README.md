package academy.learnprogramming;

public class Main {

    public static void main(String[] args) {

        //byte - rarely used
        //short - rarely used
        //int - common
        //long - occasionally used
        //float - rarely used
        //double - common
        //char - occasionally used
        //booblean - common

        // string = a class; a sequence of characters
        String myString = "This is a string";
        System.out.println("myString is equal to " + myString);
        myString = myString + ", and this is more.";
        System.out.println("myString is equal to " + myString);
        myString = myString + " \u00A9 2019";
        System.out.println("myString is equal to " + myString);

        String numberString = "250.55";
        numberString = numberString + "49.95";
        System.out.println(numberString);
        //not an int!  Only deals with text, so the numbers are considered text

        String lastString = "10";
        int myInt = 50;
        lastString = lastString + myInt;
        System.out.println("LastString is equal to " + lastString);

        double doubleNumber = 120.47d;
        lastString = lastString + doubleNumber;
        System.out.println("LastString is equal to " + lastString);




    }
}
