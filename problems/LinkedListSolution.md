# Linked List

# Reverse

## [1. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/description/)
Reverse a singly linked list.

```
//Iterative Solution 
class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode curr = head; 
        ListNode prev = null; 
        ListNode next =null; 
        while(curr != null){
            next = curr.next;  // store the next node 
            curr.next = prev;  // the previous node 
            prev =curr;  // update the previous 
            curr = next;  // move the current node forward 
        }
        return prev; 
        
    }
}
```

```
// Recursive Solution 
class Solution {
    public ListNode reverseList(ListNode head) {
        if(head == null || head.next == null)  
            return head; 
        ListNode temp = head.next; 
        head.next = null; 
        ListNode prev = reverseList(temp);  // use recursion to go the end  node 
        temp.next = head;            // when coming back from the stack call, start reversing 
        return prev;  // at each stage return the curr head, 
        
    }
}
```

iteratively and recursively

## [2. Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/description/)
Reverse a linked list from position m to n. Do it in one-pass.
Note: 1 ≤ m ≤ n ≤ length of list.

```

class Solution {
    private ListNode reverse(ListNode head,int count){
        if(head == null || head.next ==null) // corner-case
            return head; 
        
        ListNode next = null; 
        ListNode curr = head; 
        ListNode prev = null; 
        while(curr != null && count >0 ){ //routine reverse 
            next  = curr.next; 
            curr.next = prev; 
            prev =curr; 
            curr =next; 
            count--; 
        }
        return prev; 
    }
    
    public ListNode reverseBetween(ListNode head, int m, int n) {
        if(head == null)
            return head;
        
        int size = n-m +1; // calculate the size of the linked list to be reversed 
        
        ListNode dummy = new ListNode(-1); 
        dummy.next = head; 
        ListNode slowPtr = dummy ;  // the node before m
        ListNode headPtr = head;   // the mth node 
        ListNode endPtr = head;  // the node after the nth node 
        
        for(int i=1;i<m;i++){
            slowPtr = slowPtr.next;   // traverse to find the nodes
            headPtr = headPtr.next; 
        }
        
        for(int i=1;i<=n;i++){
            endPtr = endPtr.next;  
        }
        
        slowPtr.next = reverse(headPtr,size);  //link the node before m with the nth node 
        headPtr.next = endPtr;  //  link the mth node with the node after n
        return dummy.next;  //return the  head 
        
        
    }
}
```

## [3. Reverse Nodes in k-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/description/)
Given a linked list, reverse the nodes of a linked list k at a time and return its modified list.

k is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of k then left-out nodes in the end should remain as it is.

Example:

Given this linked list: 1->2->3->4->5

For k = 2, you should return: 2->1->4->3->5

For k = 3, you should return: 3->2->1->4->5

Note:

Only constant extra memory is allowed.
You may not alter the values in the list's nodes, only nodes itself may be changed.


```
ListNode* reverseKGroup(ListNode* head, int k) {
        if(head == nullptr || head->next ==nullptr)   // handle corner cases
            return head; 
        ListNode* next = nullptr; 
        ListNode* curr = head; 
        ListNode* prev = nullptr;
        int count = k; 
        
        while(curr != nullptr and count > 0){  // routine reverse logic + we will only reverse nodes of length k each time 
            next = curr->next; 
            curr->next = prev; 
            prev = curr; 
            curr = next; 
            count--; 
        }
        if(next){                                 // we still have some nodes, and the head is the new end node, since we have to link that, we call the it recursively to find their new head node
            head->next = reverseKGroup(next,k);
        }
        return prev;  // prev is the new head in all our process. 
        
        
    }
```

# Rotate
## [4. Rotate List](https://leetcode.com/problems/rotate-list/description/)
Given a linked list, rotate the list to the right by k places, where k is non-negative.

```
class Solution {
private:
    int calculate_size(ListNode* head){ // get the total size 
        int count =0; 
        while(head){
            head = head->next; 
            count++; 
        }
        return count; 
    }
    ListNode* get_end_node(ListNode* head){ // get the tail node, to convert it into a circular linked list
        while(head->next)
            head = head->next; 
        return head; 
    }
    
    ListNode* kth_node_from_end(ListNode* head, int k){// find the node before the kth node
        ListNode* slow_ptr  =head; 
        ListNode* fast_ptr = head; 
        while(k){
            fast_ptr = fast_ptr->next; 
            k--; 
        }
        ListNode* prev_ptr = nullptr; 
        while(fast_ptr){
            prev_ptr = slow_ptr;
            slow_ptr = slow_ptr->next; 
            fast_ptr = fast_ptr->next; 
        }
        return prev_ptr;  // we want the node before kth node to remove the cycle. 
        
    }
public:
    ListNode* rotateRight(ListNode* head, int k) {
        if(head == nullptr || head->next == nullptr)
            return head; 
        
        int get_size = calculate_size(head); 
        int rotation_required = k % get_size; 
        if(rotation_required == 0)
            return head; 
        
        ListNode* kth_node = kth_node_from_end(head,rotation_required); 
        ListNode* end_node = get_end_node(head); 
        end_node->next  = head;  // make it circular linked list, now all we need to do is make the kth_node as head,  
        
       
        head = kth_node->next;  // make the kth node as the new head 
        kth_node->next = nullptr;  // remove the cycle we created,
        return head; 
        
        
        
    }
```


# Merge

## [5. Merge two sorted lists](https://leetcode.com/problems/merge-two-sorted-lists/description/)
Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.
```
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if(!l1)  return l2;  // corner-cases
        if(!l2) return l1; 
        
        ListNode* dummy = new ListNode(-1); 
        ListNode* head_last = dummy;  // to insert at the end of our new linked list 
        
        while(l1 and l2){
            if(l1->val < l2->val){
                head_last->next = l1; 
                l1 = l1->next; 
            }
            else{
                head_last->next = l2; 
                l2 = l2->next; 
            }
            head_last = head_last->next; 
        }
        
        if(l1){
            head_last->next = l1; 
        }
        else{
            head_last->next =l2; 
        }
        return dummy->next; 
        
        
    }
};
```

## [6. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/description/)
Merge k sorted linked lists and return it as one sorted list. Analyze and describe its complexity.

```
class Solution {
public:
    struct compareNode{
        bool operator()(ListNode* l1, ListNode*l2){
            return l1->val > l2->val; 
        }
    }; 
    
    ListNode* mergeKLists(vector<ListNode*>& lists) {
        priority_queue<ListNode*, vector<ListNode*>, compareNode> pq; 
        for(auto i : lists){
            while(i){    //read each linked lists and put them  into the priority queue
                pq.push(i);  
                i = i->next; 
            }
        }
        ListNode* dummy= new ListNode(-1); 
        ListNode* head_last = dummy; // we have to insert at the end 
        while(!pq.empty()){     
            head_last->next = pq.top(); // build the new linked list using the top ones  
            pq.pop(); 
            head_last = head_last->next; 
        }
        head_last->next = nullptr; 
        return dummy->next; 
        
    }
};
```

## [7. Sort list](https://leetcode.com/problems/sort-list/description/)
Sort a linked list in O(n log n) time using constant space complexity.

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
private: 
    // usual merge logic 
    ListNode* merge(ListNode* l1, ListNode* l2){
        if(!l1) return l2; 
        if(!l2) return l1;
        
        ListNode* dummy = new ListNode(-1); 
        ListNode* head = dummy; 
        
        while(l1 and l2){
            if(l1->val < l2->val){
                head->next = l1; 
                l1 = l1->next; 
            }
            else{
                head->next = l2; 
                l2 = l2->next; 
            }
            head = head->next; 
        }
        if(l1){
            head->next = l1; 
        }
        else{
            head->next = l2; 
        }
        return dummy->next; 
    }
public:
    ListNode* sortList(ListNode* head) {
        if(head == nullptr || head->next == nullptr)
            return head; 
        ListNode* slow = head;
        ListNode* fast = head->next;  // very important, we need to find the first middle in case of even no of nodes.  
        while(fast and fast->next){
            fast = fast->next->next; 
            slow = slow->next; 
        }
        fast = slow->next;     //split them into and sort them and then merge them, usual merge sort 
        slow->next =nullptr;
        ListNode* l1 = sortList(head); 
        ListNode* l2 = sortList(fast); 
        return merge(l1,l2);           // return the merged list at each step. 
        
    }
};
```

## [8. Intersection of Two Linked Lists](https://leetcode.com/problems/intersection-of-two-linked-lists/description/)
Write a program to find the node at which the intersection of two singly linked lists begins.

```
public ListNode getIntersectionNode(ListNode headA, ListNode headB) {

    }
```


# Remove

## [9. Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/description/)
Remove all elements from a linked list of integers that have value val.

```
public ListNode removeElements(ListNode head, int val) {

    }
```

## [10. Remove Duplicates from Sorted List](https://leetcode.com/problems/remove-duplicates-from-sorted-list/description/)
Given a sorted linked list, delete all duplicates such that each element appear only once.

```
public ListNode deleteDuplicates(ListNode head) {

    }
```

## [11. Remove Duplicates from Sorted List II](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/description/)
Given a sorted linked list, delete all nodes that have duplicate numbers, leaving only distinct numbers from the original list.

```
public ListNode deleteDuplicates(ListNode head) {

    }
```

## [12. Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/)
Given a linked list, remove the n-th node from the end of list and return its head.
```
public ListNode removeNthFromEnd(ListNode head, int n) {

    }
```

# Partition
## [13. Partition List](https://leetcode.com/problems/partition-list/description/)
Given a linked list and a value x, partition it such that all nodes less than x come before nodes greater than or equal to x.

You should preserve the original relative order of the nodes in each of the two partitions.

```
public ListNode partition(ListNode head, int x) {

    }
```

# Add two numbers
## [14. Add two numbers](https://leetcode.com/problems/add-two-numbers/description/)
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.
```
public ListNode addTwoNumbers(ListNode l1, ListNode l2) {

    }
```

## [15. Add Two Numbers II](https://leetcode.com/problems/add-two-numbers-ii/description/)
You are given two non-empty linked lists representing two non-negative integers. The most significant digit comes first and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Follow up:
What if you cannot modify the input lists? In other words, reversing the lists is not allowed.

```
public ListNode addTwoNumbers(ListNode l1, ListNode l2) {

    }
```

# Doubly Linked List
## [16. LRU Cache](https://leetcode.com/problems/lru-cache/description/)
Design and implement a data structure for Least Recently Used (LRU) cache. It should support the following operations: get and put.

get(key) - Get the value (will always be positive) of the key if the key exists in the cache, otherwise return -1.
put(key, value) - Set or insert the value if the key is not already present. When the cache reached its capacity, it should invalidate the least recently used item before inserting a new item.

Follow up:
Could you do both operations in O(1) time complexity?

```
class LRUCache {

    public LRUCache(int capacity) {

    }

    public int get(int key) {

    }

    public void put(int key, int value) {

    }
}

/**
 * Your LRUCache object will be instantiated and called as such:
 * LRUCache obj = new LRUCache(capacity);
 * int param_1 = obj.get(key);
 * obj.put(key,value);
 */
```
