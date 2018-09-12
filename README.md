# 9.12.4
常成员函数
// 9.12.4常成员函数.cpp : 定义控制台应用程序的入口点。
// const在类中的使用

#include "stdafx.h"
#include<iostream>
using namespace std;
class R{
public:
	R(int r1,int r2):r1(r1),r2(r2){}
	void print();
	void print() const;
private:
	int r1,r2;
};

void R::print() //也可以只包含const函数，则a对象也会调用R::print() const函数
{
	cout<<"r1:"<<r1<<", r2:"<<r2<<endl;
	//r1=6; 不会报错。
}
void R::print() const
{
	cout<<"r1:"<<r1<<", r2:"<<r2<<endl;
	//r1=6; 会报错。
}

int _tmain(int argc, _TCHAR* argv[])
{
	R a(5,6);
	a.print (); //调用void R::print()
	const R b(32,42);
	b.print (); //调用void R::print() const
	
	return 0;
}

