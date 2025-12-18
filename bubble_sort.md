#include <iostream>

void bubble_sort(int a[], int n)
{
	for (int i = 0; i < n - 2; i++) {
		for (int j = n - 1; j > i; j--) {
			if (a[j - 1] > a[j]) {
				std::swap(a[j - 1], a[j]);
			}
		}
		for (int i = 0; i < n; i++) {
			std::cout << a[i] << " ";
		}
		std::cout << "\n";
	}
}
int main()
{
	int a[] = { 3, 10, 1, 23, 103, 34, 17, 53, 64, 71 };
	int n = sizeof(a) / sizeof(a[0]);
	bubble_sort(a, n);
	return 0;
}
