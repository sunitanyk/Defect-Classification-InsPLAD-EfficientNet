# Defect-Classification-InsPLAD-EfficientNet
Given the detected power line asset image, it is classified according to its current conditions e.g. good or rust.


 ## **Dataset**

The InsPLAD-fault dataset from the 2023 paper “*[InsPLAD: A Dataset and Benchmark for Power Line Asset Inspection in UAV Images](https://arxiv.org/abs/2311.01619)*” was used. The fault classification dataset included data augmented using Albumentations library Buslaev et al. (2020) to increase the training data by 10 times wherever needed. Augmentations included changes in brightness, contrast, histogram equalization, PCA color augmentation, rotation, horizontal mirroring, sharpening and blurring. 
 
## **Classifier**

EfficientNet-B0 was used as the classifier for defect detection. EfficientNet is designed to be lightweight and computationally efficient. This is crucial for applications with limited hardware resources or when real-time processing is required, such as on mobile devices or edge computing platforms. Its pre-trained weights and ability to leverage transfer learning make it a practical solution, particularly for datasets with potentially limited samples.

## **Results**


<table>
  <tr>
   <td>Defect Class
   </td>
   <td>Number of Training Samples Used
   </td>
   <td>Number of Testing Samples Used
   </td>
   <td>Balanced Accuracy
   </td>
  </tr>
  <tr>
   <td>Polymer-insulator-upper-shackle
   </td>
   <td>Good: 742
<p style="text-align: center">
Rust:  740
   </td>
   <td>Good: 33
<p style="text-align: center">
Rust:  31
   </td>
   <td>93.94%
   </td>
  </tr>
  <tr>
   <td>Lightning-rod-suspension
   </td>
   <td>Good: 348
<p style="text-align: center">
Rust:  310
   </td>
   <td>Good: 231
<p style="text-align: center">
Rust: 20
   </td>
   <td>97.28%
   </td>
  </tr>
  <tr>
   <td>Glass-insulator
   </td>
   <td>Good: 691
<p style="text-align: center">
Missing-Cap: 690
   </td>
   <td>Good: 29
<p style="text-align: center">
Missing-Cap: 30
   </td>
   <td>83.22%
   </td>
  </tr>
</table>



## **Detailed Class Reports**


### **Polymer-insulator-upper-shackle**

**Class Labels:** Good, Rust    
**Balanced Accuracy:** 93.94%


<table>
  <tr>
   <td>Confusion Matrix
   </td>
   <td>Precision-Recall Curve
   </td>
  </tr>
  <tr>
   <td>
<img src="images/polymer-insulator-upper-shackle_confusion_matrix.png" width="">
   </td>
   <td>
<img src="images/polymer-insulator-upper-shackle_precision_recall_curve.png" width="">
   </td>
  </tr>
</table>



#### **Correctly Classified Example Images**


<table>
  <tr>
   <td>True: Rust \
Predicted: Rust
   </td>
   <td>True: Rust \
Predicted: Rust
   </td>
   <td>True: Good \
Predicted: Good
   </td>
   <td>True: Good \
Predicted: Good
   </td>
  </tr>
  <tr>
   <td>
<img src="images/polymer-insulator-upper-shackle_correct_0_true_rust_pred_rust_01-06-2021_DJI_0547_159.jpg" width="" alt="alt_text" title="image_tooltip">
  </td>
   <td>
<img src="images/polymer-insulator-upper-shackle_correct_3_true_rust_pred_rust_11-06-2021_DJI_0142_7.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
   <td>

<img src="images/polymer-insulator-upper-shackle_correct_1_true_good_pred_good_Fotos 20-10-2020_DJI_0229_manilha_isolador_superior_1296.jpg" width="">

   </td>
   <td>
<img src="images/polymer-insulator-upper-shackle_correct_4_true_good_pred_good_Fotos 02-12-2020_DJI_0351_manilha_isolador_superior_160.jpg" width="">
   </td>
  </tr>
</table>


				


#### **Misclassified Example Images**


<table>
  <tr>
   <td>True: Rust \
Predicted: Good
   </td>
   <td>True: Rust \
Predicted: Good
   </td>
  </tr>
  <tr>
   <td>
<img src="images/polymer-insulator-upper-shackle_misclassified_3_true_rust_pred_good_Fotos 23-10-2020_DJI_0118_manilha_isolador_superior_1401.jpg" width="">
   </td>
   <td>
<img src="images/polymer-insulator-upper-shackle_misclassified_2_true_rust_pred_good_01-06-2021_DJI_0587_166.jpg" width="">
   </td>
  </tr>
</table>


			


### **Lightning-rod-suspension**

**Class Labels:** Good, Rust     
**Balanced Accuracy:** 97.28% 


<table>
  <tr>
   <td>Confusion Matrix
   </td>
   <td>Precision-Recall Curve
   </td>
  </tr>
  <tr>
   <td>
<img src="images/lightning-rod-suspension_confusion_matrix.png" width="">
   </td>
   <td>
<img src="images/lightning-rod-suspension_precision_recall_curve.png" width="">
   </td>
  </tr>
</table>



#### **Correctly Classified Example Images**


<table>
  <tr>
   <td>True: Good \
Predicted: Good
   </td>
   <td>True: Good \
Predicted: Good
   </td>
   <td>True: Rust \
Predicted: Rust
   </td>
   <td>True: Rust \
Predicted: Rust
   </td>
  </tr>
  <tr>
   <td>
<img src="images/lightning-rod-suspension_correct_0_true_good_pred_good_Fotos 18-11-2020_DJI_0079_suspensao_para_raio_375.jpg" width="">
   </td>
   <td>
<img src="images/lightning-rod-suspension_correct_2_true_good_pred_good_Fotos 19-11-2020_DJI_0195_suspensao_para_raio_392.jpg" width="">
   </td>
   <td>
<img src="images/lightning-rod-suspension_correct_true_rust_pred_rust_08-06-2021_DJI_0320_396.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
   <td>
<img src="images/lightning-rod-suspension_correct_true_rust_pred_rust_09-06-2021_DJI_0058_456.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
  </tr>
</table>

#### **Misclassified Example Images**

<table>
  <tr>
   <td>True: Rust \
Predicted: Good
   </td>
   <td>True: Good \
Predicted: Rust
   </td>
  </tr>
  <tr>
   <td>
<img src="images/lightning-rod-suspension_misclassified_0_true_rust_pred_good_01-06-2021_DJI_0190_57.jpg" width="">
   </td>
   <td>
<img src="images/lightning-rod-suspension_misclassified_1_true_good_pred_rust_Fotos 23-11-2020_DJI_0037_suspensao_para_raio_609.jpg" width="">
   </td>
  </tr>
</table>


		


### **Glass-insulator**

**Class Labels:** Good, Missing-Cap     **Balanced Accuracy:** 93.94%


<table>
  <tr>
   <td>Confusion Matrix
   </td>
   <td>Precision-Recall Curve
   </td>
  </tr>
  <tr>
   <td>
<img src="images/glass-insulator_confusion_matrix.png" width="" alt="alt_text" title="image_tooltip">
   </td>
   <td>
<img src="images/glass-insulator_precision_recall_curve.png" width="" alt="alt_text" title="image_tooltip">
   </td>
  </tr>
</table>



#### **Correctly Classified Example Images**


<table>
  <tr>
   <td>True: Good \
Predicted: Good
   </td>
   <td>True: Good \
Predicted: Good
   </td>
   <td>True: Missing-cap \
Predicted: Missing-cap
   </td>
   <td>True: Missing-cap \
Predicted: Missing-cap
   </td>
  </tr>
  <tr>
   <td>
<img src="images/glass-insulator_correct_true_good_pred_good_Fotos 16-11-2020_DJI_0018_cadeia_isolador_vidro_1497.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
   <td>
<img src="images/glass-insulator_correct_1_true_good_pred_good_Fotos 27-11-2020_DJI_0171_cadeia_isolador_vidro_2552.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
   <td>
<img src="images/glass-insulator_correct_2_true_missing-cap_pred_missing-cap_Fotos 08-12-2020_DJI_0378_cadeia_isolador_vidro_1422.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
   <td>
<img src="images/glass-insulator_correct_3_true_missing-cap_pred_missing-cap_Fotos 25-11-2020_DJI_0449_cadeia_isolador_vidro_1776.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
  </tr>
</table>


				


#### **Misclassified Example Images**


<table>
  <tr>
   <td>True: Missing-cap \
Predicted: Good
   </td>
   <td>True: Missing-cap \
Predicted: Good
   </td>
  </tr>
  <tr>
   <td>
     <img src="images/glass-insulator_misclassified_2_true_missing-cap_pred_good_Fotos 21-10-2020_DJI_0538_cadeia_isolador_vidro_1616.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
   <td>
    <img src="images/glass-insulator_misclassified_4_true_missing-cap_pred_good_Fotos 03-12-2020_DJI_0557_cadeia_isolador_vidro_698.jpg" width="" alt="alt_text" title="image_tooltip">
   </td>
  </tr>
</table>



### **Future Improvements**

Higher level EfficientNets(B1-B7) can be experimented with to achieve higher accuracy. With access to a bigger and diverse dataset and more training resources, richer models using Vision Transformers can be trained to further improve accuracy.
