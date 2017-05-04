# Doubly-Linked-List-Java


public class DLLNode {
	
	public int data;
	public DLLNode next;
	public DLLNode prev;
}


public class DoubleLinkList {
	private DLLNode head;
	private DLLNode tail;
	
	public DoubleLinkList(){
		head = null;
		tail = null;
	}
	
	public void addLast(int data) {
		DLLNode newnode = new DLLNode();
		newnode.data = data;
		newnode.next = null;
		newnode.prev = null;
    
		if (head == null) head = tail = newnode; 
		else {
			tail.next = newnode;
			newnode.prev = tail;
			tail = newnode;
		}
	}
	public void addFirst(int data) {
		    DLLNode newnode = new DLLNode();
		    newnode.data = data;
		    newnode.next = newnode.prev = null;
		    
		    if (head == null) head = tail = newnode;
		    else{
		    	head.prev = newnode;
		    	newnode.next = head;
		    	head = newnode;
		    }
		}
	public void printIt() {
		DLLNode p=head;
		System.out.print("NULL <--> ");
		while (p!=null) {
			System.out.print(p.data + " <--> ");
			p = p.next;
		}
		System.out.println("NULL");
	}
	public void addBetween(int data,int variable) {
		DLLNode p = head;
		while(p != null && p.data != variable) p = p.next;
		if(p != null) System.out.println("there is nowhere to add");
			if(p == head) addFirst(data);
			else{
				DLLNode newnode = new DLLNode();
				newnode.data = data;
				newnode.prev = p.prev;
				newnode.next = p;
				p.prev.next = newnode;
				p.prev = newnode;
			}
	}	
	public void printReverse() {
		System.out.println();
		DLLNode p=tail;
		System.out.print("NULL <--> ");
		while (p!=null) {
			System.out.print(p.data + " <--> ");
			p = p.prev;
		}
		System.out.println("NULL");
		tail = p;
	}
}
