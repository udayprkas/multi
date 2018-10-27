import java.io.*;
public class Question{
	public static void main(String[] args) throws Exception{
		File f=new File("C:/Users/Parmjot Singh chahal/Desktop/git/Dynamic Data Storage-2/text1.txt");
		File f2=new File("C:/Users/Parmjot Singh chahal/Desktop/git/Dynamic Data Storage-2/text2.txt");
		FileInputStream fin=new FileInputStream(f);
		FileOutputStream fout=new FileOutputStream(f2);
		int i=fin.read();
		while(i!=-1){
			fout.write((char)i);
			i=fin.read();
		}
		fin.close();
		fout.close();
		FileInputStream fin2=new FileInputStream(f2);
		i=fin2.read();
		while(i!=-1){
			System.out.print((char)i);
			i=fin2.read();
		}
		fin2.close();
	}
}