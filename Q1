Question : Smallest submatrix with Kth maximum XOR

// Java Program for above approach 
import java.util.*; 
import java.lang.*; 

class GFG { 

	// Function to print smallest index of 
	// Kth maximum Xor value of submatrices 
	static void smallestPosition(int m[][], int k) 
	{ 

		// Dimensions of matrix 
		int n = m.length; 
		int mm = m[0].length; 

		// Stores XOR values for every index 
		int[][] xor = new int[n][mm]; 

		// Min heap to find the 
		// kth maximum XOR value 
		PriorityQueue<Integer> minHeap 
			= new PriorityQueue<>(); 

		// Stores indices for 
		// corresponding XOR vlaues 
		Map<Integer, int[]> map 
			= new HashMap<>(); 

		// Traversing matrix to 
		// calculate XOR values 
		for (int i = 0; i < n; i++) { 
			for (int j = 0; j < mm; j++) { 

				int a = i - 1 >= 0
							? xor[i - 1][j] 
							: 0; 

				int b = j - 1 >= 0
							? xor[i][j - 1] 
							: 0; 

				int c = (i - 1 >= 0 && j - 1 >= 0) 
							? xor[i - 1][j - 1] 
							: 0; 

				xor[i][j] = m[i][j] ^ a ^ b ^ c; 

				// Insert calculated value 
				// in Min Heap 
				minHeap.add(xor[i][j]); 

				// If size exceeds k 
				if (minHeap.size() > k) { 

					// Remove the minimum 
					minHeap.poll(); 
				} 

				// Store smallest index 
				// containing xor[i][j] 
				if (!map.containsKey(xor[i][j])) 
					map.put(xor[i][j], 
							new int[] { i, j }); 
			} 
		} 

		// Stores the kth maximum element 
		int kth_max_e = minHeap.poll(); 

		// Print the required index 
		System.out.println( 
			(map.get(kth_max_e)[0] + 1) 
			+ " " + (map.get(kth_max_e)[1] + 1)); 
	} 
	// Driver Code 
	public static void main(String[] args) 
	{ 

		int m[][] = { { 1, 2, 3 }, 
					{ 2, 2, 1 }, 
					{ 2, 4, 2 } }; 
		int k = 1; 

		// Function call 
		smallestPosition(m, k); 
	} 
}
