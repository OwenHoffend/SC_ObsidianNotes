While reading [[A Fast Fault-Tolerant Architecture for Sauvola Local Image Thresholding Algorithm Using Stochastic Computing|this paper]] I noticed how their 81-to-1 MUX-tree mean circuit, theoretically, requires a very long bitstream to produce accurate results, however theirs seem to be fine. I wonder if SC MUXes with a large number of inputs work well for early termination when most of the mass of the input value probability distribution is centered around 0 or 1 (as it would be for printed or handwritten digits, for example).

SC-based optical character recognition using early termination would be a really cool application
OCR pipeline is something like: 
Scan --> Threshold --> ROI --> CNN
What is the state of the art of scan-to-document type image processing pipelines?