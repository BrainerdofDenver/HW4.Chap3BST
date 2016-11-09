# HW4.Chap3BST

Not complete yet. Still working on the BST implementation.

My progress thus far:

/*
   The Ficus is my favorite kind of tree and
   will be my implementation of a binary search
   tree class.
   Programmer: Andrew Brainerd
   Purpose: HW4 Chap 3.2 BST
*/
public class Ficus{
          //Class Variables
private int DMA;        private Ficus Prnt;
private String re;      private boolean hasNull;
private String st;      private int depth;
private Ficus Lft;      private int size;
private Ficus Rgt;      public static Ficus Temp;
private Ficus slf;      public static boolean BALANCED;

          //Class Constructors
public Ficus(int dma, String R, String S, Ficus tmp){

      DMA = dma;     re = R;  st = S;
      size = 1;      hasNull = true;
      slf = tmp;     depth = 1;
   }
   
          //Class Mutators
public void setDMA(int dma){
   DMA = dma;
   }
public void setRegion(String R){
   re = R;
   }
public void setState(String S){
   st = S;
   }
private void branchL(Ficus L){//Setting a left branch initiates values and updates null status
   Lft = L;
   if (Rgt != null) hasNull = false;
   Lft.setParent(slf);
   size++;
   Lft.setDepth();
   }
private void branchR(Ficus R){//Setting a right branch initiates values and updates null status
   Rgt = R;
   if (Lft != null) hasNull = false;
   Rgt.setParent(slf);
   size++;
   Rgt.setDepth();
   }
private void setParent(Ficus P){//Setting parent node initiates depth in child
   Prnt = P;
   depth = Prnt.getDepth() + 1;
   if (Prnt.getNullState() == true){//preliminary balance check by evaluation of root null states
      Ficus tmp = Prnt.Parent();
      if (tmp.getNullState() == true) BALANCED = false;
      }
   }
private void setDepth(){//Calls on the depth of parent node and ++
   if (Prnt != null) depth = Prnt.getDepth() + 1;
   else depth = 1;
   }
   
          //Accessor Methods
public int getDMA(){
   return DMA;
   }
public String getRegion(){
   return re;
   }
public String getState(){
   return st;
   }
public Ficus Left(){
   return Lft;
   }
public Ficus Right(){
   return Rgt;
   }
public Ficus Parent(){
   return Prnt;
   }
public boolean getNullState(){
   return hasNull;
   }
public int getDepth(){
   return depth;
   }
public int getSize(){
   return size;
   }
public boolean isBalanced(){
   return BALANCED;
   }
   
            //Logistic Methods
public boolean compareDMA(int D){
   return D <= DMA;
   }
}

