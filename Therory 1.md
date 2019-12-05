# Applications of Artificial Neural Networks (ANN)
-	Pattern recognition
-	General interpolation
-	Data representation
-	Signal processing
-	Time series prediction
-	System identification

# Fundamental Characteristics of ANN:s
-	An ANN consist of several NEURONS 
-	Each NEURON has an ACTIVATION FUNCTION 
-	The type of learning done is decided by the LEARNING RULE
-	The NEURONS are sorted into different NETWORK ARCHITECTURES/TOPOLOGIES
-	The ANN is driven by DATA

## NEURON
	A very simple unit which takes input from one or more sources, transforms it, and then passes it along to other # neurons.
	Can be described as an "INTEGRATOR", in that it integrates many input sources into a single output.

## ACTIVATION FUNCTION
	Decides the output of the neuron. 
	Real human neurons operate on the all-or-nothing principle, that is, if enough input excites the neuron it will fire - else it won't with no states in between.
	In ANN:s we have more variation. The output might be linear, sigmoid, all-or-nothing or piecewise linear.
		

## LEARNING RULE
	How the network decides what parts of input to give weight to.
	Fittingly, it does this by adjusting the weights between the neurons. 
	Stronger weights implies a stronger connection between neurons and vice versa.
	So if one neuron attuned to recognizing shapes "see" a ball, for example, it will strongly activate related neurons.
	One can imagine that related neurons are those that are attuned to analyzing ball-shaped objects.
	Thus we recognize the ball.
	Hopefully.

## TOPOLOGY/ARCHITECTURE
	How the entire network is structured.
	Examples include single-layer, multi-layer or reccurrent.
	If the network is structured into layers with no edges between neurons in layers, we have a FEED-FORWARD NETWORK.

## LEARNING ALGORITHM FAMILIES
	Supervised: For a given input, the desired output is known. By comparing the result produced by the ANN with the desired one, one can strive to minimize error by adjusting weights.

	Unsupervised: The underlying patterns and structures in data is unknown, and so we can't adjust weights based on divergence from desired result.
		One way to implement learning this way is by strengthening patterns. Differences get strengthenend, similarities get merged.

	Competitative: Neurons that compete to fire with only one succeeding - the one that reacts strongest to a given input.
		Leads to highly specialized neurons that excel at recognizing some aspect of the subject being learned.

	Hebbian: Nerons that fire at the same input and produces the same kind of output can be assumed to comprehend the same kind of structure, so strengthen the connection between them.
		As an analogy, say we have one cluster recognizing warmth, one recognizing the sun. Both will fire when we see the sun, and thus we increase the connection between sun and warmth. A bit like the classical conditioning performed by Pavel on dogs with food and bells.
		The hebbian family of learning algorithms is interesting in that the neurons can do their adaptions locally without knowing the state of the entire ANN, similar to how our brains work.

	Reinforcement
		Rewards on success. Punishment if failure. No specifying what exactly went wrong, allows the agent to explore strategies on it's own.
		Similar to how a child is learned.

	
## HEBB'S RULE
	Changes in strength of synaptic connections are proportional to the correlation in the firing of two connecting neurons.
	Thus, if two neurons consistently fire simoultaneously, the connection between the two is strengthened.
	In biology, this concept is known as LONG-TERM POTENTIATION (increasing the potential in the long run) and NEURAL PLASTICITY (The neural network changes over time).

---
# MISC

## PERCEPTRON
	Collection of McCulloch and Pitt neurons with some inputs and weights.

## MCCULOCH AND PITT NEURON
	A mathematical model of a biological neuron aiming to extract only the essentials. According to this model, a neuron is described as follows:

	x1...xn input sources
	w1...wn weights, one for each input source
	Summer: sums x1w1... xnwn
	Activation Function: Takes output from summer and fire (send 1) if sum is above threshold, otherwise don't fire (send 0)

	Also known as a binary threshold device.
	
	DIFFERENCES FROM REAL NEURONS
	Real neurons encode information by sending out several spikes (a spike train) rather than a single output.
	They also update themselves randomly and in paralell rather than sequentially.
	Being biological construct, their threshold can vary over time.
	Synapses (weights) in brains can be eigher positive or negative, but not switch between as in ANNS. 
	Neurons can link back to themselves.
	Neurons do not sum their input linearly.
	As an aside, real neurons send out several outputs/spikes (a spike train) and it is the sequence that encodes the information. Real neurons have varying thresholds. Real neurons update randomly, in paralell instead of sequentially as in a computer. Also, the potentials might not be summed linearly. 


## HOPFIELD NETWORK
	One type of recurrent artificial neural netwok with binary thresthold neurons guaranteed to converge to a local minimum.

## RECURRENT ARTIFICIAL NEURAL NETWORK
	A neural netwok where the connections/edges/axons form a directed cycle.This allows the RANNS to contain memory, allowing them to use their own state to generate a new state. Example use in handwriting generation/recognition.

## BACKPROPAGATION
	Method for training a neural network.
	Based on, after comparing the actual to the ideal, adjusting weights so that the result should be better next time

## COCKTAIL PARTY PROBLEM
	How to selectively focus on one single stream of information in a mass of noise - like trying to listen to one voice at a cocktail party.

## RADIAL BASIS FUNCTION
	Another type of activation function. Basically a function such that f(x) = f(|x|)

## DALES LAW
	A, for the mostly part true statement from neuroscience that a neuron may only release the same set of neurotransmitters at all of its synapses.


---
# Marshland ch1

## LEARNING
	Adapting weights for better performance

### TYPES OF LEARNING

#### supervised
	Output(actual) is compared to desired output(ideal)

#### unsupervised
	Input with similarities are categorized together

#### reinforcement
	Explorative search for ideal without being told what is explicitly off in output

### evolutionary
	Results compete agains others

## HEBBS LEARNING HYPOTHESIS
	Simoultaneous activation of neurons should have their connection strengthened and vice versa.
	deltaWij - xiyi
	if both activate, update weight by 1
	Else update by 0

## DIMENSIONALITY
		Number of elements in the input vector.

## WEIGHTS 
	Connections between neurons, analogue to synaptical connections.
	Arranged into the weight matrix W

## INPUT
	Each input in machine learning is multi-dimensional.
	If we are talking about image recognition we might have one value for each pixel as an input.
	Remember thus that inputs are vectors. 
	Each vector data item is passed to a neuron via synapses.
	Depending on the weight/strenghth of the synapse, the neuron will fire - or not.

## OUTPUT
	Corresponds to the number of output dimensions.
	As a memory rule, y(input, W)

## TARGETS
	the correct answers needed to perform supervised learning.

## ACTIVATION FUNCTION
	The mathematical function describing the firing of the neuron as a response to the weighed input.

## ERROR
	The difference between the ideal and actual.

## WEIGHT SPACE
	For each synapse in the neuronal network, there is one weight.
	Let there be one orthogonal axis for each weight.

## why machine learning
	If we, for every possible input vector had the output vector, we could just use a lookup table.
	That's infeasible though.
	The strength of machine learning is the ability to create a generalized solver.
	Given any input, you obtain a feasible - if not always perfect - result.

## REGRESSION
	To fit a mathematical function describing a curve so that the curve is as close as possible to all data points.
	Related to function approximation as well as interpolation

## THE CLASSIFICATION PROBLEM
	To take an input vector and decide which among N classes it belongs to.
	At it's easiest, a discrete problem, the set of classes cover the entire output space and are disjoint
	There are more fuzzy classification problems where output can belong to more than one class.

## NOVELTY DETECTION
	The functionality to detect divergent input.
	Consider an ANN trained to recognize cats based only on images of cats.
	If you input a dog, it will be classified as a cat since that is the best classifcation it can do.
	Novelty detection is intended to stop that kind of result.

## THE CURSE OF DIMENSIONALITY
	As the number of input dimensions grow, so do the number of data points required to train a network increase faster.

## How to use machine learning to solve a problem
-	Collect data for training (and eventually targets), hopefully clean.
-	Select features to use in the learning
-	Choose algorithm
-	Set parameters and model
-	Train the network
- 	Evaluate the result
