#include<iostream>
using namespace std;
 class emp
 {
    string name_of_cust,type_of_acc;
    int acc_no;
    float balance;

public:emp() //default const
{
    cout<<"enter the name of customer:";
    getline(cin,name_of_cust);
    cout<<"enter you type of accoont";
    getline(cin,type_of_acc);
    cout<<"account no:";
    cin>>acc_no;
    cout<<"current balance";
    cin>>balance;
}

public:emp(string n,string tn,int a,float b) //parameterized const
{
    name_of_cust =n;
    type_of_acc=tn;
    acc_no=a;
    balance=b;

}
public: emp(const emp &e1)  //copy constructor
{
    name_of_cust =e1.name_of_cust;
    type_of_acc=e1.type_of_acc;
    acc_no=e1.acc_no;
    balance=e1.balance;
}
public:void deposit( int amt)
{
    balance=balance+amt;
}
public:void withdrawl(int w_amt)
{
    if(balance>=w_amt)
{
    balance=balance-w_amt;
    
}
else{
    cout<<"insufficent amt";
}
}
public:void display()
{
    cout<<name_of_cust<<endl<<type_of_acc<<endl;
    cout<<acc_no<<endl;
    cout<<"balance is"<<balance<<endl;
}
 };

int main()
{
    emp e;
    emp e1("shashi","savings",23,5000);
    emp e2(e1);
    e.deposit(500);
    e.withdrawl(1000);
    e.display();
    return 0;
}
