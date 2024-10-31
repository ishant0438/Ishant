import random

# Display the options for the user
options = ["rock", "paper", "scissors"]

def get_computer_choice():
    # Randomly select choice for computer
    return random.choice(options)

def get_user_choice():
    # Get user's choice
    user_choice = input("Enter your choice (rock, paper, or scissors): ").lower()
    while user_choice not in options:
        print("Invalid choice. Please try again.")
        user_choice = input("Enter your choice (rock, paper, or scissors): ").lower()
    return user_choice

def determine_winner(user_choice, computer_choice):
    # Determine the winner based on the rules
    if user_choice == computer_choice:
        return "It's a tie!"
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "scissors" and computer_choice == "paper") or \
         (user_choice == "paper" and computer_choice == "rock"):
        return "You win!"
    else:
        return "Computer wins!"

def play_game():
    # Main game loop
    while True:
        print("\nRock, Paper, Scissors Game!")
        
        user_choice = get_user_choice()
        computer_choice = get_computer_choice()
        
        print(f"\nYou chose: {user_choice}")
        print(f"Computer chose: {computer_choice}")
        
        # Display the result
        result = determine_winner(user_choice, computer_choice)
        print(result)
        
        # Ask to play again
        play_again = input("Do you want to play again? (yes/no): ").lower()
        if play_again != 'yes':
            print("Thanks for playing! Goodbye!")
            break

# Start the game
play_game()
