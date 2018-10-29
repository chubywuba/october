#Code from web-site Python for beginners
#www.pythonforbeginners.com/code-snippets-source-code/game-hangman
#with modifications

import random
from sets import Set
import string
win_flag = False 
letturns = 10

#set a random mystery letter
string.letters
'qwertyuiopasdfghjklzxcvbnm'
random.choice(string.letters)
letter = random.choice(string.letters)

Lettersguessed = Set()

#welcoming the user
name = raw_input("What is your name? ")

print "Hello, " + name, "Time to play hangman!"

print "Start guessing..."

#ask the user how long they want their word to be
lettersto = raw_input("How long do you want the word to be, 4 and 10")

if lettersto =='4':
 awords = random.choice(['cool', 'moon', 'star','peck', 'alex'])

if lettersto == '5':
 awords = random.choice(['juicy', 'junks','zincy', 'fuzzy','whizz','zappy'])

if lettersto == '6':
 awords = random.choice(['denker','python','soccer', 'pazazz'])

if lettersto == '7':
 awords = random.choice(['pizzazz','zyzzyva','jacuzzi','jazzing'])

if lettersto == '8':
 awords = random.choice(['quizzing','zizzling','buzzwigs','buzzcuts'])

if lettersto == '9':
  word = random.choice(['blackjack','buzzwords','frizzling','scuzzball','puzzledly'])

if lettersto == '10':
  word = random.choice(['scuzzballs','dazzlingly','lumberjack','supplejack','mozzarella'] )

#creates an variable with an empty value
guesses = ''

#determine the number of turns
turns = 10

#Create a while loop

#check if the turns are more than zero
while turns > 0:     

    # make a counter that starts with zero
    failed = 0             

    # for every character in secret_word    
    for char in awords:      

    # see if the character is in the players guess
        if char in guesses:    
    
        # print then out the character
            print char,    

        else:
    
        # if not found, print a dashb
        
            print "_",     
       
        # and increase the failed counter with one
            failed += 1    

    # if failed is equal to zero

    # print You Won
    if failed == 0:        
      win_flag = True 
       # exit the script
      break              

    print


    # ask the user go guess a letter
    guess = raw_input("guess a letter:") 

    # set the players guess to guesses
    guesses += guess                    

    # if the guess is not found in the secret word
    if guess not in awords:  
 
     # turns counter decreases with 1 (now 9)
        turns -= 1        
 
    # print wrong
        print "Wrong"    
 
    # how many turns are left
        print "You have", + turns, 'more guesses' 
 
    if turns == 0:
      print 'Try again.'

    #check if letters have been guessed
    if guess in Lettersguessed:
     print 'Try guessing a new letter.'
     turns += 1

    else:
      Lettersguessed.add(guess)
  
 # If the turns the word has been guessed
if win_flag:
  print 'You guessed the mystery word, congradulations. Now guess the mystery letter or else you die.'
  while letturns > 0:
    guessranlet = raw_input ('Guess the mystery letter:')

    #check if player guessed the mystery letters
    if guessranlet == letter:
     print "You won!"
     #exit the script
     break

    else:
     print 'try again.'
     letturns -= 1
    
    if letturns == 0:
      print 'You Died.'

   
