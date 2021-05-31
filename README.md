# Luck-Game
This project flips a coin between user and computer for a number of rounds to be played and records the score.

import random

def num_of_rounds():
    rounds = int(input("Please enter how many rounds you want to play: "))
    ##validate if its an integer!!!
    return rounds
    

def flip_coin():

    user_input = input("Enter space to flip the coin: ")
    print("")

    while True:
        if user_input != " ":
            user_input("Seriously how could you mess that up? Try agian, enter SPACE not the word space just press space button: ")
            print("")
        else:
            x = random.randint(1,2)
            if x == 1:
                side_up = "heads"
                print("Its heads. Point for you!")
                print("")
            else:
                side_up = "tails"
                print("Its tails. Computer gets 1 point!")
                print("")
            break
    return side_up

def round_winner(side_up, you, computer):
    if side_up == "heads":
        you += 1
    if side_up == "tails":
        computer += 1

    return you, computer

def compare_scores(you, computer):
    if you > computer:
        print("Congrats! You Win!")
    elif computer > you:
        print("Computer wins but it means nothing")
    elif you == computer:
        print("Its a tie but idc")

def print_scores(you, computer, rounds_played, rounds_total):
    print("Your score: " + str(you))
    print("Computer score: " + str(computer))
    
    rounds_left = rounds_total - rounds_played
    if rounds_left != 0:
        print(str(str(rounds_left) + " rounds out of " + str(rounds_total) + " left"))
        print("")


def main():

    print("Welcome to a simple shitty luck game because my original idea was taking too long and i feel sleepy")
    print("Coin will be flipped, you're heads i am tails lets see who wins")
    print("")

    answer = "yes"
    while answer == "yes":
            rounds_total = num_of_rounds()

            # starting score
            you = 0
            computer = 0

            rounds_played = 0
            while rounds_played < rounds_total:

                side_up = flip_coin()
                [you, computer] = round_winner(side_up, you, computer)
                rounds_played += 1
                print_scores(you, computer, rounds_played, rounds_total)
                
                
            compare_scores(you, computer)

            print("")
            answer = input("Play again? Enter yes or no: ")
            print("")
    
    print("Thanks for playing this stupid game! ok ghumaite gelam bye")

main()
