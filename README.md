# guessthe_number
https://github.com/chwenhdotcom/guessthe_number
import random

def guess_number_game():
    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100.")
    secret_number = random.randint(1, 100)
    attempts = 0
    max_attempts = 40

    while attempts < max_attempts:
        print(f"You have {max_attempts - attempts} attempts left.")
        try:
            guess = int(input("Guess the number: "))
        except ValueError:
            print("Please enter a valid number.")
            continue
        
        attempts += 1
        
        if guess < secret_number:
            print("Too low! Try again.")
        elif guess > secret_number:
            print("Too high! Try again.")
        else:
            print(f"Congratulations! You guessed the number {secret_number} in {attempts} attempts!")
            break
    
    if attempts == max_attempts:
        print(f"Game over! The number was {secret_number}.")

if __name__ == "__main__":
    guess_number_game()
