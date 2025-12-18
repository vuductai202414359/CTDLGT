#include <iostream>


void insert_sort(int a[], int n)
{
	for (int i = 1; i < n; i++)
	{
		int t = a[i];
		int j = i;
		while (j > 0 && a[j - 1] > t) {
			a[j] = a[j - 1];
			j--;
		}
		a[j] = t;
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
	insert_sort(a, n);
	return 0;
}
