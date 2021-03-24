
#include <iostream>;

using namespace std;

char** rush(int height, int size)

{

	char** t;

	t = new char* [height];

	for (int i = 0; i < height; i++)

	{

		t[i] = new char[size];
		for (int j = 0; j < size; j++)
		{
			if ((i == 0 && j == 0) || (i== height - 1 && j == size - 1))
			{
				t[i][j] = '/';
			}
			else if ((i == 0 && j == size - 1) || (i == height - 1 && j == 0))
			{
				t[i][j] = '\\';
			}
			else if (((i == 0 || i == height - 1))||((j == 0 || j == size - 1)))
			{
				t[i][j] = '*';
			}
			else
			{
				t[i][j] = ' ';
			}
		}

	}

	return t;

}

void PrintTwoArray(char** array, int height, int size)

{

	for (int i = 0; i < height; i++)

	{

		for (int j = 0; j < size; j++)

		{

			cout << array[i][j] << " ";

		}

		cout << endl;

	}

	cout << endl;

}

int main()

{

	setlocale(LC_ALL, "ru");

	int height, size;

	char** array;

	cout << "введите размерность матрицы" << endl;

	cin >> size >> height;

	array = rush(height, size);

	PrintTwoArray(array, height, size);

	system("pause");

	return 0;

}
