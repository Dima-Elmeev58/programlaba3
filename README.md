# programlaba3
package com.company;
import java.util.Scanner;
public class Main {

    public static void main(String[] args) {
	// write your code here
        Scanner scanner = new Scanner(System.in);

        System.out.println("Введите число строк и столбцов двумерного массива:");
        int n = scanner.nextInt();

        int[][] array = new int[n][n];

        System.out.println("Введите элементы массива:");
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                array[i][j] = scanner.nextInt();
            }
        }

        for (int i = 1; i < n; i++) {
            int key = array[i][i];
            int j = i - 1;
            while (j >= 0 && array[j][j] > key) {
                array[j + 1][j + 1] = array[j][j];
                j--;
            }
            array[j + 1][j + 1] = key;
        }

        System.out.println("Отсортированный массив по главной диагонали:");
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print(array[i][j] + " ");
            }
            System.out.println();
        }
    }
}
