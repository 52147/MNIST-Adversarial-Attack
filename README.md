# Exploring FGSM-Based Adversarial Attacks on MNIST Using a CNN Model
📌 View on Google Colab: [Open in Colab](https://colab.research.google.com/drive/1uUv4ZUmC4bHE-VUgj6Xb3_U29QvScT2l?usp=sharing)


**Abstract:**
This study explores the application of the Fast Gradient Sign Method (FGSM) in adversarial attacks on a Convolutional Neural Network (CNN) trained on the MNIST dataset. By applying perturbations at varying epsilon (ε) values, we assess the model's robustness against adversarial examples. Our findings illustrate a significant drop in classification accuracy as ε increases, highlighting the vulnerability of deep learning models to adversarial perturbations.

---

**1. Introduction**
Deep learning models have demonstrated remarkable success in image classification tasks. However, these models are vulnerable to adversarial attacks, where small perturbations to input images can drastically alter predictions. This paper investigates the impact of FGSM-based adversarial attacks on a CNN trained on MNIST, examining the effect of different ε values on classification accuracy.

---

**2. Methodology**

**2.1 Dataset & Model Architecture**
We use the MNIST dataset, consisting of 60,000 training and 10,000 test grayscale images of handwritten digits (0-9). Our CNN model comprises two convolutional layers, each followed by ReLU activation and max-pooling, and two fully connected layers for final classification.

**2.2 Fast Gradient Sign Method (FGSM)**
FGSM generates adversarial examples by adding a perturbation to the input image, computed as:
![公式](https://latex.codecogs.com/svg.latex?X_{adv}%20=%20X%20+%20\epsilon%20\cdot%20\operatorname{sign}(\nabla_X%20L(X,%20y)))
where \( X \) is the original image, \( L \) is the loss function, and \( ε \) controls perturbation magnitude.

**2.3 Experiment Setup**
- The model was pre-trained on MNIST with standard cross-entropy loss and Adam optimizer.
- We applied FGSM attacks with ε values: \(0, 0.05, 0.1, 0.2, 0.3, 0.4, 0.5\).
- We evaluated model accuracy on adversarially perturbed test images.
- We visualized attack effectiveness using accuracy curves and sample adversarial images.

---

**3. Results and Analysis**

**3.1 Accuracy Degradation under FGSM Attacks**
As ε increases, classification accuracy decreases significantly:
- **ε = 0.0**: 100% accuracy (clean images)
- **ε = 0.1**: ~85% accuracy
- **ε = 0.2**: ~40% accuracy
- **ε = 0.3**: ~10% accuracy
- **ε = 0.5**: <5% accuracy

The relationship follows a non-linear downward trend, demonstrating the increasing severity of attacks with larger perturbations.

**3.2 Visualizing Adversarial Examples**
We present adversarial samples across different ε values. For small perturbations (ε = 0.05), images retain their original form, and predictions remain mostly correct. However, at higher ε values, distortions become prominent, and misclassification rates increase dramatically.

---

**4. Conclusion**
Our results confirm that even a simple attack like FGSM can significantly degrade CNN performance. As ε increases, the adversarial effect intensifies, reducing classification accuracy. These findings highlight the necessity for adversarial training and robust model defenses in real-world applications.

---

**5. Future Work**
Future studies may explore:
- Adversarial training to improve model robustness.
- Other attack methods such as PGD or CW attacks.
- Defense mechanisms like defensive distillation or input preprocessing.

---

**References**
- Ian J. Goodfellow et al., "Explaining and Harnessing Adversarial Examples," ICLR 2015.
- Papernot et al., "The Limitations of Deep Learning in Adversarial Settings," IEEE European Symposium on Security and Privacy, 2016.

