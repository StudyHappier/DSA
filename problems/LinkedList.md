# Linked List

# Reverse

## [1. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/description/)
Reverse a singly linked list.

iteratively and recursively

## [2. Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/description/)
Reverse a linked list from position m to n. Do it in one-pass.
Note: 1 ≤ m ≤ n ≤ length of list.

```
public ListNode reverseBetween(ListNode head, int m, int n) {

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
public ListNode reverseKGroup(ListNode head, int k) {

    }
```

# Rotate
## [4. Rotate List](https://leetcode.com/problems/rotate-list/description/)
Given a linked list, rotate the list to the right by k places, where k is non-negative.


# Merge

## [5. Merge two sorted lists](https://leetcode.com/problems/merge-two-sorted-lists/description/)
Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.
```
public ListNode mergeTwoLists(ListNode l1, ListNode l2) {

    }
```

## [6. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/description/)
Merge k sorted linked lists and return it as one sorted list. Analyze and describe its complexity.

```
public ListNode mergeKLists(ListNode[] lists) {

    }
```

## [7. Sort list](https://leetcode.com/problems/sort-list/description/)
Sort a linked list in O(n log n) time using constant space complexity.

```
public ListNode sortList(ListNode head) {

    }
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
