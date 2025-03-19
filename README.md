# Rock-Paper-Scissors
import random

# Game choices
choices = {'r': 'Rock', 'p': 'Paper', 's': 'Scissors'}

# Get user-defined winning score
winning_score = int(input("Enter the points required to win the game: "))

# Initialize scores
user_score = 0
computer_score = 0

print("\nWelcome to Rock, Paper, Scissors!")
print("Enter 'r' for Rock, 'p' for Paper, 's' for Scissors")

while user_score < winning_score and computer_score < winning_score:
    user_choice = input("\nEnter your choice: ").lower()
    
    if user_choice not in choices:
        print("Invalid input! Please enter 'r', 'p', or 's'.")
        continue
    
    computer_choice = random.choice(list(choices.keys()))
    print(f"Computer chose: {choices[computer_choice]}")

    # Winning conditions
    if user_choice == computer_choice:
        print("It's a tie!")
    elif (user_choice == 'r' and computer_choice == 's') or \
         (user_choice == 's' and computer_choice == 'p') or \
         (user_choice == 'p' and computer_choice == 'r'):
        print("You win this round! 🎉")
        user_score += 1
    else:
        print("Computer wins this round! 😢")
        computer_score += 1

    # Display current score
    print(f"Score -> You: {user_score} | Computer: {computer_score}")

# Announce final winner
if user_score == winning_score:
    print("\n🎉 Congratulations! You won the game! 🏆")
else:
    print("\n😢 Computer won the game! Better luck next time!")

print("\nGame Over! Thanks for playing. 😊")
