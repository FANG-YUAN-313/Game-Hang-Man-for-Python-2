import random

words = ["fang", "yuan", "ali", "lee"]
rand_word = random.choice(words)
lest_letter = ["_"] * len(rand_word)
print(" ".join(lest_letter))
oppor = 6
hang_man = ["""
 +--+
 |  |
 O  |
    |
    |
    |
=====""","""
 +--+
 |  |
 O  |
 |  |
    |
    |
=====""","""
 +--+
 |  |
 O  |
/|  |
    |
    |
=====""","""
 +--+
 |  |
 O  |
/|\ |
    |
    |
=====""","""
 +--+
 |  |
 O  |
/|\ |
/   |
    |
=====""","""
 +--+
 |  |
 O  |
/|\ |
/ \ |
    |
====="""]
inte = 5
inte2 = 0
print("""
+--+
 | |
   |
   |
   |
   |
=====""")
while "_" in lest_letter and oppor > 0:
    if oppor == inte:
        print(hang_man[inte2])
        inte -= 1
        inte2 += 1
    guessed = input("Guess a letter: ").lower()
    if guessed not in rand_word:
        oppor -= 1
    for j in range(len(rand_word)):
        if rand_word[j] == guessed:
            lest_letter[j] = guessed
    
    print(" ".join(lest_letter))
    print(f"Your have {oppor} more tries",end="")
