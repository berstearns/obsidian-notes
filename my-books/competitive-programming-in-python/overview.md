

# chapters
	1. introduction
		1. read the standard input
		2. read a graph on input
		3. complexity
		4. abstract types and essential data structures
			1. stacks
				abstract type that can test if it's empty, add an element to the top (push), access the top element, remove te top element		
				1. stack implementation
					1. a list using append and pop
				2. queue implementation
					1. a lst using insert(v, 0) and pop
				3. deque implementation (double stack implementation)
			2. dictionaries
				1. assoication key values
				2. hash table
				3. hash function to associate the elements with indices in an array
				4. implements a colision mechanism
			3. queues 
				1. priority queres and heaps
					1. adt allowing elements to be added and an element with minimal key to be removed
					2. it turns out ot be useful in sorting arrays in heapsort and in the constructions of huffman code. in the search for the shortest path between two nodes in a graph.
					3. implementation
						1. it's typically implemented with a heap which is a ata structure implemented in a form of a tree
					4. perfect and quasi-perfect binary trees
						1. a bt is either empty  or is made up of a node with two chidlren or subtrees left and right. the note at hte top of the tree is the root while hte nodes with two empty children at the bottmo tof the tree are theleavesa a binary tree i sperfect if all its leavesa area tat he same distance from root. it is quasi-perfect if all its leaves are on at most two levels the seond level from the bottom is completely full and all the leaves on the bottom levle are goruped to the left. such a tree canconviientlay be represented by an array.
					5. Priority queres and heaps
						1. A heap is known as a tournament treem is a tree verifying 
							1. the heap property : eah node hsa a kye samller than each of tis chidlren for a certain order relation. the root of a heap is thus the element eithh smallest value
						2. binary heaps are quasi-perfect binary tournament trees.
							1. this data strcture allows the extraction of the smallest elemtn in constant time and the insertion of a new element with a logaritimic cost =. 
							2. heap also allows the update of the importance of an element which will be useful operation for the dikstra algorithm when a short path has bheen discovered towards  a summit
								1. use hte module heapq transforminig an array into a heap
					6. union-find
						1. it's used to store a partition of a universve V and that allows the following operations
							1. find(v) returns a canonical elem ent of the set containing v. To test if u and vare the in the same set it suffices to compare find(u) with find(v)
							2. union(u, v) combines the set containig u wiht that containg v
							3. used in connected graphs and also used in the kruskal's algoorithm to determine a miniminmal spanning tree of a weigheted graph
			4. 
			5. techiniques
				1. comparison
					1. comparison between n-tuples is based on lexicographical order.
				2. sorting
				3. sweeping line
				4. greedy algorithms
				5. dynamic programming
				6. encoding of sets by integers
				7. binary (dichtomic) search
				8. 
 1. character strings
	2. sequences
	3. arrays
	4. intervals
	5. graphs
	6. cycles in graphs 
	7. shortest paths
	8. matching and flows
	9. trees
	10. sets 
	11. points and polygons
	12. rectangle
	13. numbfer and matrix
	14. exausthive search