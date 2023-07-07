# Classwork2-Assignment
# The following code will run a program that will check a string value for its delimiters and put them into a stack and check if there is a equal balance or unbalance.The code uses the push and pop commands to insert and remove the last element from an array in the LIFO order. If the top value equals -1, then the string or in this case, the number of delimiters is balanced. If not equal to 1, then it is unbalanced and the program will let the user know if it is unbalanced. 

class Main {
  public static int maxSize;
    public static String[] stack1;
  public static int[] index;
    public static int top = -1;
  
  public static void main(String[] args) {
     String[] array = new String[]{"(", "("};
     //String[] array = new String[]{"(", "(", ")", ")"};

    String[] check = delimiterCheck(array);
    
System.out.println(check.length);
    System.out.print("Input Array: ");
  for(int i = 0; i < check.length;i++){
  System.out.print( array[i]);
  }
    System.out.println("");
System.out.println("Top value : " + top);

    System.out.println("Is the stack empty? " + empty());
    System.out.println("Is there an overflow when doing the delimiter check? " + full());


    if(top == -1){
      System.out.println("Balanced");
    } else {
      System.out.println("Unbalanced");
    }
    }


public static String[] delimiterCheck(String[] array){
  maxSize = array.length;
     stack1 = new String[maxSize];
     index = new int[maxSize];
 for(int i = 0; i <maxSize; i++){
   if(array[i] == "("){
     push("(");
     index[i] = i;
   }

   if(array[i] == ")"){
     pop();
   }
 }
    return stack1;
  }
  
  public static void push(String j){
    stack1[++top] = j;
  }

  public static String pop(){
   return stack1[top--];
  }

  public static boolean empty(){
    return (top == -1);
  }

  public static boolean full(){
    return (top == maxSize -1);
  }
  
}
