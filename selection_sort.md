#include <iostream>

using namespace std;
void selection_sort(int a[], int n)
{
	for (int i = 0; i < n; i++)
	{
		int t = i;
		for (int j = i + 1; j < n; j++)
		{
			if (a[j] < a[t])
			{
				t = j;
			}
		}
		std::swap(a[i], a[t]);
		for (int i = 0; i < n; i++)
		{
			std::cout << a[i] << " ";
		}
		std::cout << "\n";
	}
}
int main()
{
    int a[] = {3, 10, 1, 23, 103, 34, 17, 53, 64, 71};
	int n = sizeof(a) / sizeof(a[0]);
	selection_sort(a, n);
	return 0;
}
