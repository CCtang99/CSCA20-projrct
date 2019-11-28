# CSCA20-projrct#
#A interesting game

def print_word(lst):
   print("".join(lst))

def modify_word(word, answer, letter):
   
   for i in range(len(word)):
      if answer[i] == letter:
         word[i] = letter
   
   

import random
word_list = ["apple","peach","grape","water","chain","melon","donut","jelly","candy","bacon"]
# first randomly pick the index of the word list above
word_index = random.randint(0,9)
# find the corresponding word
answer = word_list[word_index]
print(answer)
# testing
word = list("_" * len(answer))
# print_word(word)

art_list = ["  |\n","  O\n","/ ","| ","\\\n"," /"," \\"]
trials = 0
art_index = 1
while trials < len(answer) + 2 and word != list(answer):
   print_word(word)
   letter = input('enter a letter please:').lower()
   if not letter.isalpha():
      print('you should give a letter')
   elif letter in word:
      print('you already guest this word, try another')
   else:
      if letter in answer:
        modify_word(word, answer, letter)
      else:
        for j in range(art_index):
          print(art_list[j],end = "")
        art_index += 1
      trials += 1
   
if word == list(answer):
   print("Congradulation")
else:
   print("The correct answer is: " + answer)
