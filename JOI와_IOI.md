# JOI와 IOI
https://www.acmicpc.net/problem/5586
```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		String str = scan.next();
		int JOI_count = 0;
		int IOI_count = 0;
		
		for(int i=0; i<str.length()-2; i++)
		{
			// 문자열이 JOI의 연속일때
			if(str.charAt(i) == 'J' && str.charAt(i+1) == 'O' && str.charAt(i+2) == 'I')
				JOI_count += 1;
			
			// 문자열이 IOI의 연속일때
			if(str.charAt(i) == 'I' && str.charAt(i+1) == 'O' && str.charAt(i+2) == 'I')
				IOI_count += 1;
		}
		
		System.out.println(JOI_count);
		System.out.println(IOI_count);
	}

}

```
