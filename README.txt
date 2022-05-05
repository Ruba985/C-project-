
# Supermarket Management System Software using C++ 

this program 


## Table of Contents 

1. [API Reference](#API_Reference)
2. [Technologies](#technologies)
3. [Installation](#installation)
4. [Collaboration](#collaboration)
5. [FAQs](#faqs)
6. [Programmers](#Programmers)
## API Reference

this program has four functions `main()`, `CUSTOMER_menu ()`,
 `ADMINISTRATOR_menu ()` and 
`show_PRODUCT_list (string* , float*)`

#### **main function**

- the main fuction asks the user to specify whether they are `CUSTOMER` or `ADMINISTRATOR` or they wants to `EXIT` the program

*the output of main fuction*
```
__________________________________________
1. CUSTOMER
2. ADMINISTRATOR
3. EXIT
__________________________________________
Option: 
```
- here beside the word `option: ` the user should enter a number for choose from the options numbers above 

    * if the usre choose `CUSTOMER` opction, it will show all the prodects that the supermarket has and their prices as a menu from the fuction `show_PRODUCT_list`
    ```
    cout << "\n\n\t     Product MENU\n\n";
    cout << "__________________________________________\n";
    cout << " NO.\t\tNAME\t\tPRICE\n";
    cout << "__________________________________________\n";
    for (int i = 0; i < 30; i++)
    ```
    then user can enter the number of the product that they want and the uantity


#### **CUSTOMER_menu**

#### **ADMINISTRATOR_menu**

#### **show_PRODUCT_list**



```http
  GET /api/items
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get item

```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch |

#### add(num1, num2)

Takes two numbers and returns the sum.

## Color Reference

| Color             | Hex                                                                |
| ----------------- | ------------------------------------------------------------------ |
| Example Color | ![#0a192f](https://via.placeholder.com/10/0a192f?text=+) #0a192f |
| Example Color | ![#f8f8f8](https://via.placeholder.com/10/f8f8f8?text=+) #f8f8f8 |
| Example Color | ![#00b48a](https://via.placeholder.com/10/00b48a?text=+) #00b48a |
| Example Color | ![#00d1a0](https://via.placeholder.com/10/00b48a?text=+) #00d1a0 |


## Contributing

Contributions are always welcome!

See `contributing.md` for ways to get started.

Please adhere to this project's `code of conduct`.


## Demo

Insert gif or link to demo


## Deployment

To deploy this project run

```bash
  npm run deploy
```


## Documentation

[Documentation](https://linktodocumentation)


## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

`API_KEY`

`ANOTHER_API_KEY`


## Used By

This project is used by the following companies:

- Company 1
- Company 2


## Running Tests

To run tests, run the following command

```c++
   run test
```


## Run Locally

Clone the project

[![The code link](https://img.shields.io/badge/Link-The_Code-blue.svg)](https://www.onlinegdb.com/jFJ34Wp87)

```bash
 https://onlinegdb.com/jFJ34Wp87
```


Start the server

```c++
#include <iostream>

using namespace std;

void CUSTOMER_menu ();
void ADMINISTRATOR_menu ();
void show_PRODUCT_list (string* , float*);


string* get_PRODUCT()
{
    static string product[30] = {"a","b","c","d","e","f","g","h"};
    return product;
}

float* get_PRICR()
{
    static float price[30]={1.1,2.2,3.3,4.4,5.5,6.6,7.7,8.8};
    return price;
}


int main ()
{
  int option, product_No=0,product_quantity=0, n=0,i=1,No[30], qu[30];
  string* PRODUCT = get_PRODUCT();
  float* PRICE = get_PRICR();
  char y_n;
  float sum = 0;
  
  cout << "\n________________";
  cout << "\n 1. CUSTOMER";
  cout << "\n 2. ADMINISTRATOR";
  cout << "\n 3. EXIT";
  cout << "\n________________";

  cout << "\n Option: ";
  cin >> option;

  switch (option)
    {
    case 1:
           show_PRODUCT_list(PRODUCT,PRICE);
           cout << "\n~~~~~~~~~~~~~~~~~";
           cout << "\nYour order ";
           cout << "\n~~~~~~~~~~~~~~~~~";
           do {
               n++;
               cout<<"\n\nEnter The Product #: ";
               cin>> product_No;
               if (product_No-1 <=30)
              {
                  cout<<"\nQuantity: ";
                  cin>>product_quantity;
                  
                  No[n] = {(product_No-1)};
                  qu[n] = {product_quantity};
                  cout<<"\nDo You Want To Order Another Product ? (y/n)";
                  cin>> y_n;
                  
              }
              else {cout<<endl<<endl<<"\tThe product_number is out of range";}
               
           }
           while(y_n=='y' || y_n=='Y');
           
           cout<<"\n\nThank You...\n\n\n";
           
           
           cout << "\n~~~~~~~~~~~~~~~~~";
           cout << "\n_______ invoice _______";
           cout << "\n_________________";
           cout<<"\nPr No. \tPr Name\t  Quantity\tPrice\tAmount\n";
           cout << "\n_________________";
           for(i; i <= n; ++i ){
               cout <<"\n  "<<i<< "\t  "<<PRODUCT[No[i]]<<"\t     "<<qu[i]<<"\t\t "<<PRICE[No[i]]<<"$\t "<<qu[i]*PRICE[No[i]]<<"$\n";
               sum +=qu[i]*PRICE[No[i]];
           }
           cout << "\n\n\t\tTotal : "<< sum<< "$";
       
      break;
      
    case 2:
           ADMINISTRATOR_menu ();
      break;

    case 3:
      cout << "\n\n\n~~~~~~~~~~~~~~~~\n";
      cout << "\n\t\tGood Bye!";
      cout << "\n~~~~~~~~~~~~~~~~\n";
      break;

    default: main ();
    }
}

void CUSTOMER_menu ()
{
    
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
    cout<<"\n________________";
	cout<<"\n Press 1 to CREATE PRODUCT";
	cout<<"\n Press 2 to DISPLAY ALL PRODUCTS";
	cout<<"\n Press 3 to QUERY ";
	cout<<"\n Press 4 to MODIFY PRODUCT";
	cout<<"\n Press 5 to DELETE PRODUCT";
	cout<<"\n Press 6 to GO BACK TO MAIN MENU";
	cout<<"\n________________";
 
	cout<<"\n\n  Option: ";
	cin>> option_adm;
	
	switch(option_adm){
       
       case 1:
              cout<<"\nPlease Enter The Product Number: ";
              cin>>product_number;
              if (product_number <=30)
              {
                  cout<<"\nPlease Enter The Name of The Product: ";
                  cin >> product_name;
                  PRODUCT[product_number] = product_name;
                  cout<<"\nPlease Enter The Price of The Product: ";
                  cin>>product_price;
                  PRICE[product_number] = product_price;
                  cout<<"\n\t Record Successfully Updated...";
              }
              else {cout<<"\n\n\tThe product_number is out of range";}
              ADMINISTRATOR_menu ();
       break;
      
       case 2:
              show_PRODUCT_list(PRODUCT,PRICE);
              ADMINISTRATOR_menu ();
       break;
      
       case 3:
               cout<<"\nPlease Enter The Product Number: ";
              cin>>product_number;
              if (product_number <=30)
              {
                  cout<<"\nThe Product Number: "<< product_number;
                  cout<<"\nThe Product Name : "<< PRODUCT[product_number];
                  cout<<"\nThe Product Price : "<< PRICE[product_number];
                  
              }
              else {cout<<endl<<endl<<"\tThe product_number is out of range";}
              ADMINISTRATOR_menu ();
       break;
       
       case 4:
              cout<<"\nPlease Enter The Product Number: ";
              cin>>product_number;
              if (product_number <=30)
              {
                  cout<<"\nThe Product Number: "<< product_number;
                  cout<<"\nThe Product Name : "<< PRODUCT[product_number];
                  cout<<"\nThe Product Price : "<< PRICE[product_number];
                  
                  
                  cout<<"\nPlease Enter The New Number: ";
                  cin>>product_number;
              
                  cout<<"\nPlease Enter The New Name : ";
                  cin >> product_name;
                  PRODUCT[product_number] = product_name;
                  cout<<"\nPlease Enter The New Price : ";
                  cin>>product_price;
                  PRICE[product_number] = product_price;
                  cout<<"\n\n\t Record Successfully Updated...";}
                  
              else {cout<<"\n\n\tThe product_number is out of range";}
              ADMINISTRATOR_menu ();
       break;
      
       case 5:
              cout<<"\nPlease Enter The Product Number: ";
              cin>>product_number;
              if (product_number <=30)
              {
                   cout<<"\nThe Product Number: "<< product_number;
                  cout<<"\nThe Product Name : "<< PRODUCT[product_number];
                  cout<<"\nThe Product Price : "<< PRICE[product_number];
                  
                   cout<<"\nDo do want to continue delete this Product ? (y/n)";
                   cin >> y_n;
                   
                   if (y_n == 'y')
                   {
                       PRODUCT[product_number] = ' ';
                       PRICE[product_number] = 0;
                       cout<<endl<<endl<<"\t Record Successfully Updated...";
                       
                   }
              }
                  
                  else if (y_n == 'n') 
                  {
                      ADMINISTRATOR_menu ();
                      
                  }
              else {cout<<endl<<endl<<"\t the product_number is out of range";}
              
       break;
      
       case 6:
              main ();
       break;
       
       default : ADMINISTRATOR_menu ();
      
	}
}


void show_PRODUCT_list (string* pro , float* pri)
{
    
    cout << "\n\n\t     Product MENU\n\n";
    cout << "______________\n";
    cout << " NO.\t\tNAME\t\tPRIC…
    }
```


## Programmers

- Ruba Khawfani
- Shefaa SHalabi
- Elaf Shamsan
## Installation

Install my-project with npm

```bash
  npm install my-project
  cd my-project
```
    
