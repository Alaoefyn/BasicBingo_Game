// 1-Library Declaration
#include <iostream>
#include <iomanip>
#include <cstdlib>
#include <ctime>

using namespace std;

// 2-Function Prototypes
bool ControllingForCinko(int [][15], int, int, int []);

void CreateCards(int [][15], int);

void GiveTheCards(int [], int [][15], int [][15], int , int []);

void NumericalCheckpoint(int [], int [][15], int, int, int []);

void DrawingNumbers(int [], int);

void WhoIsTheWinner(int [], int);

void ExchangePoint(int *, int *);

void CardsShown(int [][15], int);

// 3-Main Function
int main()
{
    int tombalaCards[10][15], playerNumber=0;

    CreateCards(tombalaCards, 10);
    //Preaparing the main game cards
    
    cout << endl;
    while (playerNumber<2 || playerNumber > 5)
    //Since the game is playing with min2,max 5 players,if user writes numbers under 2 or above 5,the code will keep asking give numbers between 2 and 5 including 2 and 5.
	{
        cout << "Please type number of players on game (On tombala game; minimum 2,maximum 5 player can play.): ";
        cin >> playerNumber;
    }

    //Giving random player numbers for Players.
    int playerCards[playerNumber][15];
    int playerCardIndex[playerNumber];
    int status[playerNumber];
    int finalStatus[playerNumber];

    cout << endl;
    GiveTheCards(playerCardIndex, tombalaCards, playerCards, playerNumber, status);

    //Drawing the tombala numbers
    int drawnNumbers[90];
    DrawingNumbers(drawnNumbers, 90);


    //Checking the drawning numbers and cards are matching or not
    NumericalCheckpoint(drawnNumbers, playerCards, 90, playerNumber, status);

    for (int i=0; i<playerNumber; i++)
    {
        finalStatus[i] = 0;
        finalStatus[i] += status[i];
    }

    for (int i=0; i<2; i++)
    {
        CreateCards(tombalaCards, 10);
        GiveTheCards(playerCardIndex, tombalaCards, playerCards, playerNumber, status);
        DrawingNumbers(drawnNumbers, 90);
        NumericalCheckpoint(drawnNumbers, playerCards, 90, playerNumber, status);

        for (int j=0; j<playerNumber; ++j) {
            finalStatus[j] += status[j];
        }
    }

    WhoIsTheWinner(finalStatus, playerNumber);

    return 0;
}

//4-Function Definitions
void ExchangePoint(int *a, int *b)
{
    int tmp = *a;
    *a = *b;
    *b = tmp;
}

void CreateCards(int arr[][15], int totalCards)
{
    //Creating the Tombala cards
    cout << "Preparing tombala cards..." << "\n\n";

    int numbers[90];
    for (int i=0; i<90; i++)
    {
        numbers[i] = i+1;
    }

    for (int i=0; i<totalCards; i++)
    {
        cout << "Card number " << i << ": ";
        // I prefered NULL from old edition style.
        srand(time(NULL)+rand()%200);

        // Swapping from the beginning and continue one by one.
        for (int i = 90 - 1; i > 0; i--) {

            // Here picking a random index from 0 to i
            int j = rand() % (i + 1);

            ExchangePoint(&numbers[i], &numbers[j]);
        }
        for (int j=0; j<15; ++j)
        {
            arr[i][j] = numbers[j];
            cout << setw(3) << arr[i][j] << ' ';
        }
        cout << endl;
    }
}



void GiveTheCards(int index[], int cards[][15], int playCards[][15], int players, int status[])
//Giving the randomly choosed card numbers to players
{
    cout << "Selected card numerics for players:" << endl;   //On pdf,normally says "Card numbers selected for players" but i prefered this form.
    for (int i=0; i<players; i++)
    {
        index[i] = rand()%9;
        cout << index[i] << ' ';
        status[i] = 0;
    }


    //Here the card is assigned to the player and printed
    cout << "\n\n";
    for (int i=0; i<players; i++)
    {
        cout << "Player " << i << "'s tombala card: ";
        for (int j=0; j<15; ++j)
        {
            playCards[i][j] = cards[index[i]][j];
            cout << setw(3) << playCards[i][j] << ' ';
        }
        cout << endl;
    }
}


void DrawingNumbers(int arr[], int N)
//Drawing the 90 numbers one by one in a random order
{
//We have 90-member array.Assigning values to an array of 90 elements


//Printing all 90 numbers drawn on the screen

    cout << "Numbers Drawn:" << endl;
    for (int i=0; i<N; i++)
    {
        arr[i] = i+1;
    }

    for (int i = 0; i<N; i++)
    {
        int j = i + rand() % (N - i);
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
        if (i%10==0 && i!=0) {
            cout << endl;
        }
        cout << setw(3) << arr[i] << ' ';
    }
    cout << "\n\n";
}


//Printing the player cards
void CardsShown(int cards[][15], int players)
{
    int i, j;
    for (i=0; i<players; i++)
    {
        for (j=0; j<15; ++j)
        {
            cout << setw(3) << cards[i][j] << ' ';
        }
        cout << endl;
    }
    cout << endl;
}

bool ControllingForCinko(int card[][15], int player, int totalPlayers, int status[])
//Controlling for is someone  maded a 'Çinko' or not
{
    int hit = 0;

    bool isDone = false;

    for (int i=0; i<15; i++)
    {
        if (card[player][i] == -1)
        {
            hit += 1;
        }
    }
    if (hit == 5 && status[player] == 0)
    {
    	//Declaring first,second cinko winners and tombala winners on periods. 
        cout << "Winner of the first 'Cinko' is Player " << player << endl;
        CardsShown(card, totalPlayers);
        status[player] += 5;        
    }
    if (hit == 10 && status[player] == 5)
    {
        cout << "Winner of the second 'Cinko' is Player " << player << endl;
        CardsShown(card, totalPlayers);
        status[player] += 10;
    }
    if (hit == 15 && status[player] == 15)
    {
        cout << "Winner of the Tombala is Player " << player << endl;
        CardsShown(card, totalPlayers);
        status[player] += 15;
        isDone = true;
    }

    return isDone;
}




void NumericalCheckpoint(int numbers[], int cards[][15], int intNum, int cardNum, int status[])
//Here, all numbers are examined and evaluated.
//Also controlling the all numbers on one card each and checking them.
//As all the numbers are examined, when it comes to 'Cinko' for short, it stops when it comes to 'Tombala' in general.

{
    for (int i=0; i<intNum; i++) {

        for (int j=0; j<cardNum; ++j)
        {
            int hitNumber=0;
            for (int k=0; k<15; ++k)
            {
                if (cards[j][k] == numbers[i])
                {
                    cards[j][k] = -1;
                }
                if (cards[j][k] == -1)
                {
                    hitNumber = hitNumber + 1;
                    if (hitNumber%5==0)
                    {
                        if (ControllingForCinko(cards, j, cardNum, status))
                        {
                            return;
                        }
                    }
                }
            }
        }
    }
}



void WhoIsTheWinner(int res[], int N)
//Finding the winner by checking last points and declaring the winner of the game.
{
    int max = res[0], player = 0, i;
    for (i = 0; i<N; i++)
    {
        cout << "Player " << i << ": " << res[i] << "points." << endl;
        if (max < res[i])
        {
            player = i;
            max = res[i];
        }
    }
    cout << "Congratulations! Winner of the game is Player " << player << endl;
}
