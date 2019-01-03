
##24.Swap nodes in pairs
![Alt text](./1546504571241.png)

###1.Iterative 
>Tips: Create a dummy node before the first node, then use a pointer "current" to access the linklist and swap the adjacent nodes.Attention: 

- The critical condition - i.e., current.next == null (the list is empty) or current.next.next === null (Only one node in the list), Under these conditions, return dummy.next
- After creating the dummy node, remember to create a pointer - current.

Time complexity: O(n) 
Space complexity: O(1)

    class Solution {
	    public ListNode swapPairs(ListNode head) {
	        ListNode dummy = new ListNode(0);
	        dummy.next = head;
	        ListNode current = dummy;
        
	        while(current.next!=null && current.next.next!=null){
	            ListNode first = current.next;
	            ListNode second = current.next.next;
            
	            current.next = second;
	            first.next = second.next;
	            second.next = first;
	            
	            current = current.next.next;
	        }
        
        return dummy.next;
	    }
	}

###2. Recursion