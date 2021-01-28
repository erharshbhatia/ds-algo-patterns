Mock 1: Check if a string is rotation of another && Majority Element(II)
<br>
Majority Element general case: Given an array of size n and a number k, find all elements that appear more than n/k times.
<br>
First of all majority element is one which occurs n/k + 1 times.
<br>
Through which we come on to the conclusion that for a given n the maximum number of majority elements possible are k-1
<br>
Intution for k=2<br>
//intution is to consider the first element as the majority element and when other numbers are 
//found cancel out the count of the majority element
//now when the count becomes zero that means that the current majority element is not our ans
//therefore we update the element to curr element of array
//but after getting the majority element always verify it but Why? test case =[2, 2, 3, 4] || [1, 2, 3, 4]
Intution for k<br>
Mock 2: Date: 28 Jan, 2020
<br>
Height Checker && Long Pressed String(Imp) [two pointer && string compression]
