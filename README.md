# Macquarie_Island_Serpentinite
A variety of case studies on Macquarie Island datasets. This spans from experimental applications of lean PyTorch models to identify alteration textures to QC adided by scikit-learn PCA.




## Weathering as a predictor of element transfer
Weathering is known to mobilise specific elements: most importantly sulphur, calcium, iron and magnesium. In addition, trace elements such as As, Pb and Cd are exceptionally mobile and extremely important to track for enviromental management.

The focus is on utilising a lean PyTorch model to recognise alteration, in this case weathering (that can be trained quickly without GPU and run locally) with a small training dataset. 

Weathering in mining overall is important to track for environmental purposes: acid mine drainage (and metal leaching). It is also useful in prospectivity studies and OBK for vectoring of supergene deposits, laterite and bauxite.

<img width="3500" height="1889" alt="MQ1716-030-PPL-smaller-size" src="https://github.com/user-attachments/assets/d78638ae-4f3f-4d66-b95c-2c8e61f28e9b" />
<figcaption>A whole thin section scan from Macquarie Island (Southern Ocean, Australia) showing extensive weathering in the form for of reddish-brown iddingsite patches.</figcaption>
