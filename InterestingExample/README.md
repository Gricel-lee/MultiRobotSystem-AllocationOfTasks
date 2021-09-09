I created this simple example on how to allocate machines with certain tasks to operators.

```javascript

sig operator{
	runs: set Machine
}

abstract sig Machine{
	do: set Work
}
fact {all m:Machine | #runs.m = 1}
fact {all m:Machine | disj [m.do , (Machine-m).do ] }


sig machine1 extends Machine{}{
	#do = 2
	not disj [do , work1]
	not disj [do , work2]
}


sig machine2 extends Machine{}{
	#do = 2
	not disj [do , work2]
	not disj [do , work3]
}

abstract sig Work{}

sig work1 extends Work{}
sig work2 extends Work{}
sig work3 extends Work{}



pred checktime{}


run checktime for exactly 2 operator, exactly 2 machine1, exactly 1 machine2, 6 Work
```


![Capture](https://user-images.githubusercontent.com/63869574/132686172-f0e48234-6983-4ffa-b820-aac39e4de953.JPG)


Interestingly, Alloy only creates the next allocations result in Alloy Analyzer
```
operator1	operator0
10		11 2
10 2		11
10 11 2		
10 11		12
```

where "10" is machine 1 instance 0; "11" is machine 1 instance 1; and "2" means machine 2.

And after these, the legend appears:

![image](https://user-images.githubusercontent.com/63869574/132686476-c0e15af2-7160-422d-8756-81e2bd07a9fb.png)

See for instance, that the allocation where operator0 gets all the machines is not found (or not fetched):
```
operator1	operator0
-		10 11 2
```
