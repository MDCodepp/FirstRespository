# FirstRespository
#include <iostream>
#include <ctime> 
#include <string>
#include <cstdlib>
#include <windows.h>
using namespace std;

int main()
{
    string player1;
    string player2;
    int dice1;
    int dice2;
    int key;
    int total1 = 0;
    int total2 = 0;
    

    // Player Names
    cout << "Enter player's one name:   ";
    cin >> player1;

    cout << "Enter player's two name:   ";
    cin >> player2;

    HANDLE screen = GetStdHandle(STD_OUTPUT_HANDLE);


    //Dice Numbers
    srand(time(0));

    dice1 = rand() % 20 + 1;
    dice2 = rand() % 20 + 1;
    total1 = dice1;
    total2 = dice2;

    cout << player1 << " rolled " << total1 << endl;
    cout << player2 << " rolled " << total2 << endl;

    //If Statements 
    if(total1 > total2)
    {
        cout << player1 << " is the winner. " << endl;
    }

    else if(total1 < total2)
    {
        cout << player2 << " is the winner. " << endl;
    }

    else if (total1 == 1 || total2 == 1)
    {
        for (int color = 0; color < 1; color++)
        {
        SetConsoleTextAttribute (screen, 12);
        cout << " Critial Failure" << endl;
        Sleep(290);
        }
    }

    else if(total1 == 20 || total2 == 20)
    {
        
        for(int color = 0; color < 1; color++)
        {
        SetConsoleTextAttribute (screen, 10);
        cout << " Critial Success" << endl;
        Sleep(290);
        }
    }

    else if(total1 == total2)
    {
        cout << "Evenly Matched" << endl;
    }





    SetConsoleTextAttribute(screen, 7);
    return 0;



    




    
    

}
