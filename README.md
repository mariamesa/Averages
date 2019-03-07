# Averages
This program reads in numbers from a file and finds their average.

import java.util.Scanner;
import java.io.*;

public class Averages {
    public static void main(String[] arg) throws IOException {
        Scanner inFile = new Scanner(new File("numbers.txt"));
        int header, count = 0, nums;
        double total, avg;

        while (inFile.hasNextInt()) {
            header = inFile.nextInt();
            total = 0;
            System.out.print("The average of the " + header + " integers ");
            for (int i = 0; i < header; i++) {
                nums = inFile.nextInt();
                total += nums;
                System.out.print(nums + " ");
            }
            avg = total / header;
            System.out.print("is " + avg + "\n");
            count++;
        }
        System.out.println(count + " sets of numbers processed");
        inFile.close();
    }
}
