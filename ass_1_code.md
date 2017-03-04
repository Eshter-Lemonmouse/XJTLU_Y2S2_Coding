#include <iostream>
#include <vector>
#include <string>
#include <algorithm>

using namespace std;

int get_number(vector<int> *ptr)
{
	int tag = 0;
	if (cin >> tag)
	{
		cin.clear();
		cin.ignore();
		(*ptr).push_back(tag);
		return 0;
	}
	else	
	{
		cin.clear();
		cin.ignore();
		return 1;
	}
}

bool same_vec(vector<int> a, vector<int> b)
{
	int i, j;
	int size_more, size_less;
	int flag = 0;
	vector<int> more, less;
	if (a.size() >= b.size())
	{
		more.swap(a);
		less.swap(b);
		//size_more = more.size();//////////////////////////////////////
	}
	else
	{
		more.swap(b);
		less.swap(a);
	}
	size_more = more.size();
	size_less = less.size();
	for (i = 0; i < size_less; i++)
	{
		for (j = 0; j < size_more; j++)
		{
			if (less[i] == more[j])
			{
				flag = 1;
				break;
			}
		}
		if (flag < 1)
		{
			return false;
		}
	}
	return true;
}

int main(void)
{
	vector<int> vessel_1, vessel_2;
	int flag = 0, size_1 = 0, size_2 = 0;
	int i;
	//int tag = 0;/////////////////////////////////////////////shu
	while (!flag)//////////////////////////这里好好的
	{
		cout << "please input the number for list 1, press any other key and enter to quit." << endl;
		flag = get_number(&vessel_1);
//		if (cin >> tag)///////////////////////////////////////////
//		{
//			cin.clear();////////////////////////////////////////
			//cin.sync();//////////////////////
//			cin.ignore();///////////////////////
//			vessel_1.push_back(tag);////////////////////////////////////////
//		}
//		else///////////////////////////////
//		{
//			cin.clear();///////////////////////////////////
			//cin.sync();////////////////////////
//			cin.ignore();
//			flag = 1;/////////////////////////////////////////
//		}
	}
	flag = 0;
	while (!flag)////////////////////这里坏了
	{
		cout << "please input the number for list 2, press any other key and enter to quit." << endl;
		flag = get_number(&vessel_2);
//		if (cin >> tag)////////////////////////////////////////////
//		{
//			cin.clear();//////////////////////////////////////
//			cin.ignore();////////////////////////////////
			//cin.sync();/////////////////////////////////////////////
//			vessel_2.push_back(tag);//////////////////////////////////
//		}
//		else/////////////////////////////////////////////
//		{
//			cin.clear();//////////////////////////////////
//			cin.ignore();////////////////////////
			//cin.sync();//////////////////////////////////////
//			flag = 1;////////////////////////////////////////////////
//		}
	}
	//size_1 = vessel_1.size();
	//size_2 = vessel_2.size();
	if (same_vec(vessel_1, vessel_2))
	{
		cout << "both equal." << endl;
	}
	else
	{
		cout << "wrong." << endl;
	}
//	for (i = 0; i < size_1; i++)
//	{
//		cout << vessel_1[i] << '\t';
//	}
//	cout << endl;
//	for (i = 0; i < size_2; i++)
//	{
	//	cout << vessel_2[i] << '\t';
//	}
//	cout << endl;
	return 0;
}
