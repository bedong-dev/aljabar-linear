# aljabar-linear
mencari matrik ordo 3x3
	

From Tiny Lemur, 1 Second ago, written in Java.
This paste is a reply to deteminant matrik from bedong believer - view diff
URL https://pastebin.pl/view/d1be9a34
Embed Show code
Download Paste or View Raw
Hits: 0

        import java.util.Scanner;
        public class Determinant {
            Scanner input = new Scanner(System.in);
         
            public void ordo_2x2() {
                System.out.print("Ordo matrik 2x2");
                int[][] matrik = new int[2][2];
                System.out.println("\n Masukan Elemen Matrik :");
                for (int i = 0; i < 2; i++) {
                    for (int j = 0; j < 2; j++) {
                        System.out.print("[baris] [kolom] [" + (i + 1) + "," + (j + 1) + "]="); // input elemen matrik
                        matrik[i][j] = input.nextInt();
                    }
                }
                for (int i = 0; i < 2; i++) {
                    System.out.print("|");   // menampilkan elemen matrk ordo 2x2
                    for (int j = 0; j < 2; j++) {
                        System.out.print(matrik[i][j] + " ");
                    }
                    System.out.println("|");
                }
                // proses mencari determinan matrik 2x2
                int determinant = (matrik[0][0] * matrik[1][1]) - (matrik[0][1] * matrik[1][0]);
                System.out.println("det(A)= " + determinant);
            }
         
            public void ordo_3x3() {
                int[][] matrikA = new int[3][3];
                System.out.println("Ordo matrik 3x3 :");
                System.out.println("\n masukan elemen matrik 3x3 :");
                for (int i = 0; i < 3; i++) {
                    for (int j = 0; j < 3; j++) {
                        System.out.print("[baris] [kolom] [" + (i + 1) + "," + (j + 1) + "]=");
                        matrikA[i][j] = input.nextInt();  // mengisi elemen matrik
         
                    }
                }
                // menampilkan element matrik 3x3 di layar
                for (int i = 0; i < 3; i++) {
                    System.out.print("|");
                    for (int j = 0; j < 3; j++) {
                        System.out.print(matrikA[i][j] + " ");
                    }
                    System.out.println("|");
                }
                // mencari determinant matrik ordo 3x3 dengan metode ekpansi kofaktor
                // dengan acuan det(A)=a11.c11+a12.C12+a13.C13
                int determinant = matrikA[0][0] * ((matrikA[1][1] * matrikA[2][2]) - (matrikA[2][1] * matrikA[1][2])) -
                        matrikA[0][1] * (matrikA[1][0] * matrikA[2][2] - matrikA[2][0] * matrikA[1][2]) + matrikA[0][2] * (matrikA[1][0]*
                        matrikA[2][1] - matrikA[2][0] * matrikA[1][1]);
                System.out.println("det(A)= " + determinant);
         
            }
              public void menu(){
         
                  int pilihan;
         
                  System.out.println("MENU");
                  System.out.println("1.ordo 2x2 det(A)");
                  System.out.println("2.ordo 3x3 det(A)");
                     pilihan = input.nextInt();
         
                  if (pilihan==1) {
                      ordo_2x2();
                  } else {
                      ordo_3x3();
                  }
              }
         
         
         
         
         
             public static void main(String []args) {
         
         
                 Determinant det = new Determinant();
                 det.menu();
         
         
         
         
             }
         
        }
         
         
         
         
