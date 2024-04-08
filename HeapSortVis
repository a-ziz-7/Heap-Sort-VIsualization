import java.util.Scanner;

public class HeapSortVis {

    static int hs;

    public static void main(String[] args) {
        System.out.println("Enter A Number (1-31):");
        Scanner sc = new Scanner(System.in);
        int[] workingArray = generateArray(sc.nextInt());

        heapSort(workingArray, true);
        formattedArrayPrint(workingArray);

    }

    public static void heapSort(int[] A, boolean visualisation) {
        formattedArrayPrint(A);
        buildHeap(A);
        for (int i = A.length - 1; i >= 1; i--) {
            if (visualisation) {
                printInBinaryTreeFormatting(A, A.length - 1);
            }
            int s = A[i];
            A[i] = A[1];
            A[1] = s;
            hs--;
//            printInBinaryTreeFormatting(A, A.length - 1);
            maxHeapify(A, 1);
        }
    }

    public static void buildHeap(int[] A) {
        hs = A.length;
        for (int i = ((A.length) / 2); i > 0; i--) {
            maxHeapify(A, i);
        }
    }

    public static void maxHeapify(int[] A, int i) {
        int l = i * 2;
        int r = i * 2 + 1;
        int largest;
        if (l < hs && A[l] > A[i]) {
            largest = l;
        } else {
            largest = i;
        }
        if (r < hs && A[r] > A[largest]) {
            largest = r;
        }
        if (largest != i) {
            int s = A[i];
            A[i] = A[largest];
            A[largest] = s;
//            System.out.println("Index: " + largest + "  " + A[i] + " | " + i + " " + A[largest]);
            maxHeapify(A, largest);
        }
    }

    public static int[] generateArray(int x) {
        int[] ans = new int[x + 1];
        ans[0] = 0;
        for (int i = 1; i <= x; i++) {
            ans[i] = (int) (Math.random() * 100) + 1;
        }
        return ans;
//        return new int[]{0, 16, 14, 10, 8, 7, 9, 3, 2, 4, 1};
//        return new int[]{0, 5, 13, 2, 25, 7, 17, 20, 8, 4};
    }

    public static void printInBinaryTreeFormatting(int[] A, int x) {
        int height = (int) Math.floor(Math.log(x) / Math.log(2));
        int bottom = (int) (Math.pow(2, height) * 5 + (Math.pow(2, height) - 1) * 3);
        int index = 1;
        System.out.println();
        for (int i = 0; i < height + 1; i++) {
            bottom = (bottom - 5) / 2 + 1;
            for (int iter = 0; iter < Math.pow(2, i); iter++) {
                if (index == A.length) {
                    break;
                }
                System.out.print(lilFormatting(bottom) + notSoLilFormatting(A[index], index) + lilFormatting(bottom) + " ");
                index++;
            }
            System.out.println();

        }
    }

    public static String lilFormatting(int x) {
        StringBuilder a = new StringBuilder();
        for (int i = 0; i < x; i++) {
            a.append(" ");
        }
        return a.toString();
    }

    public static String notSoLilFormatting(int x, int i) {
        if (i >= hs || hs == 2) {
            if (String.valueOf(x).length() == 1) {
                return "| " + x + "*|";
            } else {
                return "|" + x + "*|";
            }
        } else {
            if (String.valueOf(x).length() == 1) {
                return "| " + x + " |";
            } else {
                return String.format("|%-3d|", x);
            }
        }
    }

    public static void formattedArrayPrint(int[] arr){
        System.out.print("[");
        for (int i = 1; i < arr.length-1; i++){
            System.out.print(arr[i] + ", ");
        }
        System.out.println(arr[arr.length-1] + "]");
    }

}
