#include <bits/stdc++.h>

using namespace std;

class shoppinglist
{
    private:
    string pname;
    int pcode;
    float price;
    float dis;
    
    public;
    void menu();
    void add();
    void rem();
    void list();
    void buyer();
    void administrator();
    void edit();
    void receipt();
};

void shoppinglist :: menu()
{
    m:
    int choice;
    string email;
    string password;
    
    cout<<"\n\t\t\t |                          |"<<endl;
    cout<<"\n\t\t\t |  Supermarket Main Menu   |"<<endl;
    cout<<"\n\t\t\t |                          |"<<endl;
    cout<<"\n\t\t\t  1) Administrator           "<<endl;
    cout<<"\n\t\t\t  2) Buyer                   "<<endl;
    cout<<"\n\t\t\t  3) Exit                    "<<endl;
    cout<<"\n\t\t\tEnter your choice:";
    cin>>choice;
    cout<<"\n\t\t\t";
    
    switch(choice)
    {
        case 1:
        {
            cout<<"\n\t\t\t Enter your login details\n\n";
            cout<<"\n\t\t\t Enter your email:";
            cin>>email;
            cout<<"\n\t\t\t Enter your password:";
            cin>>password;
            
            if(email=="robby123@gmail.com" && password=="robby123")
            {
                administrator();
            }
            else
            {
               cout<<"Invaid login details"<<endl; 
            }
            break;
        }
        
        case 2:
        {
            buyer();
        }
        
        case 3:
        {
            exit(0);
        }
        
        default:
        {
            cout<<"Please select from the given options"<<endl;
        }
    }
    goto m;
}

void shoppinglist :: administrator()
{
    m:
    int choice;
    cout<<"\n\t\t\t  |                            |"<<endl;
    cout<<"\n\t\t\t  |  Administrator Main Menu   |"<<endl;
    cout<<"\n\t\t\t  |                            |"<<endl;
    cout<<"\n\t\t\t 1)Add product        ";
    cout<<"\n\t\t\t 2)Edit product       ";
    cout<<"\n\t\t\t 3)Delete product     ";
    cout<<"\n\t\t\t 4)Return to main menu";
    cout<<"Enter your choice:";
    cin>>choice;
    
    switch(choice)
    {
        case 1:
        {
            add();
            break;
        }
        case 2:
        {
            edit();
            break;
        }
        case 3:
        {
            rem();
            break;
        }
        case 4:
        {
            menu();
            break;
        }
        deafult:
        {
            cout<<"Please select from the given options"<<endl;
        }
    }
    goto m;
}
void shoppinglist :: buyer()
{
    m:
    int choice;
    cout<<"\n\t\t\t  |                            |"<<endl;
    cout<<"\n\t\t\t  |    Customer Main Menu      |"<<endl;
    cout<<"\n\t\t\t  |                            |"<<endl;
    cout<<"\n\t\t\t 1)Buy product              ";
    cout<<"\n\t\t\t 2)Back to main menu        ";
    cout<<"Enter your choice:";
    cin>>choice;
    
    switch(choice)
    {
        case 1:
        {
            receipt();
            break;
        }
        case 2:
        {
            menu();
            break;
        }
        default:
        {
            cout<<"Please select from the given options"<<endl;
        }
    }
    goto m;
}

void shoppinglist :: add()
{
    m:
    fstream data;
    int c;
    int token=0;
    float p;
    float d;
    string n;
    
    cout<<"\n\n\n Add New Product \n\n\n";
    cout<<"\n Enter product code:";
    cin>>pcode;
    cout<<"\n Enter product name:";
    cin>>pname;
    cout<<"\n Enter product price:";
    cin>>price;
    cout<<"\n Enter product discount:";
    cin>>dis;
    
    data.open("Database.txt",ios::in);
    
    if(!data)
    {
        data.open("Database.txt",ios::app|ios::out);
        data<<" "<<pcode<<" "<<pname<<" "<<price<<" "<<dis<<"\n";
        data.close();
    }
    else
    {
        data>>c>>n>>p>>d;
        
        while(!data.eof())
        {
            if(c==pcode)
            {
                token++;
            }
            data>>c>>n>>p>>d;
        }
        data.close();
    if(token==1)
    {
        goto m;
    }
    else
    {
        data.open("Database.txt",ios::app|ios::out);
        data<<" "<<pcode<<" "<<pname<<" "<<price<<" "<<dis<<"\n";
        data.close();
    }
    }
    
    cout<<"\n\t\t\tRecord Inserted";
}
void shopping :: edit()
{
    fstream data,data1;
    
}
