# Color-Choice-Game-CCG- 

#importing needed modules for our project:
#import random variable

import random

#Declare computer_score and player_score as variable
#Show_colors_choices_to_user_to_choose and enter a color:
#print multiline instruction
#performstring concatenation of string


print("Winning Rules of the Color choice Game as follows: " + "\nEnter a number from one, two, five and match computer choice to Win the computer .")
computer_score = 0
player_score = 0

while True:
    print("red = 1 \n Yellow = 2 \n Orange = 3\n Green = 4 \nBlue = 5\n Take a turn: ")

    #take the input from user
    player_choice = int(input("User turn : "))

    #OR id the short-circuit operator if any one of the condition is true then it return True value

    #Looping until user enter invalid input
    while player_choice > 5 and player_choice < 1:
        player_choice = int(input("Enter valid input : "))

    #initialize value of choice_col variable corresponding to the player_choice value
    if player_choice == 1:
        choice_col = 'red'
    elif player_choice == 2:
        choice_col = 'Yellow'
    elif player_choice == 3:
        choice_col = 'Orange'
    elif player_choice == 4:
        choice_col = 'Green'
    else:
        choice_col = 'Blue'

    #print user choice
    print("User color choice is: " + choice_col)
    print("\nNow its computer turn to choose a color .....")

    computer_choice = random.randint(1, 5)

    while computer_choice == player_choice:
        computer_choice = random.randint(1, 5)

    if computer_choice == 1:
        compu_choice_col = 'red'
    elif computer_choice == 2:
        compu_choice_col = 'Yellow'
    elif computer_choice == 3:
        compu_choice_col = 'Orange'
    elif computer_choice == 4:
        compu_choice_col = 'Green'
    else:
        compu_choice_col = 'Blue'

    print("Computer color choice is: " + compu_choice_col)
    #Condition for Winning
    if (choice_col == compu_choice_col):
        player_score += 1
        print("Player_Score: " + str(player_score))
        print("Computer_Score: " + str(computer_score))
    else:
        computer_score += 1
        print("Player_Score: " + str(player_score))
        print("Computer_Score: " + str(computer_score))

    print("Do you want to play again? (Y/N)")
    answer = input()

    #if user input n or N then condition is True
    if answer == 'n' or answer == 'N':
        break

if computer_score == player_score:
    print("Game is tied")
    print("\n Thanks for playinng")
elif computer_score < player_score:
    print("Player is Victorious")
    print("<== User Win ==>")
    print("\n Thanks for playing")
elif computer_score > player_score:
    print("\n<== Computer Win ==> ")
    print("\nPlayer is Defeated")
    print("\n Thanks for playing")
