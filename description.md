## Explanation of the code

* At first, create two array functions to the products' names and their prices (for the products' names it will be string function and for the prices it will be a float function)

```c++
string* get_PRODUCT() // Body of function
{
    static string product[30] = {};
    return product;
}
```

```c++
float* get_PRICR()
{
    static float price[30]={};
    return price;
}

```

### in the main fuction 
1. #### Create some variables: 

```c++
int option, product_No=0,product_quantity=0, n=0,i=1,No[30], qu[30]; 
```
```c++
char y_n,pick_delivery;
float sum = 0;
```

2. #### Calling the array fucrions.
```c++
string* PRODUCT = get_PRODUCT();
float* PRICE = get_PRICR();
```

3. #### Print the options that user have and save what the user choose in `option ` variable
```c++
cout << "\n______"; // show the options available in the system
  cout << "\n 1. CUSTOMER";
  cout << "\n 2. ADMINISTRATOR";
  cout << "\n 3. EXIT";
  cout << "\n______";

  cout << "\n Option: ";
  cin >> option;
```

4. #### Using of a `switch` case to determine the user's choice from `option` as either a customer or an administrator, or to exit the application
```c++
switch (option) // switch case for the entered requirements
    {
    case 1: //for the customers
      break;

    case 2: // for the administrators
      break;

    case 3: //to exit from the program
      break;

    default: main ();
    }
}
```
5. #### implement the user's choice in `option` variable:
    * If the user entered number 1, it will print the menu of the products.
        
        **printing the products' menu is from other fuction(void fuction)*

        The function use `for loop`to print all the products' namse and prices from the array fucrions.
        ```c++
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

        Calling `show_PRODUCT_list` in the `main ()` to pint products' menu.
        ```c++
         switch (option) // switch case fr the entered requirements
             {
             case 1:
                    show_PRODUCT_list(PRODUCT,PRICE);
               break;
        ```
        Here the user adds the products that their will buy from the menu by specifying the product number and its quantity, determine delivery or not and at the end calculate and print the bill.
        ```c++
        switch (option) // switch case for the entered requirements
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
        ```
    * If the user entered number 2, it will go to other function :
        
        * Create new fuction called `ADMINISTRATOR_menu ()` for all administrators' options 
          ```c++
          void ADMINISTRATOR_menu ()
          ```
        * Calling the array fucrions.
          ```c++
          void ADMINISTRATOR_menu ()
          {
              string* PRODUCT = get_PRODUCT();
              float* PRICE = get_PRICR();
          }
          ```
        * Create some variables: 
          ```c++
           int option_adm, product_number;
           string product_name;
           float product_price;
           char y_n;
          ```
        * Print the options that user have and save what the user choose in `option_adm` variable
          ```c++
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
          ```
        * Using of a `switch` case to determine the user's choice what will thay do as administrator from `option_adm`.

           ```c++
           switch(option_adm){ // swith case to follow the user's answer for the menu

                 case 1: //for create a new prodect.
                   break;

                 case 2: //for uery about product.
                   break;

                 case 3: //for uery about product.    
                   break;

                 case 4: //for modify product.     
                   break;

                 case 5: //for delete product.
                   break;

                 case 6: //for go back to main function. 
                   break;

                 default : ADMINISTRATOR_menu (); // to go back to the menu

	          }
          }
          ```
        * implement the user's choice in `option_adm` variable.

    * If the user entered number 3, it will exit from the program.
    ```c++
    case 3:
      cout << "\n\n\n~~~~~~\n";
      cout << "\n\t\tGood Bye!";
      cout << "\n~~~~~~\n";
      break;

    ```
         
