# laba15
```c
#include <stdio.h>
#include <locale.h>
#define _USE_MATH_DEFINES
#include <math.h>
#define n 10
#define N 100
int task1() {
	float A[n];
	float M[n];
	float temp, sum = 0;
	double sr_zn;
	for (int i = 0; i < 10; i++) {
		printf("a[%d] = ", i + 1);
		scanf("%f", &temp);
		A[i] = temp;
		M[i] = A[i];
	}
	for (int i = 0; i < 10; i++) {
		if (A[i] < 0) {
			M[i] = 0; 
		}
	}
	printf("\n % -10s %-15s %-15s\n", "Индекс", "Исходное значение", "Новое значение");
	for (int i = 0; i < 10; i++) {
		printf("%-10d %-15.2f %-15.2f\n", i + 1, A[i], M[i]);
	}
	for (int i = 0; i < 10; i++) {
		sum += M[i];
	}
	sr_zn = sum / n;
	printf("\nСреднее арифметическое элементов массива (после преобразования): %.2f\n", sr_zn);
	return 0;
}
int task2() {
	double function(double x) {
		return pows(x, 4) - 2 * pows(x, 2) + 1;
	}
	const int N = 100;
	double D[N];
	float sum = 0;
	int count = 0;
	double nach = -1.0;
	double kon = 2.0; 
	double step = (kon - nach) / (N - 1);
	for (int i = 0; i < N; i++) {
		double x = nach + i * step;
		D[i] = function(x);
	}
	double sum_poloj = 0.0;
	double sum_otr = 0.0;
	int count_poloj = 0;
	int count_otr = 0;
	for (int i = 0; i < N; i++) {
		if (D[i] > 0.0) {
			sum_poloj += D[i];
			count_poloj += 1;
		}
		else if (D[i] < 0.0) {
			sum_otr += D[i];
			count_otr += 1;
		}
	}
	double sr_znaj = 0.0;
	if (count_poloj > 0) {
		sr_znaj = sum_poloj / count_poloj;
	}
	printf("D; сумма положиительных элементов массива равна %.4f; cумма отрицательных элементов массива равна %.4f\n", sum_poloj, sum_otr);
	printf("количество положительных элементов массива равно %d; количество отрицательных элементов равно %d\n", count_poloj, count_otr);
	printf("среднее арифметическое положительных элементов массива равно %.4f", sr_znaj);
	return 0;
}
int task_dz() {
	//31. Среднее арифметическое отрицательных элементов массива, расположенных после максимального элемента.
	double sr_zn = 0;
	float sum = 0;
	float temp;
	float B[n];
	int max_ind = 0;
	int count = 0;
	for (int i = 0; i < 10; i++) {
		printf("b[%d] = ", i + 1);
		scanf("%f", &temp);
		B[i] = temp;
	}
	for (int i = 1; i < 10; i++) {
		if (B[i] > B[max_ind]) {
			max_ind = i;
		}
	}
	for (int i = max_ind + 1; i < 10; i++) {
		if (B[i] < 0) { 
			sum += B[i];
			count += 1; 
		}
	}
	printf("\n Максимальный элемент: %.2f (индекс %d)\n", B[max_ind], max_ind);
	if (count = 0) {
		printf("Отрицтельных элементов после максимального нет.\n");
	}
	else {
		sr_zn = sum / count;
		printf("Среднее арифметическое отрицательных элементов после максимума: %.2f\n", sr_zn);
	}
	return 0;
}

int main() {
	setlocale(LC_ALL, ".UTF-8");
	task2();
}
```c
