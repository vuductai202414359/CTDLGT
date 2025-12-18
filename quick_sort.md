#include <iostream>


void quick_sort(int a[], int l, int r, int n) {
	int p = a[(l + r) / 2];
	int i = l, j = r;
	while (i < j) {
		while (a[i] < p) {
			i++;
		}
		while (a[j] > p) {
			j--;
		}
		if (i <= j) {
			std::swap(a[j], a[i]);
			i++;
			j--;
		}
	}
	if (i < r) {
		quick_sort(a, i, r, n);
	}
	if (l < j) {
		quick_sort(a, l, j, n);
	}
	for (int k = 0; k < n; k++) {
		std::cout << a[k] << " ";
	}
	std::cout << "\n";

}
int main()
{
	int a[] = { 3, 10, 1, 23, 103, 34, 17, 53, 64, 71 };
	int n = sizeof(a) / sizeof(a[0]);
	quick_sort(a, 0, n-1, n);
	return 0;
}
