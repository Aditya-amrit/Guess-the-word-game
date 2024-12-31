# Guess-the-word-game
import random

Alp = ["apple", "huskky", "baboon"]
c = random.choice(Alp)
print("Word to guess:", c)
d = len(c)
word = []
for i in range(d):
    word += "_"
print(word)
end = False
life = 6

while not end and life > 0:
    a = input("Enter a letter: ").lower()
    if a in c:
        for position in range(d):
            if c[position] == a:
                word[position] = a
    else:
        life -= 1
        print(f"Wrong!! You have {life} lives left.")

    print("Current state of the word:", " ".join(word))

    if "_" not in word:
        end = True
        print("You won the game!!!")

if life == 0:
    print("Game over! you lost")
