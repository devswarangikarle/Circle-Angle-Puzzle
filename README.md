# Circle-Angle-Puzzle

Liam was feeling puzzled after hearing Ethan’s mysterious story. To lighten the mood, Ethan decides to distract him with a quick riddle. He arranges K enchanted stones in a perfect circle, equally spaced, and numbers them from 1 to K in a clockwise order.
Pointing to two stones, X and Z, he asks, “How many choices are there for a third stone, Y, such that the angle XYZ is obtuse?”
Liam’s curiosity is piqued, and he’s ready for the challenge.

import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int T = Integer.parseInt(br.readLine().trim());
        while (T-- > 0) {
            String[] input = br.readLine().trim().split(" ");
            long K = Long.parseLong(input[0]);
            long X = Long.parseLong(input[1]);
            long Z = Long.parseLong(input[2]);
            long D = Math.min((Z - X + K) % K, (X - Z + K) % K);
            long result;
            if (D == K / 2 && K % 2 == 0) {
                result = 0;
            } else if (D < K / 2) {
                result = D - 1;  
            } else { 
                 result = (D > K / 2) ? (K - D - 1) : (D - 1);
            }
            System.out.println(result);
        }
    }
}
