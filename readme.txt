This package was used to optimize the rsCC-specific pathways.

Step 1: gridsearch was used to find a group of optimal parameters for the objective function(see manuscript)

a reasonable group of papameters is alp=[20,2,10,1,1];

Step 2: call the function "intmodel.m"

Formate:  [dif,rst] = intmodel(alp,[54,104,76],sig_rec,met_rec,sig_mstid',sig_mst',meta_mstid',meta_mst');

54 is the number of proteins in the signaling part.
104 is the number of metabolites in the network,
76 is the number of metabolic reactions.

sig_rec: all the details of signaling reactions.
met_rec: all the details of metabolic reactions.
sig_mstid: the index of measured signaling proteins
sig_mst: the expressions of measured signaling proteins
meta_mstid: the index of measured metabolites.
meta_mst: the expressions of measrued metabolites.

rst is the optimal solution.
rst is a structure, all the predicted elements invovled in the whole network were stored in rst.x.

Now, the length of rst.x is 510. what's the meaning:

54 signaling proteins
104 metablites
76 metabolic reactions
92 signaling reactions
76 flux
76 DeltaG
16 the positve directions
16 the negative directions

total is 510.

you can obtain all the predicted values of metabolic enzymes as rst.x(54+104+(1:76))
