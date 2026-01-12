import java.util.Scanner;

public class ProjectApp {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        //I put variable to store the User's choice '
        int choice;

        // we used do while loop to continuous run the program unless user type "0"'
        do {
            System.out.println("\n--- MAIN MENU ---");
            System.out.println("1. Sequence ");
            System.out.println("2. Selection ");
            System.out.println("3. Looping ");
            System.out.println("0. Exit");
            System.out.print("Select an option: ");
            
            //  Getting the menu choice From  user
            choice = sc.nextInt();
            
        
            sc.nextLine(); 

            // we used switch case so the program won't run simultaneously and  what the user has chosen
            switch (choice) {
                case 1:
                    
                    System.out.println("Trip Calculator ");
                    
                    System.out.print("Enter Destination Name: ");
                    String destination = sc.nextLine();
                    // Float=  is specifically a 32-bit(4byte)
                    //I used float so it only shows2 decimal point unless double which needed to be precise that showsallthe numbers
                    System.out.print("Enter Distance (in Kilometers): ");
                    float distance = sc.nextFloat();

                    System.out.print("Enter Average Speed (km/h): ");
                    float speed = sc.nextFloat();

                   
                    // Formula: Time = Distance divided by Speed
                    float travelTime = distance / speed;

                    // I use the '+' sign to combine our labels with the values in the variables 
                    System.out.println(" TRAVEL DETAILS");
                    System.out.println("Destination: " + destination);
                    
                    System.out.printf(" Total Distance:        %.2f km%n", distance);
                    System.out.printf("Your speed :            %.2f km/h%n", speed);
                    
                    System.out.println("-----------------------");
                    
                    // Here, I used  %.2f so itlbe readablr (e.g., "2.50 hours" instead of "2.500000")
                    System.out.printf("Estimated Travel Time: %.2f hours%n", travelTime);
                    
                    System.out.println("-----------------------");
                    System.out.println(" Ingat po!");
                
                    break;//we used brake so the program won't continues to run

                case 2:
           
                    System.out.println("What is the password?");

                    String password = sc.nextLine();

                    //This is the password
                    if (password.equals("DCIT22PROJECT")) {
                      //itllbe showed if  password input is correct
                          System.out.println("Password accepted");
                    } else {
                       //The 'else' block runs ONLY if the 'if' condition above was FALSE
                       //and here below is the opposite 
                           System.out.println("Access Denied! Try again.");
                    }
               
                    break;

                case 3:
               
                    // : The flashlight starts at 100% battery
                    int batteryLife = 100;

                    System.out.println("The flashlight is ON. Battery: 100%");                                     
                    //it'll check if battery is not below or  equal to 0%
                   
                    while (batteryLife > 0) {
                        
                        System.out.print("\nHow many minutes will you use the light? ");

                        //the program will wait for another input if it has still battery 
                        int minutesUsed = sc.nextInt();

                        // every minutes of use ng flashlight minus ng batteryrpercent
                        //this code shows that every minute the flashlight used is minus into battery life
                        batteryLife = batteryLife - minutesUsed;

                        //it will show what happen and how many percent left is
                        if (batteryLife > 0) {
                            System.out.println("Battery is now at: " + batteryLife + "%");
                        }
                        
                        // repeat sa "while line"
                        //to see the new battery percentage 
                    }

                    // the program will end if the battery of the flashlight is at 0%
                    System.out.println("The battery is dead. It's dark now!");
                    
                    break;

                case 0:
                    
                    System.out.println("Exiting... Thank you po!");
                    break;

                default:
                    //  the program will run into error if the user pick numbers other than 0-3
                    System.out.println("Invalid choice! Please choose from 0-3.");
            }
        } while (choice != 0); //  the program will run until the user didn't pick the option "0"

        sc.close();
    }
}
