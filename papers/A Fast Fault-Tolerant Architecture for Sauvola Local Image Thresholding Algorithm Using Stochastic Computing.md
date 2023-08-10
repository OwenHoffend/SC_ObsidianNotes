Citation: M. H. Najafi and M. E. Salehi, "A Fast Fault-Tolerant Architecture for Sauvola Local Image Thresholding Algorithm Using Stochastic Computing," in _IEEE Transactions on Very Large Scale Integration (VLSI) Systems_, vol. 24, no. 2, pp. 808-812, Feb. 2016

Link: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7104144

#paper
#application
#image_processing
#read

Cited in:
* [[A Fast Fault-Tolerant Architecture for Sauvola Local Image Thresholding Algorithm Using Stochastic Computing]]
* [[Mean Circuit Design Using Correlated Random Bitstreams in Stochastic Computing]]
* [[Remodelling correlation - A fault resilient technique of correlation sensitive stochastic designs]]

Cites: [[]]

Notes:
The problem they are trying to solve is to threshold document scans to identify character/not-character pixels. The issue is that scanned documents often have non-uniform illumination, in which cases a global threshold doesn't work well. Here, they use an algorithm called Sauvola thresholding, which does a "Local" threshold instead. 

Their architecture implements this equation to determine what the threshold for a WxW pixel window should be:
![[Pasted image 20230802232712.png]]
Where $m(x,y)$ is the mean, and $s(x,y)$ is the standard deviation of the pixel window. K is a constant and R is the maximum standard deviation possible (128 for gray-scale documents).

Their circuit implementing this function looks like this:
![[Pasted image 20230802234852.png]]
They use the formula $\sqrt{|mean(x^2)-mean(x)^2|}$  to compute the std. dev. This circuit is notable because it is an example of a multi-layer image processing circuit that utilizes correlation on an internal layer. The authors say that using the same select pattern for both of the stochastic mean circuits gives enough correlation for the XOR gate to work as an absolute-valued-subtractor. **This is probably not a good application of COMAX due to the sequential logic involved, but it's an interesting application.**