## Find length of a Singly Linked List in Java (Implementation)

- Getting **length** in Singly Linked List.

```

public class SinglyLinkedList {
	
	private ListNode head;
	
	private static class ListNode {
		private int data; //Generic type
		private ListNode next;
		
		public ListNode(int data) {
			this.data = data;
			this.next = null;
		}
	}

	public void display() {
		ListNode current = head;
		
		while (current != null) {
			System.out.println(current.data + " --> ");
			current = current.next;
		}
		System.out.println("null");
	}
	
	
	public int length() {
		if (head == null) {
			return 0;
		}
		int count = 0;
		ListNode current = head;
		while (current != null) {
			count++;
			current = current.next;
		}
		return count;
	}
	
	public static void main(String[] args) {
		SinglyLinkedList sll = new SinglyLinkedList();
		//Head is null
		sll.head = new ListNode(10);
		ListNode second = new ListNode(1);
		ListNode third = new ListNode(8);
		ListNode fourth = new ListNode(11);
		
		//Connecting nodes
		sll.head.next = second; // 10 --> 1
		second.next = third; // 10 --> 1 --> 8
		third.next = fourth; // 10 --> 1 --> 8 --> 11 --> null
	
		
		sll.display();
		System.out.println("Length is . " + sll.length());
	}
}

```