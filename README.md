Number_game_with_clues
A mini game to guess a number. After each guess the user is given a clue 
     
     
     import random

     def clue_f(secret_number,guess) :
    if secret_number > guess :
       clue ="\noops! try a larger number"
    elif secret_number < guess:
       clue ="\noops! try a smaller number"
    else :
       clue ="Correct"
     #additional clues are added 
    if secret_number != 0 :
      if secret_number % 2 !=0 :
         clue += "\nIts ann odd number"
      elif secret_number % 5 ==0 :
         clue +="\nIts a multiple of 5"
      elif secret_number % 7 ==0 :
         clue +="\nIts a multiple of 7"
      elif secret_number % 8 ==0 :
         clue +="\nIts a multiple of 8"
      elif secret_number %  2==0 :
         clue += "\nIts ann even number"

    return clue

    def game_number():


    print("****Lets start the game****\n****Test your intitution****\nGuess the number ")         #different ranges are given indicating the difficulty level
    print ("***Select the range of number***")
    print ("*** A- 1-10 ****")
    print ("*** B- 1-50 ****")
    print ("*** C- 1-100 ****")

    range= (input ("Enter your range \n A or B or C : "))

    if range == 'A':
       max_n = 10 
       print ("Guess the number in between 1-10")
    elif range == 'B':
       max_n = 50 
       print ("Guess the number in between 1-50")
    elif range == 'C':
       max_n= 100
       print ("Guess the number in between 1-100")
        
    

    secret_number = random.randint(1, max_n)
    initial_score= 50  # given 5 attempts 
    attempts=0
    while True:
     try:
        guess = int(input("\nGuess the number : "))
        attempts += 1
        if guess == secret_number :
           print ("You have guessed right")
           print (f"you have guessed it right in {attempts} attempts")
           break

        else :
           initial_score -=10
           clue= clue_f(secret_number,guess)
           print("you have guessed it worng")
           print("let me give u a hint : \n",clue)


           if initial_score <=0 :
             print("game is finished")
             break
           
     except :
        print ("error")
    game_number()
