# ClassWork

package com.company;


import java.io.*;
import java.util.*;
import java.util.Random;

public class Main {

    public static void main(String[] args) {
        // write your code here



        //1) Create a one dimensional array that can store 50 integers
        int array[]= new int [50];

        // 2) use a random number generator to create a values between 1 - 8, and then loop to fill the array

        System.out.print("Task 3:\n\n");

        Random rand = new Random();

        for (int i=0; i<50; i++){
          array[i]= rand.nextInt(8) + 1;

          //3) print the contents of the array to the screen
          System.out.print(" " + array[i]);
        }

        // 4) Create a second array that can store 50 integers
        int array2[] = new int [50];

        //  5) Open and read the file fiftyInts.txt into the array, and print the contents of the array to the screen



        System.out.print("\n\n\n Task 5: \n\n");
        try {

            File userFile = new File("fiftyInts.txt");
            Scanner scanUserFile = new Scanner(userFile, "UTF-8");

        for(int i=0; i < 50; i++) {

            if (scanUserFile.hasNextInt()) {

                array2[i] =  scanUserFile.nextInt();
                System.out.print(" " + array2[i]);

            }
            else {
                System.out.print("\n\nDataFileFILE has been completely READ OR NON INTEGER VALUE FOUND\n\n");
                scanUserFile.close();

                break;
            }
        }
     } catch (FileNotFoundException e) {
            System.err.format("File Not Found Exception: %s%n", e);
            e.printStackTrace();
        }

        //   6) Find every position in the arrays where the values in the array match and print this to the screen

        System.out.print("\n\n Task 6: ");
      for (int i = 0; i<50; i++) {
          if (array[i]==array2[i]){
              System.out.print(" " + i);
          }
      }



    }// end main method
}// end main class
