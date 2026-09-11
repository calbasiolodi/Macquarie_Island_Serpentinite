# Macquarie_Island_Serpentinite (CV and modal quantification of alteration patches)
A variety of case studies on Macquarie Island datasets. This spans from experimental applications of lean PyTorch models to identify alteration textures to QC adided by scikit-learn PCA. In this specific project we focus on computer vision (CV) with PyTorch.

## Weathering as a predictor of element transfer
Weathering is known to mobilise specific elements: most importantly sulphur, calcium, iron and magnesium. In addition, trace elements such as As, Pb and Cd are exceptionally mobile and extremely important to track for enviromental management.

The focus is on utilising a lean PyTorch model to recognise alteration, in this case weathering (that can be trained quickly without GPU and run locally) with a small training dataset. 

Weathering in mining overall is important to track for environmental purposes: acid mine drainage (and metal leaching). It is also useful in prospectivity studies and OBK for vectoring of supergene deposits, laterite and bauxite.

<figure>
  <img width="3500" height="1889" alt="MQ1716-030-PPL-smaller-size" src="https://github.com/user-attachments/assets/d78638ae-4f3f-4d66-b95c-2c8e61f28e9b">
  <figcaption><i>Figure 1: A whole thin section scan from Macquarie Island (Southern Ocean, Australia) showing extensive weathering in the form for of reddish-brown iddingsite patches.</i></figcaption>
</figure>

### Example of training process
The pipeline is relatively simple: first the alteration area is manually selected in FIJI with a color threshold then refined manually by adding/removing the relevant areas in the pictures. The hidden laers use a combination of linear laers and leakyReLU to prevent neuron from shutting down, together with Adam opitimizer with a lr set to 0.001. Then a binary mask displaying what the model needs to recognise is outputted with the standard Sigmoid() function as we need only a binary classification: altered vs. pristine.

<img width="512" height="512" alt="1702-01300" src="https://github.com/user-attachments/assets/121273d7-ca9e-4a05-90ab-91e95b814ba4" />
<figcaption>A thin section from another sample (MQ17-02). This is one of the training images. Of course the scale has been removed :)</figcaption>

Afterwards a simple PyTorch model with UNet with ResNet18 underlying structure is implemented. The Epoch number is set at 10. The output is a binary map (boolean), displaying the altered vs the non-altered portions on another picture (test dataset) from the same sample not spatially contiguous with the training data.
