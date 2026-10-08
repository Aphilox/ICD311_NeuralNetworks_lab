IMAGE          TRUE          PREDICTED          PLAUSIBLE REASON
Shirt          Shirt         T.shirt/top        Similar silhouette and low resolution
Pullover       Pullover      Coat               Both upper-body garments with similar shape
Sneaker        Sneaker       Sandal             The 28x28 grayscale resolution makes the flat sole and upper profile of a sneaker look very similar to a                                                        sandal. The MLP lacks spatial awareness to distinguish fine details.



\## Real-World Inference Test



In addition to the Fashion-MNIST test set, I tested the model on custom, real-world images (a bag, a regular shoe, and an inverted black-and-white shoe). 



| Image | True Label | Predicted Label | Confidence | Plausible Reason |

|---|---|---|---|---|

| Bag | Bag | Sandal | 1.00 | The model expects white objects on black backgrounds. The bag did not match the training distribution. |

| Shoe | Sneaker | Sandal | 1.00 | Domain shift: The model relies on pixel intensity patterns, not spatial shape. It flattened the image and could not recognize the shoe's structure. |

| Inverted Shoe | Sneaker | Sandal | 1.00 | Even with color inversion, the MLP lacks spatial awareness. It cannot recognize edges, curves, or laces. |



\*\*Conclusion:\*\* The MLP failed on all real-world images. This demonstrates that a simple MLP is not robust to domain shifts (changes in background, lighting, or angle). It also proves that flattening an image destroys critical spatial information. For real-world computer vision, a Convolutional Neural Network (CNN) is required.

