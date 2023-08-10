H. Abdellatef, A. Abdellatif and N. Ramaha, "A New Correlation Manipulation Circuit for Stochastic Computing," _2022 International Conference on Smart Systems and Power Management (IC2SPM)_, Beirut, Lebanon, 2022, pp. 182-186

Link: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9988884

#paper 
#unread 
#correlation_theory

Cited in:
* 

Cites: 

Notes:
Doesn't have very many views and zero citations

This paper is another by the Abdellatef group that improves upon their earlier 2019 work (REF) on sequential correlation manipulating circuits (which I referenced in the COMAX paper). Fundamentally, both designs function similarly: They both dynamically estimate which bitstream (of two) is the minimum and which is the maximum, then they detect the cases where there is a 1 on the min bitstream but not on the max bitstream (which should never happen if SCC=1). They count how many such cases have been seen, then relocate the 1s as necessary to increase the correlation. It seems that the main difference between this paper and their 2019 work is that they are using a counter-based method to dynamically estimate which bitstream is the min/max, instead of just relying on using the first 1-0 pair to determine which is min/max, like their earlier method. This was a major design flaw in their earlier method because it only works when the bitstreams are sufficiently correlated already, which was one of the reasons I chose not to compare against it in the results section of the COMAX paper. The authors compare their newest design against the FSM design from V. Lee (REF), but notably they do not compare against their own 2019 work (REF) in the results section. Maybe this is because they realize their own past design is flawed.

Given the improvements they’ve made, I’d probably compare COMAX against this new 2022 design as well in a future revision of our paper. This could be the paper that the reviewer meant when they said that a previous work was missing from the reference list. Like we discussed last time, I’d probably leave out specific details about how the FSM is constructed from the paper (removing the background section on the FSMR), and include a table of results produced by various recorrelator types.