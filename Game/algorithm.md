# Algorithm

1. Define a module named deposit() to get the user input that gets the deposit from the user with basic constraints to obtain a valid value.

2. Declare a global variable named **MAX_LINES** and define another method named **get_number_of_lines()** to get the input of no.of lines, so that the amount that gets involved in the bet gets multiplied with this input.

3. Declare 2 global variables named **MAX_BET AND MIN_BET** Define another method named **get_bet()** to get the input of amount which the user is going to bet on each line with necessary constraints.

4. Now define a **main()** method to call the above functions to process the fundamental inputs of the game.

5. To run the slot machine Import a module named **random**, because we need to generate the slot machine values in a random manner.

6. A slot machine with a **3*3 slots** lines is going to be created, if we get 3 same values in a row then **You win!** is the concept that is going to be implemented.

   6.1 Declare global variables named **ROWS , COLS** with a value of **3.**

   6.2 Specify the number of symbols. Do this with a help of a **dictionary** datatype as below,

      symbol_count ={
   
              "*" : 2,
   
              "&" : 4,
   
              "^" : 6,
   
              "@" : 8
   
          }

     6.3 define a method **get_slot_machine_spin(rows,cols,symbols)** , where we generate what symbols are going to be in each column    
        based on the frequency we have. For each column symbols will be randomly generated is the core idea of this method.

     6.a Easiest way to randomly select the symbols for each column is by creating a **list** , that contains all of the different                  values we possibly could select from.

     6.b Now we can choose and value, and once it's chosen it's removed from the list and then we choose again.

                all_symbols = []
   
                # a and 2 - sym, symcount
   
                for symbol,symbol_count in symbols.items():
   
                    for _ in range(symbol_count):
   
                        all_symbols.append(symbol)
   
            
                columns = []
   
                for col in range(cols):
   
                    column = []
   
                    current_symbols = all_symbols[:]
   
                    for row in range(rows):
   
                        value =  random.choice(current_symbols)
   
                        current_symbols.remove(value)
   
                        column.append(value)
   
            
                    columns.append(column)

            
                return columns

   6.4 Now to print the above symbol selection in a presentable way create a method named **print_slot_machine()**

         def print_slot_machine(columns):

          #Transpose of a matrix
   
          for row in range(len(columns[0])):
   
           for i,column in enumerate(columns):
   
               if i != len(columns) -1:
   
                   print(column[row],end=" | ")
   
               else:
   
                   print(column[row],end="")
   
           print()

    6.5 now create a method named **check_winings(columns, lines, bet, values)** and define the logic to check whether the symbols looks         same . Declare the values of the symbols,

               symbol_values ={
            
                      "*" : 5,
            
                      "&" : 4,
            
                      "^" : 3,
            
                      "@" : 2
            
                  }
         
             def check_winnings(columns,lines,bet,values):
            
             winnings = 0
            
             winning_lines = []
            
         
             for line in range(lines):
            
                 symbol =  columns[0][line]
            
                 for column in columns:
            
                     symbol_to_check = column[line]
            
                     if symbol != symbol_to_check:
            
                         break
            
                 else:
            
                     winnings += values[symbol] * bet
            
         
             return winnings,winning_lines


 7. Define a method named **spin()** to work on the balance with deposit if we win or lose with respective results!

             def spin(balance):
    
             lines = get_nol()
    
         
             # check if there is sufficient deposit for bet
    
             while True:
    
                 bet = get_bet()
         
                 total_bet = bet * lines
         
                 if total_bet > balance:
    
                     print(f"You dont have the sufficient bet amount, as your current balance is only ${balance}")
    
                 else:
    
                     break
         
             print(f"You are betting ${bet} on {lines} lines. Total Bet = ${total_bet}")
         
             slots = get_slot_machine_spin(ROWS, COLS, symbol_count)
         
             print_slot_machine(slots)
         
             winnings, winning_lines = check_winnings(slots, lines, bet, symbol_values)
         
             print(f"You won ${winnings}.")
    
             print(f"You won on lines :", *winning_lines)
         
             return winnings - total_bet

 
 
 8. Now call the methods inside **main()**,

          balance = deposit()
    
           while True:
    
           print(f"Curent balance is ${balance}")
    
           answer = input("Press enter to play (q to quit).")
    
           if answer == "q":
    
               break
    
           balance += spin(balance)

   
           print(f"You left with ${balance}")






             

   
 
