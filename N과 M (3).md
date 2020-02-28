# N과 M (3)
https://blog.naver.com/zzang9ha/221815893032

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class Main {
	public static int arr[];
	public static int N;
	public static int M;
	public static StringBuilder sb = new StringBuilder();
	
	public static void dfs(int count) {
		if(count == M) {
			for(int i : arr)
				sb.append(i + " ");
			sb.append("\n");
			return;
		}
		
		for(int i=1; i<=N; i++) {
			arr[count] = i;
			dfs(count + 1);
		}
	}

	public static void main(String[] args) throws IOException {
		BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
		String str = bf.readLine();
		StringTokenizer st = new StringTokenizer(str);
		N = Integer.parseInt(st.nextToken());
		M = Integer.parseInt(st.nextToken());
		arr = new int[M];
		dfs(0);
		
		System.out.println(sb);
		bf.close();
	}

}

```
