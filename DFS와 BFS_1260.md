# DFS와 BFS
https://www.acmicpc.net/problem/1260

```java
import java.util.*;

public class Main {
	static int map[][];
	static boolean [] visit;
	static int n, m, v;
	
	// 인접행렬
	public static void dfs(int i) {
		visit[i] = true;	// 탐색을 시작할 번호 v는 방문했으므로 true로 설정
		System.out.print(i + " ");
		for(int j=1; j<=n; j++) {
			if(map[i][j] == 1 && visit[j] == false)
				dfs(j);	// 내가 찾은 경로가 만약 다른 경로가 있으면 바로 다음 곳으로 이동시키고, 없으면 다시 재귀호출로 돌아옴.
		}
	}
	
	// 인접행렬
	public static void bfs(int i) {
		Queue<Integer> q = new LinkedList<Integer>();
		q.offer(i);
		visit[i] = true;			// 방문한 위치는 알아야하므로 체크하기 위해 visit 필요
		while(!q.isEmpty()) {		// 큐가 비어있을때까지
			int temp = q.poll();	// 첫번째 방문한 위치는 빼준다.
			System.out.print(temp + " ");
			
			for(int k=1; k<=n; k++) {
				if(map[temp][k] == 1 && visit[k] == false) {
					q.offer(k);
					visit[k] = true;	// true면 방문한것
				}
			}
		}
	}
	
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		n = scan.nextInt();	// 정점
		m = scan.nextInt();	// 간선
		v = scan.nextInt();	// 탐색 시장할 정점의 번호
		map = new int[n+1][n+1];	// 각 정점간 탐색 경로를 저장할 배열
		visit = new boolean[n+1];	// 정점의 탐색 여부를 체크하기 위한 배열
		
		for(int i=1; i<=m; i++) {
			int a = scan.nextInt();
			int b = scan.nextInt();
			map[a][b] = map[b][a] = 1;
		}
		
		dfs(v);
		
		for(int i=1; i<=n; i++)
			visit[i] = false;
		
		System.out.println();
		
		bfs(v);
		
		scan.close();
	}

}

```
