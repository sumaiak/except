# except
task 1;
package task1;



import java.util.ArrayList;
import java.util.Iterator;

    public class Main {
        static ArrayList<customer> customers = new ArrayList();

        public Main() {
        }

        public static void main(String... args) {
            customers.add(new customer("sumaia", "kalash", "sumak", 1));
            customers.add(new customer("alex", "dahl", "alexd", 2));
            customers.add(new customer("sana", "kalash", "sanak", 3));
            customers.add(new customer("musa", "kalash", "musak", 4));
            customers.add(new customer("alexander", "rian", "aexrian", 5));
            customers.add(new customer("nadia", "julie", "nadiaj", 6));
            printCustomers();
        }

        static void printCustomers() {
            for(customer c : customers){
                System.out.println(c.toString());



            }





            }

        }
        -----------------------------------------------class customer
        package task1;

public class customer {
            private String firstName;
            private String lastName;
            private String userName;
            private int id;

            public customer(String firstName, String lastName, String username, int id) {
                this.firstName = firstName;
                this.lastName = lastName;
                this.userName = username;
                this.id = id;
            }

            public String getFirstName() {
                return this.firstName;
            }

            public int getId() {
                return this.id;
            }

            public String getLastName() {
                return this.lastName;
            }

            public String getUserName() {
                return this.userName;
            }

            public String toString() {
                String s = "fullname:" + this.firstName + " " + this.lastName + " ,username:" + this.userName + "  ,your id number:" + this.id;
                return s;
            }

        


--------------------------------------------------------------------------------------------



package task2;
import java.io.File;
import java.util.ArrayList;
import java.util.Scanner;

public class Cafe {

    public  ArrayList<String> coffeMenu = new ArrayList<>();

      public  File loadMenuData(){
        return new File("C:\\Users\\skdk1\\OneDrive\\Desktop\\java\\coffeee\\coffemenu");

    }


    }
------------------Main cafe------
package task2;

import java.io.FileNotFoundException;
import java.util.Scanner;

public class Main {


    public static void main(String[] args) {

        Cafe drinks = new Cafe();


        try {
            drinks.loadMenuData();

            Scanner scanner = new Scanner(drinks.loadMenuData());
            while (scanner.hasNext()) {
                drinks.coffeMenu.add(scanner.nextLine());
            }
        } catch (FileNotFoundException e) {

            System.out.println("File not found. Check path and filename");

        }
        drinks.loadMenuData();
        for (String drink : drinks.coffeMenu) {
            System.out.println(drink);

            {
            }
        }
    }
}
----------------------------------------------------------------------------------------------------------------------------------------------------
task 3;

Building 
package task3;

import java.util.ArrayList;

public class Building {


    private final ArrayList<Room>rooms;

    private   int numberOfBathrooms;
     private  int numberOfFloors;



    private  boolean isOfficeBuilding;



    public Building(ArrayList<Room>rooms, boolean isOfficeBuilding, int numberOfBathrooms, int numberOfFloors) {

        this.rooms = rooms;
        this.isOfficeBuilding = isOfficeBuilding;
        this.numberOfBathrooms = numberOfBathrooms;
        this .numberOfFloors = numberOfFloors ;
    }
    public int getNumberOfBathrooms() {
        return numberOfBathrooms;
    }

    public int getNumberOfFloors() {
        return numberOfFloors;
    }
    public boolean isOfficeBuilding() {
        return isOfficeBuilding;
    }
    public ArrayList<Room> getRooms() {
        return rooms;
    }
}
----------------------------------class room-------------------
package task3;

public class Room {
   private int numberOfDoors;
   private int numberOfLamps;
   private int numberOfWindows;
        public  Room(int numberOfDoors, int numberOfLamps, int numberOfWindows) {
        this.numberOfDoors = numberOfDoors;
        this.numberOfLamps = numberOfLamps;
        this.numberOfWindows = numberOfWindows;
    }



        public int getNumberOfDoors() {
            return numberOfDoors;
        }
         public int getNumberOfWindows() {
            return numberOfWindows;
    }


    public int getNumberOfLamps() {
        return numberOfLamps;
    }



    }
----------------------------------------Main/room/bulding
package task3;

import java.util.ArrayList;

public class Main {
    public static int countLampsInBuilding(Building buildings) {
        int totalLamps = 0;
        for (Room r : buildings.getRooms()) {
            totalLamps = totalLamps + r.getNumberOfLamps();
        }
        return totalLamps;
    }

    public boolean isNormal(Building x) {
        if (x.getNumberOfFloors() > x.getRooms().size()) {
            return true;
        } else {
            System.out.println("This is an odd building");
            return false;
        }
    }
        public static void main (String[]args){
            ArrayList<Room> room = new ArrayList<>();
            Room white = new Room(5, 3, 5);
            Room black = new Room(8, 4, 6);
            Room pink = new Room(7, 5, 3);
            room.add(white);
            room.add(black);
            room.add(pink);

            Building buildings = new Building(room,true,6 ,2);


        }
    }
    -----------------------------------------TASK5---------------------------
    @startuml
'https://plantuml.com/object-diagram




class Building

class Room


Main -- Building
Building-- Room

Building : - int numberOfBathroom
Building : - int numberOfFloors
Building : - boolean isOfficeBuilding
Building : - final ArrayList<Room>rooms
Building : + ArrayList<Room> rooms, int numberOfBathrooms, int numberOfFloors, boolean isOfficeBuilding
Building : + boolean getIsOfficeBuilding()
Building : + int getNumberOfBathrooms()
Building : + int getNumberOfFloors()
Building : + ArrayList<Room> getRooms()
Main : +  static int countLampsInBuilding(Building x)
Main : +  static boolean isNormal(Building x)
Main : + static void main(String[] args)

Room : +  Room(int numberOfDoors, int numberOfLamps, int numberOfWindows)
Room : +  int getNumberOfDoors()
Room : + int getNumberOfLamps()
Room : + int getNumberOfWindows()
Room : - int numberOfDoors
Room : - int numberOfLamps
Room : - int numberOfWindows
@enduml

