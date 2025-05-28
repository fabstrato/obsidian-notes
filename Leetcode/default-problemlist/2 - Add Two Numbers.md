At first i misinterpreted this problem, thinking i had to sum the total of the array and add one to the other (l1 = [1,2,3] l2= [3,2,1] result= [4,4,4]), but after i got the gist of it, the best way i thought of going through this was converting the numbers to str and putting a for to concat them, converting them back to int after reversing them:

```
class Solution:

    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:

    firstlist = 0

    secondlist = 0

    lenfirst = len(l1)

    lensecond = len(l2)

  

    while lenfirst != -1:

        numtemp1 += str(l1[lenfirst])

        lenfirst--

  

    while lensecond != -1:

        numtemp2 += str(l2[lensecond])

        lensecond--
```

i could use enumerate, but it still is a little confusing to me, so i just decided to go through with this method for now, at least until

```
TypeError: object of type 'ListNode' has no len()
```

and gpt schooled me

![[Pasted image 20250528163134.png]]

i only asked gpt to give me an example on how to iterate on listnodes, and throughout some UnboundLocalErrors, i got this:

```
class Solution:

    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:

        numtemp = ""

        current = l1

        while current:

            numtemp = str(current.val) + numtemp

            current = current.next

  

        print(numtemp)
```

which would give me:

```
Stdout

342
```

so reversing is good to go.

managed to get the value from basically copying the method above for the second list, now to create listnodes, i had to go through some docs, ended up with this as the final:

```
# Definition for singly-linked list.

# class ListNode:

#     def __init__(self, val=0, next=None):

#         self.val = val

#         self.next = next

class Solution:

    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:

        numtemp1 = ""

        numtemp2 = ""

        numtemp_final = ""

  

        current1 = l1

        while current1:

            numtemp1 = str(current1.val) + numtemp1

            current1 = current1.next

  

        current2 = l2

        while current2:

            numtemp2 = str(current2.val) + numtemp2

            current2 = current2.next

  

        num = int(numtemp1) + int(numtemp2)

        dummy = ListNode()

        curr = dummy

  

        for digit in str(num)[::-1]:

            curr.next = ListNode(int(digit))

            curr = curr.next

  

        return dummy.next
```