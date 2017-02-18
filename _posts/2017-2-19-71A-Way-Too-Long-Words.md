####71A - Way Too Long Words_Codeforces 

**Accepted**

    import java.io.IOException;
    import java.util.Scanner;
    
    public class Waytoolongwords {
    	public static void main(String[] args)throws IOException{
    		int n=0;
    		Scanner in = new Scanner(System.in);
    		n = in.nextInt();
    		while(n>0){
    			String str1 = in.next();
    			if (str1!=null && str1.length()>10 ){
    				System.out.println(str1.substring(0,1) + (str1.length()-2) + str1.substring(str1.length()-1));
    			}else{
    				System.out.println(str1);
    			}
    			n--;
    		}
    	}
    }


At first I used BufferedReader twice to save both the number and the string, 
the output are all null, so I changed to use Scanner.
See [here](http://stackoverflow.com/questions/5287538/how-can-i-get-the-user-input-in-java "here") for some options for java input.

**Wrong Answer**

    import java.io.BufferedReader;
    import java.io.IOException;
    import java.io.InputStreamReader;
    
    public class Waytoolongwords {
    	public static void main(String[] args)throws IOException{
    		int n=0;
    		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    		String str = br.readLine();
    		n = Integer.parseInt(str);
    		while(n>0){
    			BufferedReader br1 = new BufferedReader(new InputStreamReader(System.in));
    			String str1="";
    			str1 = br1.readLine();
    			if (str1!=null && str1.length()>10 ){
    				System.out.println(str1.substring(0,1) + (str1.length()-2) + str1.substring(str1.length()-1));
    			}else{
    				System.out.println(str1);
    			}
    			n--;
    		}
    	}
    }