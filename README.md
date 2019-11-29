# CSCA20-projrct#
#An interesting game

#set the initial whether want to start a new game to yes as default
whether_play = "yes"
#if user respond yes, the new game will start 
while whether_play.lower() == "yes":
  #convert list to string in order to print it out
  def print_word(list):
    print("".join(list))

  #put letter in to corresponding blank if the entered letter is right
  def modify_word(word, answer, letter):
    #if the entered letter stand in couple blanks, fill them in corresponding places
    for i in range(len(word)):
        if answer[i] == letter:
          word[i] = letter

  import time
  import random

  print('-----------Welcome to our mini game!-----------')
  time.sleep(1)

  word_list = ["apple","peach","grape","water","chain","melon","donut","jelly","candy","bacon"]
  # first randomly pick the index of the word list above
  word_index = random.randint(0,9)
  # find the corresponding word
  answer = word_list[word_index]
  print(answer)
  # testing
  word = list("_" * len(answer))
  # print_word(word)

  #build the man image
  art_list = ["  |\n","  O\n","/ ","| ","\\\n"," /"," \\"]
  trials = 0
  art_index = 1

  #enter the loop
  while trials < len(answer) + 2 and word != list(answer):
    print_word(word)
    letter = input('enter a letter please:').lower()
    # check whether the user input is a letter
    if not letter.isalpha():
        print('you should give a letter')
    # check if the letter is already entered by user 
    elif letter in word:
        print('you already guest this word, try another')
    else:
        # if user input is in the correspondning word, call the function to arrange the letter into the correct position
        if letter in answer:
          modify_word(word, answer, letter)
        # else if the user input is not in the corresponding word, we will add a new sign to the hangman picture
        else:
          # the for loop ensures that the hangman will be properly drawed(i.e. the hands and body will be in the same line while the two legs are in the seperated line)
          for j in range(art_index):
            print(art_list[j],end ="")
          #the man was hanged gradually if user enter a wrong letter
          art_index += 1
        #check entered letter one by one
        trials += 1
        
  #check if the entered letter is right   
  if word == list(answer):
    print("Congratulation! You save the man:)")
  else:
    print("\nUh-oh...The man died:( \nThe correct answer is: " + answer)
  time.sleep(1)
  #at the end of the game, ask the user whether to start a new game, and the program will decide in the while loop 
  whether_play = input('play again? yes/no ')

