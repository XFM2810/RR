#include<stdio.h>
int main() {
	char c[] = "Ab1xyz874[429]2323";
	int i = 0, sum = 0, j = 0, flag = 0;
	int a[100]={ 0 };
	while (c[i] != '\0') {
		if (c[i] <= '9'&&c[i] >= '0') {
			a[flag++] = c[i] - 48;
		}
		i++;
	}
	
	for (int i = 1; i < flag; i++) {
		if (a[i] == a[i - 1] + 1) {
			sum = sum * 10 + a[i-1 ];
			j++;
		}
		else if (j > 0) {
			sum = sum * 10 + a[i-1];
			break;
		}
		else {
			sum = 0;
			j = 0;
		}
	}
	printf("%d", sum);
}

