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


run checktime for exactly 2 operator, exactly 2 machine1, exactly 1 machine2, 6 Work```

Interestingly, Alloy only creates the combinations



