# CSCA20-projrct#
#A interesting game
import random
word_list = ["apple","peach","grape","water","coffee","melon","donut","cheese","banana","orange"]
# first randomly pick the index of the word list above
word_index = random.randint(0,9)
# find the corresponding word
new_word = word_list[word_index]
print(new_word)
new_list = []
length = 0
for l in range(len(new_word)):
   new_list.append("0")
#ask user for the letter until the list is full 
while length < len(new_word):
   letter = input("enter a letter please: ")
   for i in range(len(new_word)):
     if new_word[i] == letter:
       new_list [i] = letter
       length += 1
# convert the new list into a string and print it out
new_string = ""
new_string = (new_string.join(new_list))
print(new_string)
