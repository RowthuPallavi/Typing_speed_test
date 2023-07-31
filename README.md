# Typing_speed_test
Testing Typing Speed using python
import random
import time

def generate_random_sentence(words, num_words):
    return ' '.join(random.sample(words, num_words))

def calculate_typing_speed(start_time, end_time, sentence):
    words_per_minute = (len(sentence.split()) / (end_time - start_time)) * 60
    return words_per_minute

def main():
    # List of simple words to be used in the typing test
    sample_words = ["apple", "banana", "cat", "dog", "egg", "fish", "green", "happy", "ice"]

    print("Welcome to the Speed Typing Test!")
    input("Press Enter when you are ready to start...")

    # Generate a random sentence with 4 words for the typing test
    sentence = generate_random_sentence(sample_words, 4)
    print("Type the following sentence:")
    print(sentence)

    input("Press Enter to start typing...")

    start_time = time.time()

    user_input = input("Type the sentence here: ")

    end_time = time.time()

    if user_input == sentence:
        print("Congratulations! You typed the sentence correctly.")
        words_per_minute = calculate_typing_speed(start_time, end_time, sentence)
        print(f"Your typing speed: {words_per_minute:.2f} words per minute.")
    else:
        print("Oops! You made a mistake. Please try again.")

if __name__ == "__main__":
    main()
