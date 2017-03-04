#include <iostream>
#include <vector>

using namespace std;

int get_number(vector<int> *ptr)
{
	rewind(stdin);
	int tag = 0;
	if (cin >> tag)
	{
		rewind(stdin);
		(*ptr).push_back(tag);
		return 0;
	}
	else
	{
		rewind(stdin);
		return 1;
	}
}

//bool same_vec(vector<int> a, vector<int> b)
//{

//}

int main(void)
{
	vector<int> vessel_1;
	vector<int> vessel_2;
	int flag = 0, size_1 = 0, size_2 = 0;
	int i;
	while (!flag)//////////////////////////这里好好的
	{
		cout << "please input the number for list 1, press any other key and enter to quit." << endl;
		flag = get_number(&vessel_1);
	}
	flag = 0;
	while (!flag)////////////////////这里坏了
	{
		cout << "please input the number for list 2, press any other key and enter to quit." << endl;
		flag = get_number(&vessel_2);
		//system("pause");////////////////////////////////////shu
	}
	size_1 = vessel_1.size();
	size_2 = vessel_2.size();
	for (i = 0; i < size_1; i++)
	{
		cout << vessel_1[i] << '\t';
	}
	cout << endl;
	for (i = 0; i < size_2; i++)
	{
		cout << vessel_2[i] << '\t';
	}
	cout << endl;
	return 0;
}
