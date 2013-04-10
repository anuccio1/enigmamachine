import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.GridLayout;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;

import javax.swing.JPanel;
import javax.swing.JTextArea;
import javax.swing.JTextField;
import javax.swing.JButton;
import javax.swing.JFrame;


/**
 * Keyboard class that extends the jframe and implements the keylistener
 * @author anuccio
 *
 */
public class Keyboard extends JFrame implements KeyListener{
	/**
	 * array of characters for each key
	 */
	private static final char[][] keys = { {'`','1','2','3','4','5','6','7','8','9','0','-','=','*'},
		{'!','Q','W','E','R','T','Y','U','I','O','P','[',']','\\'},
		{'@','A','S','D','F','G','H','J','K','L',';','\'','#'},
		{'$','Z','X','C','V','B','N','M', ',', '.','?','^'},
		{' ','<','v','>'}};

	/** each key has a button */
	private JButton[][] buttons=null;
	/** panel for each row */
	private JPanel[] panelrows;
	/** Panel for board */
	private JPanel panel;
	/**textfield where user types */
	private JTextArea textfield;
	/** Color object */
	private Color c;
	/** String of key */
	private String currentkey;

	/**
	 * Constructor that initializes the JFrame
	 */
	public Keyboard(){
		super("Enigma Machine");
		setLayout(new BorderLayout());					//borderlayout

		textfield = new JTextArea(20,15);
		textfield.addKeyListener(this);
		textfield.setFocusTraversalKeysEnabled(false);
		add(textfield,BorderLayout.NORTH);		//adds the textfield to the top of the frame


		buttons = new JButton[5][20];			//jbutton array for each key
		panel = new JPanel();
		panel.setLayout(new GridLayout(5,0));	//grid layout for the keys

		panelrows = new JPanel[5];

		panelrows[0] = new JPanel(new GridLayout(1,keys[0].length));
		panelrows[1] = new JPanel(new GridLayout(1,keys[1].length));
		panelrows[2] = new JPanel(new GridLayout(1,keys[2].length));
		panelrows[3] = new JPanel(new GridLayout(1,keys[3].length));
		panelrows[4] = new JPanel(new GridLayout(1,keys[4].length));

		for(int i=0;i<keys.length;i++){
			for(int j=0;j<keys[i].length; j++){
				currentkey = Character.toString(keys[i][j]);		//sets the action keys
				if (keys[i][j] == '*'){
					currentkey = "Backspace";
				}

				if (keys[i][j] == '!'){
					currentkey = "Tab";
				}

				if (keys[i][j] == '@'){
					currentkey = "Caps";
				}

				if (keys[i][j] == '#'){
					currentkey = "Enter";
				}
				if (keys[i][j] == '$'){
					currentkey = "Shift";
				}

				buttons[i][j] = new JButton(currentkey);
				c = buttons[i][j].getBackground();	//color of the key background

				panelrows[i].add(buttons[i][j]);
			}
			panel.add(panelrows[i]);

		}
		add(panel,BorderLayout.SOUTH);		//adds the keyboard to the bottom


	}

	/**
	 * Keypressed method that is a key listener
	 */
	@Override
	public void keyPressed(KeyEvent e) {
		char keypressed;
		keypressed = e.getKeyChar();
		keypressed = Character.toUpperCase(keypressed);

		for(int i=0;i<keys.length;i++){
			for(int j=0;j<keys[i].length; j++){
				if(keypressed == keys[i][j]){
					buttons[i][j].setBackground(Color.GREEN);				//sets the button to green when the key is typed

				}
			}
		}


	}
	/**
	 * Key Released sets the button background back to normal once the key is released
	 */
	@Override
	public void keyReleased(KeyEvent e) {

		char keypressed;
		keypressed = e.getKeyChar();
		keypressed = Character.toUpperCase(keypressed);
		for(int i=0;i<keys.length;i++){
			for(int j=0;j<keys[i].length; j++){
				if(keypressed == keys[i][j]){
					buttons[i][j].setBackground(c);

				}
			}
		}
	}

	@Override
	public void keyTyped(KeyEvent e) {

	}//end constructor



}
