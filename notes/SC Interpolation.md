It seems that Linear an Bilinear Interpolation can be very easily implemented in SC using MUXes, where the parameters $s$ and $t$  (defined in [[Interpolation]]) are used as inputs to MUXes, as shown:

(ADD figure here)

To perform image upscaling, we just have to define a good tile size and set the $s$ and $t$ constants appropriately based on the desired upscaling factor. 

(Example of doing this here)

