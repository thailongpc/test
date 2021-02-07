#include <iostream>

using namespace std;
#define size 20
#define TRUE 1
#define FALSE 0
int c, STOP;

void print(int A[], int n)
{
	c++;
	cout << "phan tu thu " << c << ": ";
	for (int i = 1; i <= n; i++)
	{
		cout << A[i] << " ";
	}
	cout << endl;
}

void SetValue(int A[], int n)
{
	for (int i = 1; i <= n; i++)
	{
		A[i] = 0;
	}
}

void Process(int A[], int n)
{
	int i = n;
	while (i > 0 && A[i])
		i--;
	if (i > 0) {
		A[i] = 1;
		for (int j = i+ 1; j <= n; j++)
		{
			A[j] = 0;
		}
	}
	else
		STOP = TRUE;
}

void Show(int A[], int n)
{
	while (!STOP)
	{
		print(A, n);
		Process(A, n);
	}
}
int main()
{
	int A[size];
	int n;
	cin >> n;
	SetValue(A, n);
	Show(A, n);

	return 0;
}
