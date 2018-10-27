q1.
---
class Print{
	
	public synchronized void print(String n,int count){
		for(int i=count;i<=500+count;i++){
			System.out.println(n+" : "+i);
		}
	}
}
public class QuestionOne{
	public static void main(String[] args){
		Print obj=new Print();
		Thread t1=new Thread(new Runnable(){
			public void run(){
				
				obj.print("T1",0);
			}
		});
		
		Thread t2=new Thread(new Runnable(){
			public void run(){
				obj.print("T2",500);
			}
		});
		
		t1.start();
		t2.start();
	}
}