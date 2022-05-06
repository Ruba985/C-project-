
# Supermarket Management System Software using C++ 




.

.


## Table of Contents 

1. [API Reference](#API_Reference)
2. [Environment Variables](#Environment_Variables)
3. [Used By](#Used_By)
4. [Run Locally](#Run_Locally)
5. [Programmers](#Programmers)


## [API Reference]

this program has three functions `main()`,`ADMINISTRATOR_menu ()` and 
`show_PRODUCT_list (string* , float*)`

#### **main function**

- the main fuction asks the user to specify whether they are `CUSTOMER` or `ADMINISTRATOR` or If they wants to exit

*the output of main fuction*

```
______
 1. CUSTOMER
 2. ADMINISTRATOR
 3. EXIT
______
Option: 
```
- Here along with the word `option`, the user should enter the chosen number from the mentioned list
    * If the user's choice is `customer`, all the available products will be shown with their prices and appear as a menu from the function `show_product_list`.
    
    *the output of the products list*
 ```
    ______
    NO.            NAME            PRICE
    ______
    1              ....              0$
    2              ....              0$
```
    
    Then, the user can enter the number of the required product, its quantity and if they want to add another product. then, calculate the total price and print the bill
    
```
    ___ invoice ___
    _______
    Pr No.    Pr Name          Quantity      Price          Total Amount

    _______
    1         ....               -           0$              0$


                Total : 0$
```
    * If the user's choice is `ADMINISTRATOR`, it will move to the `ADMINISTRATOR menu` function


#### **ADMINISTRATOR_menu**

- when the user choose `ADMINISTRATOR`, it will show a new menu for the user to specify what they want to do as ADMINISTRATOR 
```
        ADMINISTRATOR MENU

______
 Press 1 to CREATE PRODUCT
 Press 2 to DISPLAY ALL PRODUCTS
 Press 3 to QUERY 
 Press 4 to MODIFY PRODUCT
 Press 5 to DELETE PRODUCT
 Press 6 to GO BACK TO MAIN MENU
______

  Option: 
```
- Here along with the word `option`, the user should enter the chosen number from the mentioned list


#### **show_PRODUCT_list**

This function print the list of the products and their prices, and it use in the `main` fuction and the `ADMINISTRATOR_menu` fuction

*the output of the products list*
 ```
    ______
    NO.            NAME            PRICE
    ______
    1              ....              0$
    2              ....              0$

```




## Environment Variables

To run this project, the administrator will need to add the following environment variables to they software file

- ad the products that their supermarket sells from `ADMINISTRATOR_menu ()` first chose `Press 1 to CREATE PRODUCT`



## Used By

This project is used by the following companies:

- Administrators in supermarkets
- Supermarket customers

## Run Locally

Clone the project

[![The code link](https://img.shields.io/badge/Link-The_Code-blue.svg)](https://onlinegdb.com/woP_WxgPI)
```
https://onlinegdb.com/woP_WxgPI
```
 
the code 

```c++
// ECE103L- TERM PROJECT.
// Supermarket management system.
// Done by Shefaa, Ruba, and Elaf.
// Effat university
// The instructor is: Saeed Qaiser.





#include <iostream> // call header

using namespace std;

// Declarations

void ADMINISTRATOR_menu ();
void show_PRODUCT_list (string* , float*);


string* get_PRODUCT() // Body of function
{
    static string product[30] = {};
    return product;
}

float* get_PRICR()
{
    static float price[30]={};
    return price;
}


int main () // main function
{
  int option, product_No=0,product_quantity=0, n=0,i=1,No[30], qu[30];
  string* PRODUCT = get_PRODUCT();
  float* PRICE = get_PRICR();
  char y_n,pick_delivery;
  float sum = 0;

  cout << "\n______"; // show the options available in the system
  cout << "\n 1. CUSTOMER";
  cout << "\n 2. ADMINISTRATOR";
  cout << "\n 3. EXIT";
  cout << "\n______";

  cout << "\n Option: ";
  cin >> option;

  switch (option) // switch case fr the entered requirements
    {
    case 1:

           show_PRODUCT_list(PRODUCT,PRICE);
           cout << "\nWe have limited products of 30, please choose from this range.";
           cout << "\n~~~~~~~";
           cout << "\nYour order is: ";
           cout << "\n~~~~~~~";
           do {
               n++;
               cout<<"\n\nEnter The Product #: ";
               cin>> product_No;
               if (product_No <=30)
              {
                  cout<<"\nQuantity: ";
                  cin>>product_quantity;

                  No[n] = {(product_No)};
                  qu[n] = {product_quantity};
                  cout<<"\nDo You Want To Order Another Product ? (y/n)";
                  cin>> y_n;


              }
              else {cout<<endl<<endl<<"\tThe product_number is out of range";}

           }
           while(y_n=='y' || y_n=='Y'); // condition if the user's answer is yes

           cout<<"\nDo You Want To pick it up or to be delivered ? (pick/delivery)";
                  cin>> pick_delivery;
           cout<<"\n\nThank You...\n\n\n";


           cout << "\n~~~~~~~";
           cout << "\n___ invoice ___";
           cout << "\n_______";
           cout<<"\nPr No.    Pr Name\t   Quantity\t Price\t\tTotal Amount\n";
           cout << "\n_______";
           for(i; i <= n; ++i ){
               cout <<"\n  "<<i<< "\t    "<<PRODUCT[No[i]]<<"\t\t     "<<qu[i]<<"\t\t  "<<PRICE[No[i]]<<"$\t\t "<<qu[i]*PRICE[No[i]]<<"$\n";
               sum +=qu[i]*PRICE[No[i]];
           }
           cout << "\n\n\t\tTotal : "<< sum<< "$";

      break;

    case 2:
           ADMINISTRATOR_menu ();
      break;

    case 3:
      cout << "\n\n\n~~~~~~\n";
      cout << "\n\t\tGood Bye!";
      cout << "\n~~~~~~\n";
      break;

    default: main ();
    }
}

void ADMINISTRATOR_menu ()
{
    string* PRODUCT = get_PRODUCT();
    float* PRICE = get_PRICR();
    int option_adm, product_number;
    string product_name;
    float product_price;
    char y_n;

    cout << "\n\n\n\tADMINISTRATOR MENU\n";
    cout<<"\n______";
	cout<<"\n Press 1 to CREATE PRODUCT";
	cout<<"\n Press 2 to DISPLAY ALL PRODUCTS";
	cout<<"\n Press 3 to QUERY ";
	cout<<"\n Press 4 to MODIFY PRODUCT";
	cout<<"\n Press 5 to DELETE PRODUCT";
	cout<<"\n Press 6 to GO BACK TO MAIN MENU";
	cout<<"\n______";

	cout<<"\n\n  Option: ";
	cin>> option_adm;

	switch(option_adm){ // swith case to follow the user's answer for the menu

       case 1:
              cout<<"\nPlease Enter The Product Number: ";
              cin>>product_number;
              if (product_number >=1 || product_number <=30) // condition to limit the product number
              {
                  cout<<"\nPlease Enter The Name of The Product: ";
                  cin >> product_name;
                  PRODUCT[product_number-1] = product_name;
                  cout<<"\nPlease Enter The Price of The Product: ";
                  cin>>product_price;
                  PRICE[product_number-1] = product_price;
                  cout<<"\n\t Record Successfully Updated...";
              }
              else {cout<<"\n\n\tThe product_number is out of range";}
              ADMINISTRATOR_menu (); // to go to the start of this menu
       break;

       case 2:
              show_PRODUCT_list(PRODUCT,PRICE);
              ADMINISTRATOR_menu ();
       break;

       case 3:
               cout<<"\nPlease Enter The Product Number: ";
              cin>>product_number;
              if (product_number >=1 || product_number <=30)
              {
                  cout<<"\nThe Product Number: "<< product_number;
                  cout<<"\nThe Product Name : "<< PRODUCT[product_number-1];
                  cout<<"\nThe Product Price : "<< PRICE[product_number-1];

              }
              else {cout<<endl<<endl<<"\tThe product_number is out of range";}
              ADMINISTRATOR_menu ();
       break;

       case 4:
              cout<<"\nPlease Enter The Product Number: ";
              cin>>product_number;
              if (product_number >=1 || product_number <=30)
              {
                  cout<<"\nThe Product Number: "<< product_number;
                  cout<<"\nThe Product Name : "<< PRODUCT[product_number-1];
                  cout<<"\nThe Product Price : "<< PRICE[product_number-1];


                  cout<<"\nPlease Enter The New Number: ";
                  cin>>product_number;

                  cout<<"\nPlease Enter The New Name : ";
                  cin >> product_name;
                  PRODUCT[product_number-1] = product_name;
                  cout<<"\nPlease Enter The New Price : ";
                  cin>>product_price;
                  PRICE[product_number-1] = product_price;
                  cout<<"\n\n\t Record Successfully Updated...";}

              else {cout<<"\n\n\tThe product_number is out of range";}
              ADMINISTRATOR_menu ();
       break;

       case 5:
              cout<<"\nPlease Enter The Product Number: ";
              cin>>product_number;
              if (product_number >=1 || product_number <=30)
              {
                   cout<<"\nThe Product Number: "<< product_number;
                  cout<<"\nThe Product Name : "<< PRODUCT[product_number-1];
                  cout<<"\nThe Product Price : "<< PRICE[product_number-1];

                   cout<<"\nDo do want to continue delete this Product ? (y/n)";
                   cin >> y_n;

                   if (y_n == 'y')
                   {
                       PRODUCT[product_number-1] = ' ';
                       PRICE[product_number-1] = 0;
                       cout<<endl<<endl<<"\t Record Successfully Updated...";

                   }
              }

                  else if (y_n == 'n')
                  {
                      ADMINISTRATOR_menu (); // to go back to the first menu

                  }
              else {cout<<endl<<endl<<"\t the product_number is out of range";}

       break;

       case 6:
              main ();
       break;

       default : ADMINISTRATOR_menu (); // to go back to the first menu

	}
}


void show_PRODUCT_list (string* pro , float* pri) // body of the function
{

    cout << "\n\n\t     Product MENU\n\n";
    cout << "______\n";
    cout << " NO.\t\tNAME\t\tPRICE\n";
    cout << "______\n";
    for (int i = 0; i < 30; i++)
    cout <<" "<< i+1 << "\t\t" << pro[i] << "\t\t" << pri[i] << "$\n";
}


```


## Programmers

- Ruba Khawfani
- Shefaa SHalabi
- Elaf Shamsan
