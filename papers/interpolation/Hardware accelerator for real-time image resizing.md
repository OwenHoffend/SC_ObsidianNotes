
P. N. Gour, S. Narumanchi, S. Saurav and S. Singh, "Hardware accelerator for real-time image resizing," _18th International Symposium on VLSI Design and Test_, Coimbatore, India, 2014, pp. 1-6

#paper 
#interpolation 
#unread
#application

Link: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6881070

Cited in: 
* [[Hardware Adaptive High-Order Interpolation for Real-Time Graphics]]

Cites:

Notes:
This paper mentions that Bicubic interpolation in the context of images uses a "cubic convolution kernel" that is applied to a 4x4 window. While it performs much better than bilinear interpolation, the problem with bicubic interpolation generally is one of computational complexity. An area of past research has been achieving "bicubic-like" quality with only bilinear-like complexity, usually by sacrificing some small amount of performance (approximate algorithms). There are a number of examples of prior work in this area:

* "Winscale, [6] ":
	* Uses an "area pixel model", wherein pixels are represented as blocks having area rather than as points, and performs bilinear interpolation on the area blocks.
* "Extended Linear [7]"
	* Performs interpolation on 16 surrounding pixels using a piecewise linear function that approximates a bicubic kernel. It comes close to the bicubic quality while avoiding the high cost. The following figure shows the linear approximation to the cubic function that was used:
	* ![[Pasted image 20230810154443.png]]

* "Modified Bicubic [8]"
	* Another approximation of the bicubic kernel which operates on 16 pixels. It uses pre-calculated coefficients stored in a table.

The main contribution of this paper is a linear approximation to the bicubic algorithm that uses four line segments. This one much more closely follows the cubic function's curve, as shown below
![[Pasted image 20230810154816.png]]

What does [[Hardware Adaptive High-Order Interpolation for Real-Time Graphics]] do to improve on this design? How is it different?
* Answer: This paper is only focused on super-resolution, so the "weight pattern is repeated across the whole image and only needs to be computed once". This paper also uses a linear approximation instead of an actual cubic function.
