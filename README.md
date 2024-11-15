# titulo luego cambiar
## algoritmo usado en lenguaje java:
```java

import java.util.Random;
import java.util.Scanner;

public class main {

    public static void main(String[] args) {
        Random rrr = new Random();
        Scanner leer = new Scanner(System.in);
        System.out.println("INGRESE LA DIMENSION");
        int d = leer.nextInt();
        int m[][] = new int[d][d];
        for (int i = 0; i < m.length; i++) {
            for (int j = 0; j < m[0].length; j++) {
                m[i][j] = rrr.nextInt(101);
            }

        }

        for (int i = 0; i < m.length; i++) {
            for (int j = 0; j < m[0].length; j++) {
                System.out.print("[" + m[i][j] + "]  ");
            }
            System.out.println("");
        }

        int suma = 0;

        System.out.println("INGRESE ANILLO A SUMAR");
        int k = leer.nextInt();
        int axi1 = k - 1;
        int axi2 = d - k;

        for (int i = k - 1; i <= d - k; i++) {
            suma += m[axi1][i];
            suma += m[axi2][i];
            suma += m[i][axi1];
            suma += m[i][axi2];
        }
        suma -= m[axi1][axi1];
        suma -= m[axi1][axi2];
        suma -= m[axi2][axi1];
        suma -= m[axi2][axi2];
        
        if (d % 2 != 0 && k == (d / 2) + 1) {
            int centro = d / 2;
            suma = m[centro][centro];
        }

        System.out.println("la suma del anillo " + k + " es de " + suma);
    }
}

