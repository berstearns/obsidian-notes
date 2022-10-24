problem statement:

given a number of levels n and two arrays were each element is numbered 1<=v<=n determine if by combining the two arrays we have all numbers in the range(1,n)

solution:
	we just want to check if len(set(union(arr1, arr2))) == n

status:
	idea worked
	