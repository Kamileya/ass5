#include <iostream>
#include <ctime>
#include <cstdlib>
#include <algorithm>
using namespace std;
class Environment {
public:
    Environment(){
        for(int i =0; i < 3 ;i++){
            for(int j = 0 ;j < 3 ;j++){
                board[i][j] = ' ';
            }
        }
    }
    char board[3][3];
    void drawboard();
    char checkwinner();
    bool checkturn(int y , int x);

};
class Player : public Environment{
public:
    void playwithhuman();
    void playwithbot();
};
bool Environment :: checkturn(int y , int x) {
    if(board[y][x] == ' '){
        return true;
    }
    else return false;
}
void Player ::playwithhuman() {
    int cnt = 0 , turn = 0;
    int x, y , y1 , x1;
    while(true){
        cout<<"Go!!!\n";
        cout<<"By Y axis | By X axis\n";
        cin>>y>>x;
        y1 = y-1;
        x1 = x-1;
        if(checkturn(y1 , x1)){
            if(turn%2 == 0){
                board[y1][x1] = 'X';
                turn++;
            }
            else {
                board[y1][x1] = '0';
                turn++;
            }
        }
        else cout<<"Not correct turn. Restart!!!\n";
        if(checkwinner() == 'X'){
            cout<<"Winner is "<<checkwinner()<<endl;
            break;
        }
        else if(checkwinner() == '0'){
            cout<<"Winner is "<<checkwinner()<<"\n";
            break;
        }
        drawboard();
    }

}
void Player ::playwithbot() {
    int cnt = 0 , turn = 0;
    int x, y , y1 , x1;
    srand(time(0));
    while(true){
        cout<<"Go!!!\n";
        drawboard();
        if(turn%2 == 0){
            cout<<"Human's turn!!!\n";
            cin>>y>>x;
            y1 = y-1;
            x1 = x-1;
        }
        else {
            cout<<"Bot's turn!!!\n";
            while(!(checkturn(y1 , x1)) ){
                y1 = rand()%3;
                x1 = rand()%3;
            }
        }
        if(checkturn(y1 , x1)){
            if(turn%2 == 0){
                board[y1][x1] = 'X';
                turn++;
            }
            else {
                board[y1][x1] = '0';
                turn++;
            }
        }
        else cout<<"Not correct turn. Choose the correct place!!!\n";
        if(checkwinner() == 'X'){
            cout<<"Winner is "<<checkwinner()<<endl;
            break;
        }
        else if(checkwinner() == '0'){
            cout<<"Winner is "<<checkwinner()<<"\n";
            break;
        }
    }
}
void Environment ::drawboard() {
    cout<<" "<<board[0][0]<<" | "<<board[0][1]<<" | "<<board[0][2]<<endl
        <<"---|---|---\n"
        <<" "<<board[1][0]<<" | "<<board[1][1]<<" | "<<board[1][2]<<endl
        <<"---|---|---\n"
        <<" "<<board[2][0]<<" | "<<board[2][1]<<" | "<<board[2][2]<<endl;
}
char Environment ::checkwinner() {
    char win = 'd';
    for(int i =0; i < 2 ; i++){
        if(board[i][0] != ' ' or board[0][i] != ' '){
            if(board[i][0] == board[i][1] and board[i][1] == board[i][2]){
                win = board[i][0];
            }
            else if(board[0][i] == board[1][i] and board[1][i] == board[2][i]){
                win = board[0][i];
            }
        }
    }
    if(board[0][0] != ' ' or board[0][2] != ' '){
        if(board[0][0] == board[1][1] and board[1][1] == board[2][2]){
            win = board[0][0];
        }
        if(board[0][2] == board[1][1] and board[1][1] == board[2][0]){
            win = board[0][2];
        }
    }
    return win;
}

int main() {
    Player player;

    int choice;
    while(choice != 4){
        cout<<"1.Player vs. Player\n"
            <<"2.Player vs. Bot\n"
            <<"3.Player vs. AdvBot\n"
            <<"4.Quit\n";
        cin>>choice;
        if(choice == 1){
            player.playwithhuman();
        }
        else if(choice == 2){
            player.playwithbot();
        }
        else if(choice == 3){

        }
        else {
            break;
        }

    }
}
