q1.
------
import java.util.*;
class Date{
	int d,m,y;
	String date;
	Date(String date){
		this.date=date;
	}
	String calculate(){
		int pos1=0,pos2=0;
		N:for(int i=0;i<date.length();i++){
			if(date.charAt(i)=='/'){
				pos1=i;
				break N;
			}
		}

		for(int i=pos1+1;i<date.length();i++){
			if(date.charAt(i)=='/'){
				pos2=i;
				break;
			}
		}
		d=Integer.parseInt(date.substring(0,pos1));
		m=Integer.parseInt(date.substring(pos1+1,pos2));
		y=Integer.parseInt(date.substring(pos2+1,date.length()));
		String months[] = {"Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"};
		return ""+d+" "+months[m-1]+" "+y;
	}
}

public class QuestionOne{
	public static void main(String[] args){
		Scanner scan=new Scanner(System.in);
		String s=scan.next();
		Date d=new Date(s);
		System.out.println("Date " + d.calculate());
	}
}
-----------------------------------------------------------------------

(q2.)
import java.util.*;
class Demo<T extends Comparable<T>>{
	public static<T extends Comparable> void sortAnyType(T a[]){
		Arrays.sort(a);
	}
	public static<T extends Comparable> void print(T a[], int n){
		
		for(int i=0;i<n;i++){
			System.out.print(a[i]+" ");
		}
		System.out.println();System.out.println();
	}
}

public class QuestionTwo<E extends Comparable>{
	public static void main(String[] args){
		Integer[] ints={3,1,2,7,4,5};
		Float[] f={3.2f,1.3f,2.5f,7.1f,4.0f,5.9f,3.1f};
		Character[] c={'d','g','c','w','h','s'};
		String[] s={"adsd","fdff","grbb","cvbdf","efvss"};
		
		System.out.println("Integer class");System.out.println("======================");
		Demo.sortAnyType(ints);
		Demo.print(ints,ints.length);

		System.out.println("Float class");System.out.println("======================");
		Demo.sortAnyType(f);
		Demo.print(f,f.length);

		System.out.println("Character class");System.out.println("======================");
		Demo.sortAnyType(c);
		Demo.print(c,c.length);

		System.out.println("String class");System.out.println("======================");
		Demo.sortAnyType(s);
		Demo.print(s,s.length);
	}
}
--------------------------------------------------------

(q3.)
import java.util.*;
class DemoP<T extends Comparable>{
	public static<T extends Comparable> void print(T a[], int n){
		
		for(int i=0;i<n;i++){
			System.out.print(a[i]+" ");
		}
		System.out.println();System.out.println();
	}
}

public class QuestionThree<E extends Comparable>{
	public static void main(String[] args){
		Integer[] ints={3,1,2,7,4,5};
		Float[] f={3.2f,1.3f,2.5f,7.1f,4.0f,5.9f,3.1f};
		Character[] c={'d','g','c','w','h','s'};
		String[] s={"adsd","fdff","grbb","cvbdf","efvss"};
		
		System.out.println("Integer class");System.out.println("======================");
		DemoP.print(ints,ints.length);

		System.out.println("Float class");System.out.println("======================");
		DemoP.print(f,f.length);

		System.out.println("Character class");System.out.println("======================");
		DemoP.print(c,c.length);

		System.out.println("String class");System.out.println("======================");
		DemoP.print(s,s.length);
	}
}
-------------------------------------------------------------
(q4.)
import java.util.*;
class Detail implements Comparable<Detail>{
	String dob;
	String name;
	int date;
	int month;
	int year;
	String getName(){
		return name;
	}
	String getDob(){
		return dob;
	}
	Detail(String dob,String name){
		this.name=name;
		this.dob=dob;
	}
	public int compareTo(Detail ob){
		if((this.name).compareTo(ob.name)>1){
			return 1;
		}
		else if((this.name).compareTo(ob.name)<0){
			return -1;
		}
		else{
		if(this.year<ob.year){
			return -1;
		}
		else{
			if(this.month>ob.month){
				return 1;
				}
			else if(this.month<ob.month){
				return -1;
			}
			else{
				if(this.date>ob.date){
					return 1;
				}
				else if(this.date<ob.date){
					return -1;
				}
				else{
					return 0;
				}
			}
		}
		}
	}	
	
}
public class QuestionFour{

	void findDetail(Detail d){
		String dob=d.getDob();
		String[] s=dob.split("/",0);
		d.date=Integer.parseInt(s[0]);
		d.month=Integer.parseInt(s[1]);
		d.year=Integer.parseInt(s[2]);
	}
	void print(List<Detail> l){
		Iterator it=l.iterator();
		while(it.hasNext())
			findDetail(((Detail)it.next()));

		Collections.sort(l);

		it=l.iterator();
		while(it.hasNext()){
			Detail d=((Detail)it.next());
			System.out.println(d.name+"	"+d.date+" "+d.month+" "+d.year);
		}
	}

	public static void main(String[] args){
		List<Detail> l=new ArrayList<Detail>();
		l.add(new Detail("1/4/1999","xyz") );
		l.add(new Detail("1/5/1999","arun") );
		l.add(new Detail("1/6/1997","abhi") );
		l.add(new Detail("1/7/1996","himalya") );
		QuestionFour d=new QuestionFour();
		d.print(l);
	}
}
