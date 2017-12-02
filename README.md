# interview
// Adapted and modified from https://introcs.cs.princeton.edu/java/14array/Deck.java.html
package interview;
import java.lang.Math;

 public class Card {
	 public static void main (String [] args) {
	 String [] suits = {"hearts" , "spades", "clubs", "diamonds"};
	 String [] facevalues = {"Ace", "2", "3", "4", "5", "6", "7", "8", "9", "10", "Jack", "Queen", "King"};	 
	
	// taking all the suits and facevalues to make 52 cards. 
	 int n = suits.length*facevalues.length;
		String [] deck = new String [n];
		for (int i=0; i<facevalues.length; i++) {
			for (int k =0; k< suits.length;k++) {
				 deck[suits.length*i + k] = facevalues[i] + " of " + suits[k];
			}
		}
	shuffle (n, deck);
	
	System.out.println("If the user wants call only one random card");
	dealOneCard(1,deck);
	
	shuffle (n, deck);
	
	System.out.println("If the user makes a 53rd call ");
	
	dealOneCard(53,deck);
	
	System.out.println("If the user make a call to show all 52 card in ramdom");
	
	dealOneCard (n,deck);
}
// card shuffling method 
public static void shuffle(int n, String[] deck) {
	for (int i = 0;i< n;i++) {
		int x = i + (int)( Math.random()*(n-i));
		String tem = deck [x];
		deck[x] = deck[i];
		deck [i] = tem;
		}
}
// printing the shuffled card method. 
public static void dealOneCard ( int n, String [] deck) {
	if (n<53) {
		for (int i = 0; i < n;i++) {
			System.out.println(deck[i]);
		}
	}else {
		System.out.println("There is only 52 card");
	}
}
}
