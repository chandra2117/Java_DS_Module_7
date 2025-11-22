# Ex6 Right Rotation LinkedList
## DATE: 20.09.2025
## AIM:
To write a Java  program to:
Create a singly linked list.
Rotate the linked list to the right by k positions.
Display the rotated linked list.
## Algorithm
1.Read n values to build the linked list and read k.
2.Find the length of the list and reach the last node.
3.Make the list circular by connecting last node to head.
4.Move length − (k % length) steps to find new tail.
5.Break the circle and print the list from the new head. 

## Program:
```
/*
Program to  Right Rotation LinkedList
Developed by: CHANDRAPRIYADHARSHINI C
RegisterNumber: 212223240019

import java.util.Scanner;
public class RotateLinkedList {
    public static Node rotate(Node head, int k) {
       //Type your code here
       if (head == null || head.next == null || k <= 0) return head;

        // Compute the length of the list
        Node temp = head;
        int length = 1;
        while (temp.next != null) {
            temp = temp.next;
            length++;
        }

        // Make the list circular
        temp.next = head;

        // Find the new tail: (length - k % length - 1)th node
        int stepsToNewHead = length - k % length;
        Node newTail = head;
        for (int i = 1; i < stepsToNewHead; i++) {
            newTail = newTail.next;
        }

        // Set the new head and break the circle
        head = newTail.next;
        newTail.next = null;

        return head;
       
    }
    public static void display(Node head) {
        Node current = head;
        System.out.print("LinkedList: ");
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Node head = null, tail = null;
        int n = scanner.nextInt();
        for (int i = 0; i < n; i++) {
            Node newNode = new Node(scanner.nextInt());
            if (head == null) {
                head = tail = newNode;
            } else {
                tail.next = newNode;
                tail = newNode;
            }
        }
        int k = scanner.nextInt();
        head = rotate(head, k);
        display(head);
        scanner.close();
    }
}
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

*/
```

## Output:

<img width="1280" height="344" alt="Screenshot 2025-11-22 132944" src="https://github.com/user-attachments/assets/47e0be95-d40c-4083-a48d-8bc31a830d0d" />



## Result:
Thus, the C program to perfom right rotation on linked list is implemented successfully.
