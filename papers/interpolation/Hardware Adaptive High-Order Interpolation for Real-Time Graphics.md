Citation: Lin, D., Seiler, L. and Yuksel, C. (2021), Hardware Adaptive High-Order Interpolation for Real-Time Graphics. Computer Graphics Forum, 40: 1-16.

#paper 
#skimmed 
#application 
#interpolation

Link: http://www.cemyuksel.com/research/papers/highorderinterpolation.pdf

Cited in:

Cites:
* [[Hardware accelerator for real-time image resizing]]

Notes:
The core idea of this paper is to break high-order image interpolation problems into a sequence of smaller bilinear interpolations. It can be shown, for example, that higher order bicubic interpolation problems can be written as a sum of a bilinear interpolation and some higher-order terms. The core idea is that the higher-order terms can be written as the difference between the desired value(s) of the intermediate control point(s) and the value produced by a linear interpolation. For example, the following equation gives the 1D cubic interpolation along an edge, with respect to a linear interpolation of the edge point terms $f(0)$ and $f(0)$ and the edge derivative terms $f_x(0)$, $f_x(1)$. Note that the notation is slightly different than in the paper.

$$C_4^{1D}(s) = L_2^{1D}(s)+(1-s)s\mathcal{L}_s^1(D_{\vec{0}}, D_{\vec{1}})$$
Where the difference terms are $D_{\vec{0}}=f_x(0)-(f(1)-f(0))$ and $D_{\vec{1}}=f_x(1)-(f(0)-f(1))$

By formulating the problem as multiple (bi)linear interpolations with extra scaling in between to achieve the higher order terms (eg. the $(1-s)s\mathcal{L}_s^1(D_{\vec{0}}, D_{\vec{1}})$ seen above), their technique allows a high degree of hardware re-use, and minimizes the performance impact of the high-order terms. 

I could be wrong, but I think the higher-order terms can be kept or discarded based on the value of $(1-s)s$, which means we can decide whether to compute $\mathcal{L}_s^1(D_{\vec{0}}, D_{\vec{1}})$. 

Unlike previous approaches like [[Hardware accelerator for real-time image resizing|this one]], their design "adaptively discards small high-order terms purely based on mathematical formulation of bicubic interpolation". The method is exact bicubic interpolation if the high-order terms are kept.