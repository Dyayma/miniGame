import java.util.Scanner;

public class LittleGame {
    
    public static void main(String[] args){
        Scanner scanner = new Scanner (System.in);
    
    System.out.print("Enter character name: ");
    String name = scanner.nextLine();

    String classType;
    while (true){
    System.out.print("Enter class type (Warrior/Mage/Archer): ");
    classType = scanner.nextLine();
    if (classType.equalsIgnoreCase("Warrior")||
        classType.equalsIgnoreCase("Mage")||
        classType.equalsIgnoreCase("Archer")){
        break; }
    else{
        System.out.println("Invalid Class Type. Please enter Warrior, Mage,or Archer only!");
    }
    }
 
    System.out.print("Enter Initial Level: ");
    int level = scanner.nextInt();
    scanner.nextLine();
    
    Character player = new Character( name, classType, level);
    
    player.displayInfo();

    System.out.print("Do you want to level up? (yes/no):");
    String levelUpChoice = scanner.nextLine();
    if (levelUpChoice.equalsIgnoreCase("yes")){
        player.levelUp();
        player.displayUpdatedInfo();
    }else if (levelUpChoice.equalsIgnoreCase("no"))
        System.out.println("Your level remains");
        player.displayInfo();
    }
}
}



public class Character {
    
    private String name;
    private String classType;
    private int level;
    
    Character (String name, String classType, int level){
        this.name = name;
        this.classType = classType;
        this.level = level;       
    }
    public String getName(){
        return name;
    }
    public String getClassType(){
        return classType;
    }
    public int getLevel(){
        return level;
    }
    public void levelUp(){
        level++;
        System.out.println("Congratulations! " + name + " has leveled up to Level " + level);
    }
    
    public void displayInfo(){
        System.out.println("Character Created!");
        System.out.println("Name: " + name);
        System.out.println("Class:" + classType);
        System.out.println("Level:" + level);
    }
    
    public void displayUpdatedInfo(){
        System.out.println("Updated Character Info:");
        System.out.println("Name: " + name);
        System.out.println("Class:" + classType);
        System.out.println("Level:" + level);    
}

    
}
