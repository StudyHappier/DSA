# Types of Linked Lists
- singly linked list
- doubly linked list

```
// singly linked list
private static class ListNode {
   private int val;
   private ListNode next;

   public ListNode(int val, ListNode next) {
       this.val = val;
       this.next = next;
   }
}

// doubly linked list
private static ListNode {
   private int val;
   private ListNode next;
   private ListNode prev;
}
```

# Basic operations in singly linked list
## insert a new node
1. at the front of the linked list
```
public ListNode insertAtFirst(ListNode head, int m) {
   ListNode node = new ListNode();
   node.val = m;
   node.next = head;
   return node;
}
```
2. after a given node
3. at the end of the linked list
```
public ListNode insertAtLast(ListNode head, int m) {
   ListNode node = new ListNode();
   node.val = m;

   if (head == null) {
      return node;
   } else {
      ListNode last = head;
      while (last.next != null) {
          last = last.next;
      }

      last.next = node;
      return head;
   }
}

```

## delete a node
1. delete the first element of the linked list
```
public ListNode deleteAtFirst(ListNode head) {
   if (head != null) {
      head = head.next;
   }

   return head;
}
```
# Basic operations in doubly linked list
## insert
1. At the front of the DLL
2. After a given node.
3. At the end of the DLL
4. Before a given node.


# References
1. [Geeksforgeeks](https://www.geeksforgeeks.org/doubly-linked-list/)
