# Reading Notes Chapter 1 & 2
## Questions / Future work
 - What is a heuristic method?
 - grid search
 - SWIG
 - how to grid search, cross-validation (scikit-learn estimator)
## Chapter1: Tensorflow basics
### General ideas and implementation principles
 - Kernel: specific hardware implementation for an op
 - Architecture
    - Client - Server - Worker
 - Difficulties for distributed system
     - Allocate devices: cost model (greedy vs RL)
     - Communication between computation nodes: split the graph into subgraphs according to devices that it is allocated to
 - Save and recover network status
    - Restore node -> Variable node -> Save node
### Advanced features
 - Execute a subgraph
 - Control flow
 - Queue
 - Container
### Optimization (parallism)
 - Data parallism: distribute data mini-batches to devices
    - sync(like using bigger mini-batch)
    - async
 - Model parallism: assign subgraphs to devices
 - Pipeline parallism

### My ideas
 - Most features are implemented by modifying the graph
    - adding helper nodes
        - save/restore
        - send/recv
        - derivative
        - feed/fetch
    - duplicate subgraphs
        - parallism
        - control flow

## Chapter 2: Comparison against other ML frameworks
### Tensorflow tips
 - grid search
### Keras
 - Advantage
    - based on tensorflow/theano
    - simplified, modulized
    - suitable for research
 - **Disadvantage**
    - lack multi-GPU support(which doesn't matter to me)
### Other frameworks
`caffe`,`theano`,`torch`,`cntk`
