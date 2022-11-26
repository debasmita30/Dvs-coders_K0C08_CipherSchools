# DVS-coders_K0C08_CipherSchools
#Quiz Game Using Python
import random
questions = [
    {
        "question": "India won 2022 T20 world cup",
        "all_answers": [True, False],
        "correct_answer": False
    },
    {
        "question": "England won 2022 T20 world cup",
        "all_answers": [True, False],
        "correct_answer": True
    },

    {
        "question": "Python is not a case-sensitive language",
        "all_answers": [True, False],
        "correct_answer": False
    },
    {
        "question": ".py is the extension of python",
        "all_answers": [True, False],
        "correct_answer": True
    },
    {
        "question": "4+3%5=8",
        "all_answers": [True, False],
        "correct_answer": False
    },
    {
        "question": "def is not a keyword in python",
        "all_answers": [True, False],
        "correct_answer": False
    },
    {
        "question": "eval is not a keyword in python",
        "all_answers": [True, False],
        "correct_answer": True
    },
    {
        "question": "Tony is the first name of  Iron Man",
        "all_answers": [True, False],
        "correct_answer": True
    },

    {
        "question": "Hulk is red in color",
        "all_answers": [True, False],
        "correct_answer": False
    },
]


instructions = [
    "1. There are 5 rounds",
    "2. Minimum 1 and maximum of 5 questions will be asked in each round"
]

all_possible_answer_choices = [1, 2]
score = 0

print("Game instructions: ")

for instruction in instructions:
    print(instruction)


while True:
    print("\nDo you want to play the game?Y/N")
    user_play_choice = input("Enter Y if yes and N if no: ")
    all_choices = ["Y", "y"]
    all_choices_no = ["N", "n"]
    if user_play_choice in all_choices:
        for i in range(5):
            number_of_questions_to_be_asked = random.randint(1, 5)
            print("\nROUND: " + str(i+1))
            print("Total questions in this round: " +
                  str(number_of_questions_to_be_asked) + "\n")

            for _ in range(number_of_questions_to_be_asked):
                current_question = random.randint(0, len(questions)-1)

                print()
                print(questions[current_question]["question"])
                for index, answer in enumerate(questions[current_question]["all_answers"]):
                    print(str(index+1) + "." + str(answer))
                print()

                user_answer = 0
                while user_answer not in all_possible_answer_choices:
                    user_answer = input(
                        "Enter correct answer number [1/2]: "
                    )
                    if (user_answer.isnumeric()):
                        user_answer = int(user_answer)
                    else:
                        print("Please enter numeric values")

                if questions[current_question]["all_answers"][user_answer-1] == questions[current_question]["correct_answer"]:
                    score = score + 1

        break
    elif user_play_choice in all_choices_no:
        break
    else:
        print("Please enter Y or N only")

print("\n\ncongratulation", "Your score is: " + str(score))
