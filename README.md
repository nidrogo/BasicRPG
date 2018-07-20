# BasicRPG
Made In Eclipse
@ID Tech Camp, Macalester

import java.util.Scanner;
import java.util.Random;

public class ChallengeProblem2 
{
	static Scanner input = new Scanner (System.in);
	static Characters p1= new Characters( );
	static Characters p2= new Characters( );
	
	public static void main(String[] args) 
	{	
		
		Random generator1 = new Random();

		
		System.out.println("Input Health for Player 1 and Player 2!");		
		p1.health = input.nextInt();
		p2.health = input.nextInt();
		
		
		p1.attack = generator1.nextInt(50-5)+5;
		p2.attack = generator1.nextInt(50-5)+5;
	 
		while (true)
		{
			System.out.println("Let the match Begin!");
			System.out.println("Player 1 has " + p1.attack + " attack points");
			System.out.println("Player 2 has " + p2.attack + " attack points");
		
		while (p1.health>0 && p2.health>0)
		{
			p1.health=p1.health-p2.attack;
			p2.health=p2.health-p1.attack;
			System.out.println("P2 Attacks!  P1 has " + p1.health + " health remaining!");
			System.out.println("P1 Attacks!  P2 has " + p2.health + " health remaining!"); 
		}
		
		if(p1.health==p2.health)
		{
			System.out.println("TIE!");
		}
		
		if(p1.health>p2.health)
		{
			System.out.println("Player 1 Wins!");
		}
		
		if(p2.health>p1.health)
		{
			System.out.println("Player 2 Wins!");
		}
		
		shop ();
		}
		
	}
		
		public static void shop() 
			{
				
				System.out.println("Would You Like to Buy Stat Upgrades to Continue? \n1 - Yes\n2 - No");
				int playerChoice = input.nextInt();
				
				if(playerChoice == 2)
				{
				System.out.println("Game Over!");
				System.exit(0);
				}
					
				if(playerChoice == 1)
				{
				System.out.println("Upgrade Your Stats! \n1 - Upgrade Attack By 10 Points\n2 - Upgrade Health by 10 Points\n3 - Return to Game");
				playerChoice = input.nextInt();
				}
				
				if(playerChoice == 2)
				{
				p1.health+= 100+10;
				p2.health+=100;
				System.out.println("Player 1 has " + p1.health + "health!");
				}
				
				if(playerChoice == 1)
				{
				p1.health+=100;
				p2.health+=100;
				p1.attack+= 10;
				System.out.println("Player 1 has " + p1.attack + " attack!");
				}
				
				if(playerChoice == 3)
				{
				p1.health+=100;
				p1.health+=100;
				System.out.println("Returning to Game...");
				}
			}
		
}
