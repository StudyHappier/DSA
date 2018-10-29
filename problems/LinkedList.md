# Linked List

# Reverse

## Reverse Linked List
Reverse a singly linked list.

iteratively and recursively

## Reverse Linked List II
Reverse a linked list from position m to n. Do it in one-pass.
Note: 1 ≤ m ≤ n ≤ length of list.

```
public ListNode reverseBetween(ListNode head, int m, int n) {

    }
```

## Reverse Nodes in k-Group
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
## [Rotate List](https://leetcode.com/problems/rotate-list/description/)
Given a linked list, rotate the list to the right by k places, where k is non-negative.


# Merge

## Merge two sorted lists
Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.
```
public ListNode mergeTwoLists(ListNode l1, ListNode l2) {

    }
```

## Merge k Sorted Lists
Merge k sorted linked lists and return it as one sorted list. Analyze and describe its complexity.

```
public ListNode mergeKLists(ListNode[] lists) {

    }
```

## Sort list
Sort a linked list in O(n log n) time using constant space complexity.

```
public ListNode sortList(ListNode head) {

    }
```


## Intersection of Two Linked Lists
Write a program to find the node at which the intersection of two singly linked lists begins.

```
public ListNode getIntersectionNode(ListNode headA, ListNode headB) {

    }
```


# Remove

## Remove Linked List Elements
Remove all elements from a linked list of integers that have value val.

```
public ListNode removeElements(ListNode head, int val) {

    }
```

## Remove Duplicates from Sorted List
Given a sorted linked list, delete all duplicates such that each element appear only once.

```
public ListNode deleteDuplicates(ListNode head) {

    }
```

## Remove Duplicates from Sorted List II
Given a sorted linked list, delete all nodes that have duplicate numbers, leaving only distinct numbers from the original list.

```
public ListNode deleteDuplicates(ListNode head) {

    }
```

## Remove Nth Node From End of List
Given a linked list, remove the n-th node from the end of list and return its head.

```
public ListNode removeNthFromEnd(ListNode head, int n) {

    }
```

# Partition
## Partition List
Given a linked list and a value x, partition it such that all nodes less than x come before nodes greater than or equal to x.

You should preserve the original relative order of the nodes in each of the two partitions.

```
public ListNode partition(ListNode head, int x) {

    }
```

# Add two numbers
## Add two numbers
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

## Add Two Numbers II
You are given two non-empty linked lists representing two non-negative integers. The most significant digit comes first and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Follow up:
What if you cannot modify the input lists? In other words, reversing the lists is not allowed.
