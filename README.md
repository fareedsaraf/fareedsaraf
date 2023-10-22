- 👋 Hi, I’m @fareedsaraf
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
fareedsaraf/fareedsaraf is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import java.util.Scanner; 
class Display
{
	Display(){}
	String name,nic;
	int phonenumber;
	char AccountType;
	private double balance;
	
	public void setbalance(double balance){
		this.balance=balance;
	}
	public double getbalance(){
		return balance;
	}
 
	Display(String name, String nic,int phonenumber,char AccountType)//double balance)
	{
		this.name=name;
		this.nic=nic;
		this.phonenumber=phonenumber;
		this.AccountType=AccountType;
		//this.balance=balance;
	}
}
class Wcard extends Display{
	int ch,pass,npass;
	double wamount,newBalance;
	char s;
	Scanner i=new Scanner(System.in);
 
	Wcard(){}
 
	Wcard(String name, String nic,int phonenumber,char AccountType){
		super(name,nic,phonenumber,AccountType);
	}
	void dis(){
		System.out.println("Enter your 4 Digit pin number: ");
		pass=i.nextInt();
		System.out.println("**********************");
		System.out.println("\n");
		System.out.println("1-Tamil");
		System.out.println("2-Englis");
		System.out.println("3-Sinhala");
		//System.out.println("\n");
		System.out.println("**********************");
		/*System.out.println("\n");
		System.out.println("1-Widhrawal");
		System.out.println("2-Check balance");
		System.out.println("3-Change Pin");
		System.out.println("**********************");*/
		
		do{
			System.out.println("\n");
			System.out.println("1-Widhrawal");
			System.out.println("2-Check balance");
			System.out.println("3-Change Pin");
			System.out.println("**********************");
			System.out.println("Enter a number. That which Way do you want to use");
			ch=i.nextInt();
			switch(ch){

				case 1: 
					System.out.println("Enter your widhrawal amount: ");
					wamount=i.nextDouble();
					if(getbalance()>wamount){
						System.out.println("Your widhrawal amount Succesfully completed");
						setbalance(getbalance()-wamount);
						System.out.println("Your balance is: "+getbalance());
					}
					else
						System.out.println("Insuffiction balance");
     
				break;
				case 2:
					System.out.println("Your balance is: "+getbalance());
     
				break;
				case 3:
					System.out.println("Enter your new 4 Digit PIN number: ");
					npass=i.nextInt();
					System.out.println("Re Enternter your 4 Digit PIN number: ");
					npass=i.nextInt();
					System.out.println("Your PIN number has been changed");
    
				break;
				default:
					System.out.println("Invalid number!");
    
    
			}
			System.out.println("Do you need to work another process");
			s=i.next().charAt(0);
		}
		while(s=='y');
			System.out.println("Invalid choise! , Take your card");
	}
}

/*class both extends Display{
 void wc(){}

 }*/
class w_notcard{
 
	String nic;
	int otp;
	double amount,balance;
	Scanner input=new Scanner(System.in);
	String[][] accdt={{"Saraf","200111600200","774039122","Saving"},{"rijas","200111400350","745253655","S"}};
	double[]salary={2000.00,62000.00};
	w_notcard(){}
	void wcard(){
		System.out.println("Enter NIC number: ");
		//choose=input.next();
		nic=input.next();
		//String[][] accdt={{"Saraf","200111600200","774039122","Saving"},{"rijas","200111400350","745253655","S"}};
		double[]salary={2000.00,62000.00};
   //nic=accdt[0][1];
		if(accdt[0][1].contains(nic)){
			//System.out.println("sent  OTP number to your registered phone number: "+accdt[0][2]);
			System.out.println("An OTP has been send to your phone "+accdt[0][2]);
			System.out.println("Enter OTP number");
			otp=input.nextInt();
			System.out.println("Enter amount");
			amount=input.nextDouble();
			
			if(salary[0]>amount){
				salary[0]=salary[0]-amount;
				System.out.println("your widhrawl succesfuly complete");
			}
			else 
				System.out.println("Insuffiction balance");
		}
		else if(accdt[1][1].contains(nic)){ 
			//System.out.println("sent  OTP number to your registered phone number: "+accdt[1][2]);
			System.out.println("An OTP has been send to your phone "+accdt[1][2]);
			System.out.println("Enter OTP number");
			otp=input.nextInt();
			System.out.println("Enter amount");
			amount=input.nextDouble();
			if(salary[1]>amount){
				salary[1]=salary[1]-amount;
				System.out.println("your widhrawl succesfuly complete");
			}
			else 
				System.out.println("Insuffiction balance");
		}
		else 
		{
			System.out.println("You Entered  NIC number is wrong");
		} 
	}
}
class m_banking extends w_notcard{
	m_banking(){}
	void mobile(){
		System.out.println("----- Welcome to Mobile Banking -----");
		System.out.println("            Hello "+accdt[0][0]);
	}
	//wcard();
	void wcard(){
		super.wcard();
		if(accdt[0][1].contains(nic)){
			System.out.println("Your current balance is: "+(salary[0]-amount));
		}else{
			System.out.println("Your current balance is: "+(salary[1]-amount));
		}
	}
}

class main{
	static int choose;
	static char select;
	public static void main(String[]arg){
  
	Scanner input=new Scanner (System.in);

	Display acc[]=new Display[]{
		new Display("Saraf","200111600200",774039122,'S'),
		new Display("rijas","200111400350",745253655,'S')
	};
	Display ac=new Display();
	
	Wcard w=new Wcard("Saraf","200111600200",774039122,'S');
	w.setbalance(2000.00);
	w_notcard a=new w_notcard();
  
	m_banking mb=new m_banking();
  
	do{
		System.out.println("\n");
		System.out.println("Welcome to people's Bank \n All prosiger Athoraized");
		//System.out.println("\n");
		System.out.println("\n     1-Cash widhrow With card");
		System.out.println("     2-Cash widhrow Without card");
		System.out.println("     3-mobile Banking");
		System.out.println("");
		System.out.println("**********************");
		System.out.println("Enter a number. That which Way do you want to use");
		choose=input.nextInt();
		
		switch(choose){
		case 1:
			w.dis();
		break;
		case 2:
			a.wcard();
		break;
		case 3:
			mb.mobile();
			mb.wcard();
		break;
		default:
			System.out.println("Invalid number!");
		}
		System.out.println("Do you need to work another process");
		select=input.next().charAt(0);
	}
		while(select == 'y');
			System.out.println("Thank you for choosing people's bank!");
	}
}
