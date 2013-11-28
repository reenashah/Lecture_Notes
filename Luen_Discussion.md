###Conference Call with Luen

v versus t: an error diagram
- 0:1 scale
- negative relationship
- draw for ETAS model and Alarm Model

a) ETAS
- conditional intensity is the main output of the model; how likely it is to have an earthquake at any particular point in time
- both are functions of conditional intensity
	- high values of lambda in left side, low values on right side
	- threshold at which we turn on the alarm
	e.g.) turn on alarm iff lambda >= 10
	*we can do this for all values of lambda*

- to evaluate tao (proportion of time the alarm is on): 
	- find tao to evaluate the conditional intensity on a grid of times
	- find v, we can evaluate the conditional intensity on a grid of event times
	*you'd want to do this on a test set

- to find v, find the conditional intensity, evaluated on event times
	- what proportion of events has a conditional intensity greater than 1, less than 1
	- if conditional intensity >1, any alarm that captures that event also captures events where predicted conditional intensity >1
		- you will miss anything with lower conditional intensity
	* v = proportion of earthquakes you miss
		- proportion of events that have conditional intensity just beforehand of the value of 
                        lambda

Error Diagram
- instead of lambda, you can do it in terms of window length
- in the previous diagram, we saw it had a negative relationship
- when we just talk about window length, it's the other way around; as window length goes up, we capture more; so it's a positive relationship in terms of window length
	- then you can calculate what proportion of earthquakes you miss if you choose a certain window length

- for a particular window length, we are just going to use the inter-arrival times as the only thing that is in our prediction
	- then we can deduce a function lambda from the inter-arrival times by finding the CDF; differentiate to find the PDF
	- you can say lambda = 1/w, and that might be the easiest thing to do
		- wrong if you want # of earthquakes, but may help if you just want an instance

- automatic alarm to magnitude-dependent alarm:
	- adjusting for magnitude
	- it's the same principle as in the MDA alarm

- load test catalog
	- SEC catalog from 1984-2010
	- converted it so there's a time variable (days after the beginning of 1984) and magnitude variable
	- set start of test period to be 18 June 2004

- two definitions of alpha
	- depends on 10^x and e^x
	- be careful which version you are using

High-Value Issues
- end goal: beat ETAS
	- his version didn't
- need some different kind of approach
- work out exactly how or why ETAS does do better than the MDA alarms
	- think of each as having different components
	- is one component that scales by magnitude, one that scales by time, one that takes the sum overall [which one is the best? which is actually working?]
	- which parts of ETAS are responsible for results
		- maybe magnitude scaling works better than time scaling
		- better way to time scaling, etc.
- new model
	- may even be more complex
