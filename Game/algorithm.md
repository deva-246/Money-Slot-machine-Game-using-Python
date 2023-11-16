# Algorithm

1. Define a module named deposit() to get the user input that gets the deposit from the user with basic constraints to obtain a valid value.

2. Declare a global variable named **MAX_LINES** and define another method named **get_number_of_lines()** to get the input of no.of lines, so that the amount that gets involved in the bet gets multiplied with this input.

3. Declare 2 global variables named **MAX_BET AND MIN_BET** Define another method named **get_bet()** to get the input of amount which the user is going to bet on each line with necessary constraints.

4. Now define a **main()** method to call the above functions to process the fundamental inputs of the game.

5. To run the slot machine Import a module named **random**, because we need to generate the slot machine values in a random manner.

6. A slot machine with a **3*3 slots** lines is going to be created, if we get 3 same values in a row then **You win!** is the concept that is going to be implemented.

   6.1 Declare global variables named **ROWS , COLS** with a value of **3.**

   6.2 Specify the number of symbols a row must hold. Do this with a help of a **dictionary** datatype as below,

   symbol_count ={
   
              "*" : 2,
   
              "&" : 4,
   
              "^" : 6,
   
              "@" : 8
   
          }

     6.3 define a method **get_slot_machine_spin(rows,cols,symbols)** , where we generate what symbols are going to be in each column     
         based on the frequency we have. For each column symbols will be randomly generated is the core idea of this method.

     6.4 

   
 
