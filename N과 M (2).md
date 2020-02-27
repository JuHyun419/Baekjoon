# N과 M (2)
https://www.acmicpc.net/problem/15650

```java
import java.util.Scanner;

public class Main {
	public static int arr[];
	public static boolean visit[];
	public static int N;
	public static int M;
	public static StringBuilder sb = new StringBuilder();
	
	public static void dfs(int count) {
		if(count == M) {
			for(int i=0; i<M-1; i++) {
				if(arr[i] > arr[i+1])
					return;
			}
			
			for(int i : arr)
				sb.append(i + " ");
			sb.append("\n");
			return;
		}
		
		for(int i=1; i<=N; i++) {
			if(!visit[i]) {
				visit[i] = true;
				arr[count] = i;
				dfs(count+1);
				visit[i] = false;
			}
		}
	}

	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		N = scan.nextInt();
		M = scan.nextInt();
		arr = new int[M];
		visit = new boolean[N+1];
		dfs(0);
		
		System.out.println(sb);
		scan.close();
	}

}

```
