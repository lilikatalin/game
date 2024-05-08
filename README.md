import random

def intro():
    print("Welcome to Adventure Quest!")
    print("You find yourself in a mysterious land full of dangers and treasures.")

def choose_path():
    print("You stand at a crossroad.")
    print("There are two paths ahead. Which path will you choose? (1 or 2)")

    path = input("> ")

    if path == "1":
        print("You follow the path and encounter a fierce dragon!")
        encounter_dragon()
    elif path == "2":
        print("You take the other path and find a hidden treasure!")
        treasure()
    else:
        print("Invalid choice. Try again.")
        choose_path()

def encounter_dragon():
    print("The dragon stares at you with its fiery eyes.")
    print("What will you do? (1) Fight or (2) Flee?")

    choice = input("> ")

    if choice == "1":
        outcome = random.choice(["win", "lose"])
        if outcome == "win":
            print("You defeated the dragon and gained its treasure!")
            win_game()
        else:
            print("The dragon defeated you. Game over!")
            lose_game()
    elif choice == "2":
        print("You flee from the dragon.")
        choose_path()
    else:
        print("Invalid choice. Try again.")
        encounter_dragon()

def treasure():
    print("You found a chest full of gold and jewels!")
    print("You become rich beyond your wildest dreams.")
    win_game()

def win_game():
    print("Congratulations! You won the game.")

def lose_game():
    print("Game over. Better luck next time.")

def play_game():
    intro()
    choose_path()

if __name__ == "__main__":
    play_game()
