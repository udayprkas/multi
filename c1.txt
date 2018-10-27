import java.util.Scanner;
class ArrayList{
	private int[] a=null;
	private int size;
	private int index=-1;
	ArrayList(){
		this.size=10;
		a=new int[this.size];
		
	}
	public void add(int n){
		if(index==(size-1)){
			int[] temp=a;
			this.size=(int)(this.size*1.5);
			a=new int[this.size];
			for(int i=0;i<=index;i++){
				a[i]=temp[i];
			}
		}
		index++;
		a[index]=n;
	}
	public void traverse(){
		if(index==-1){
			System.out.println("List is empty");
		}
		else{
			for(int i=0;i<=index;i++){
				System.out.println(a[i]);
			}
		}
	}
	public void clear(){
		a=null;
		index=-1;
		this.size=0;
	}
	public int size() {
		return (this.index+1);
	}
}

public class QuestionOne{
	public static void main(String[] args){
		ArrayList l=new ArrayList();
		l.add(10);
		l.add(20);
		for(int i=0;i<=11;i++){l.add(i*10);}
		l.traverse();
		l.clear();
		l.traverse();
	}
}