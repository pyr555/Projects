/* Tells porgram we are using scanner class*/
import java.util.Scanner;

 class RupakhetiRyanAssignment5 {
  public static void main(String[] args) {
    /* Lets scanner class be used for input */
    Scanner scanner = new Scanner(System.in);
    
    /* Constants for prize wining */
    final double LM = 20.00;
    final double PM = 4.00;

    /* Generate a random number from 1 to 26 for powerball */
    int TicketN = 1 + (int) (Math.random() * 26) ;
    
    /* Generate a two random letters from A to Z for powerball */
    char randomChar1 = (char) ('A' + (int) (Math.random() * ('Z' - 'A' + 1)));
    char randomChar2 = (char) ('A' + (int) (Math.random() * ('Z' - 'A' + 1)));

  
    
    /* Flag that tells program if something is valid input */
    boolean isValid = true;

    /* Makes space in Code output */
    System.out.println("\n\n");

    /*Displays instructions */
    System.out.println("              Lottery Game                ");
    System.out.println("------------------------------------------");
    System.out.println("Enter 2 letters and a Powerball number");
    System.out.println("Match: All to win the jackpot");
    System.out.println("Match: One letter to win $20.00");
    System.out.println("Match: Powerball to win $4.00");
    System.out.println("------------------------------------------");

    /* Makes space in Code output */
    System.out.println("\n\n");

    /* Prompts user to put in 2 letters */ 
    System.out.print("Enter two letters from A to Z( YOU GET ONE TRY ): ");
    
    /* Stores as a string and converts to uppercase if neede */
    String Loption = scanner.nextLine().toUpperCase();
    
    /* If input string is longer than 2 chars it ends program and gives message that says so */
    if(Loption.length() != 2)
    {
      isValid = false;
      System.out.println("INVALID ENTRY. Next time make sure you only put in 2 letters from A to Z");
    /* Or if input not a letter form A to Z it ends program and gives message that says so */
    }else if((Loption.charAt(0) < 'A' && Loption.charAt(0) > 'Z') || (Loption.charAt(1) < 'A' || Loption.charAt(1) > 'Z')){
      isValid = false;
      System.out.println("INVALID ENTRY. Next time make sure you only put in 2 letters from A to Z");
    /* If the input goes then lets user prompt user for powerball number */
    }else{
      System.out.print("Enter Powerball number between 1 and 26: ");
      int Poption = scanner.nextInt();
    /* If input not a number from 1 to 26 then end porgram and say message that says so */ 
      if(Poption < 1 || Poption > 26){
        isValid = false;
        System.out.print(" INVALID ENTRY. Next time make sure you type in a number that is from 1 to 26");
    /* If input is valid then print the two seperate tickets */
      }else{
        System.out.println("\nCustomer Ticket");
        System.out.println(Loption.charAt(0) + " " + Loption.charAt(1) + " " + Poption);
        System.out.println("\n ");
        System.out.println("\nPowerball Ticket");
        System.out.println(randomChar1 + " " + randomChar2 + " " + TicketN);
    
    /* If any letter in the input ticket is same as generate win $20.00 */
        if((Loption.charAt(0) == randomChar1 || Loption.charAt(0) == randomChar2) && (Loption.charAt(1) == randomChar1 || Loption.charAt(1) == randomChar2) && Poption == TicketN){
          
          System.out.println(" You won the Jackpot");
    /* Or any letter in the input ticket is same as generate win $20.00 */
        }else if((Loption.charAt(0) == randomChar1 || Loption.charAt(1) == randomChar2 || Loption.charAt(1) == randomChar1 || Loption.charAt(0) == randomChar2) && Poption != TicketN){
           System.out.printf("You won $%.2f\n", LM);
    /* Or if the numbers are the same win $4.00 */
        }else if((Loption.charAt(0) != randomChar1 || Loption.charAt(0) != randomChar2) && (Loption.charAt(1) != randomChar1 || Loption.charAt(1) != randomChar2) && Poption == TicketN){
          System.out.printf("You won $%.2f\n", PM);
    /* If nothing mathces then you lose */
        } else if((Loption.charAt(0) != randomChar1 || Loption.charAt(1) != randomChar2 ) && (Loption.charAt(1) != randomChar1 || Loption.charAt(1) != randomChar2) && Poption != TicketN){
          System.out.println("\n ");
          System.out.print("You won nothing try again next time ");
          
        }

        scanner.close();
          
          
        
      }
      
    }
    
    
    
   
   
  }



} 

