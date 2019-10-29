# AppendCodingNinja
AppendLastNToFirst
Send Feedback
Given a linked list and an integer n, append the last n elements of the LL to front.
Indexing starts from 0. You don't need to print the elements, just update the elements and return the head of updated LL.
Assume given n will be smaller than length of LL.
Input format :

Line 1 : Linked list elements (separated by space and terminated by -1)`

Sample Input 1 :
1 2 3 4 5 -1
3
Sample Output 1 :
3 4 5 1 2
* */
public class Solution {
	public static LinkedListNode<Integer> append(LinkedListNode<Integer> root, int n) {
      LinkedListNode<Integer> temp=null;
      LinkedListNode<Integer> end=null;
      int length=1;
      end=root;
      //pointing this end node to last node
      while(end.next!=null){
        length++;
        end=end.next;
      }
      int i=1;
      temp=root;
      //pointing this temp node to the (length-2)node i.e the node after this we have to append 
      //if n==2 then we will point to 8th node
      while(i<length-n){
        i++;
        temp=temp.next;
      }
      end.next=root;
      root=temp.next;
      temp.next=null;
      return root;
    }
}
