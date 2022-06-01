import java.util.Scanner;
class Account
{
private int accountId;
private String accountType;
private int balance;
public int getAccountId()
{
return accountId;
}
public String getAccountType()
{
return accountType;
}
public int getBalance()
{
return balance;
}
public void setAccountId(int id)
{
this.accountId=id;
}
public void setAccountType(String st)
{
this.accountType=st;
}
public void setBalance(int bal)
{
this.balance=bal;
}
public boolean withdraw(int withdraw_amount)
{
if(getBalance()<withdraw_amount)
{
System.out.println("Sorry!!!!!!!!! No enough balance");
return false;
}
else
{
System.out.println("Balance Amount After Withdraw: "+(getBalance()-withdraw_amount));
return true;
}
}
}
public class AccountApplication
{
public static Account getAccountDetails()
{
Account ac=new Account();
Scanner sc=new Scanner(System.in);
System.out.println("Enter account id: ");
ac.setAccountId(sc.nextInt());
sc.nextLine();
System.out.println("Enter account type: ");
ac.setAccountType(sc.nextLine());
int balance;
do
{
System.out.println("Enter Balance");
ac.setBalance(sc.nextInt());
balance=ac.getBalance();
if(balance<=0)
System.out.println("Balance should be positive");
}
while(balance<=0);
return ac;
}
public static int getWithdrawAmount()
{
Scanner sc=new Scanner(System.in);
int wd;
do
{
System.out.println("Enter amount to be withdrawn:");
wd=sc.nextInt();
if(wd<=0)
System.out.println("Amount should be positive");
}
while(wd<=0);
return wd;
}
public static void main(String[] args)
{
Account ac=new Account();
ac=getAccountDetails();
int am = getWithdrawAmount();
ac.withdraw(am);
}
}
