import random

HANGMAN_STAGES = [
    """
    +---+
    |   |
        |
        |
        |
        |
=========
""",
    """
    +---+
    |   |
    O   |
        |
        |
        |
=========
""",
    """
    +---+
    |   |
    O   |
    |   |
        |
        |
=========
""",
    """
    +---+
    |   |
    O   |
   /|   |
        |
        |
=========
""",
    """
    +---+
    |   |
    O   |
   /|\  |
        |
        |
=========
""",
    """
    +---+
    |   |
    O   |
   /|\  |
   /    |
        |
=========
""",
    """
    +---+
    |   |
    O   |
   /|\  |
   / \  |
        |
=========
"""
]

def load_word_list():
    return ["apple", "banana", "orange", "grape", "mango", "cherry"]

def choose_secret_word(word_list):
    return random.choice(word_list)

def display_word(secret_word, guessed_letters):
    return ' '.join(letter if letter in guessed_letters else '_' for letter in secret_word)

def play_hangman():
    word_list = load_word_list()
    secret_word = choose_secret_word(word_list)
    max_attempts = 6
    remaining_attempts = max_attempts
    guessed_letters = set()

    print("Welcome to Hangman!")
    print("Try to guess the secret word.")
    print("You have", max_attempts, "attempts.")

    while remaining_attempts > 0:
        print("\nWord:", display_word(secret_word, guessed_letters))
        guess = input("Enter a letter: ").strip().lower()

        if len(guess) != 1 or not guess.isalpha():
            print("Invalid input! Please enter a single letter.")
            continue

        if guess in guessed_letters:
            print("You've already guessed this letter.")
            continue

        guessed_letters.add(guess)
        if guess in secret_word:
            print("Correct!")
            if all(letter in guessed_letters for letter in secret_word):
                print("Congratulations! You guessed the word:", secret_word)
                break
        else:
            remaining_attempts -= 1
            print("Incorrect! Remaining attempts:", remaining_attempts)
            print(HANGMAN_STAGES[max_attempts - remaining_attempts])

    else:
        print("Sorry, you've run out of attempts. The secret word was:", secret_word)

if __name__ == "__main__":
    play_hangman()
