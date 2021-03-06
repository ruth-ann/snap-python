GetInvParticipRat
'''''''''''''''''

.. function:: GetInvParticipRat(MaxEigVecs, TimeLimit)

A graph method that computes the inverse participation ratio of an undirected graph.

Parameters:

- *EigVecs*: int
    Maximum number of eigenvectors to return.

- *TimeLimit*: int
    Maximum number seconds to search.
    
Return value:

- *EigValIprV*: :class:`TFltPrV`, a vector of (float, float) pairs (output)
    The output inverse participation ratios.

See Spectra of "real-world" graphs: Beyond the semicircle law by Farkas, Derenyi, Barabasi and Vicsek  URL: http://arxiv.org/abs/cond-mat/0102335


The following example computes the inverse participation ratio for :class:`TUNGraph`::

 import snap
 
 UGraph = snap.TUNGraph.New()
 UGraph.AddNode(1)
 UGraph.AddNode(2)
 UGraph.AddNode(3)
 UGraph.AddNode(4)
 UGraph.AddNode(5)
 UGraph.AddNode(6)
 UGraph.AddEdge(1, 2)
 UGraph.AddEdge(2, 3)
 UGraph.AddEdge(3, 5)
 UGraph.AddEdge(4, 6)
 UGraph.AddEdge(4, 1)

 EigValIprV = UGraph.GetInvParticipRat(20, 1000)
 for item in EigValIprV:
     print('%f, %f' % (item.GetVal1(), item.GetVal2()))

