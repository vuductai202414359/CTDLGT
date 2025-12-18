#include <iostream>
int t[1000];

void in (int a[], int n) {
    for (int i = 0; i < n; i++)
        std::cout << a[i] << " ";
    std::cout << "\n";
}
void mergeParts(int a[], int l, int m, int r) {
    int i = l, j = m + 1;
    int k = 0;

    while (i <= m && j <= r) {
        int l;

        if (a[i] < a[j]) l = a[i++];
        else l = a[j++];
        t[k++] = l;
    }

    while (i <= m) t[k++] = a[i++];
    while (j <= r) t[k++] = a[j++];

    for (int i = 0; i < k; i++) a[l + i] = t[i];

}

void mergeSort(int a[], int l, int r) {
    if (l >= r) return;

    int m = (l + r) / 2;

    mergeSort(a, l, m);
    mergeSort(a, m + 1, r);
    mergeParts(a, l, m, r);
}
int main()
{
	int a[] = { 3, 10, 1, 23, 103, 34, 17, 53, 64, 71 };
	int n = sizeof(a) / sizeof(a[0]);
	mergeSort(a, 0, n-1);
    in(a, n);
	return 0;
}
