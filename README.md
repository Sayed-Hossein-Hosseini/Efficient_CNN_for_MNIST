# Efficient CNN for MNIST

This project presents the design and implementation of a lightweight Convolutional Neural Network (CNN) for handwritten digit classification using the MNIST dataset.

---

## 🎯 Project Goal

Design a model with the **minimum possible number of parameters** while achieving acceptable classification accuracy (around 98% or higher) on MNIST. **Pretrained models are not allowed** in this project.

---

## ⚡ LightCNN Model Specifications

The final implemented model, called **LightCNN**, has a simple and highly efficient structure:

* **Total Parameters:** Approximately 6,000
* **Test Accuracy:** Around 98%
* **Architecture Details:**

  * 1st Convolutional Layer: 8 filters, kernel size 3x3 → Output: 8x28x28
  * 2nd Convolutional Layer: 16 filters, kernel size 3x3 → Output: 16x14x14
  * 3rd Convolutional Layer: 32 filters, kernel size 3x3 → Output: 32x7x7
  * Global Average Pooling Layer → Output: 32x1x1
  * Final Fully Connected Layer: 32 inputs → 10 outputs (MNIST classes)

> Instead of using large fully connected layers, this model leverages **Global Average Pooling** to reduce parameters and improve efficiency.

---

## 📊 Comparison with Reference Architectures

To evaluate performance, LightCNN is compared with two lightweight and two heavyweight reference models for MNIST.

| Model                                                              | Parameters  | Test Accuracy |
| ------------------------------------------------------------------ | ----------- | ------------- |
| Ultra-Light Model with \~210 parameters                            | \~210       | \~74%         |
| Medium Model with \~3,000 parameters                               | \~3,000     | \~92%         |
| **Heavyweight CNN (Classic \~80,000 params)**                      | \~80,000    | \~99%         |
| **Heavyweight 3-Layer Fully Connected Network (\~120,000 params)** | \~120,000   | \~99.2%       |
| **Proposed LightCNN**                                              | **\~6,000** | **\~98%**     |

> As seen, LightCNN achieves impressive \~98% accuracy with significantly fewer parameters compared to heavyweight models, while outperforming ultra-lightweight designs.

---

## 🏁 How to Run

### Requirements:

* Python 3.x
* PyTorch
* torchvision

### Model Training:

```python
model = LightCNN()
# Define optimizer and loss function
# Load data and train model (see notebook for details)
```

### Model Testing:

After training, the model achieves approximately 98% accuracy on the test set.

---

## 🔬 Advantages & Highlights

✅ Optimized design with minimal layers<br>
✅ Eliminates heavy fully connected layers using Global Average Pooling<br>
✅ Suitable for resource-constrained devices (e.g., mobile, embedded)<br>
✅ Achieves high accuracy with a compact architecture<br>
✅ Thorough comparison with both lightweight and heavyweight models, demonstrating excellent performance with significantly fewer parameters<br>

---

## ⚠️ Limitations

* Achieving >99% accuracy requires increased complexity and parameters
* Current architecture is optimized for MNIST and may not generalize to more complex datasets

---

## ✨ Conclusion

This project demonstrates that with careful design, it's possible to build an extremely lightweight network that provides high accuracy (\~98%) on MNIST.

Comparisons with both lightweight and heavyweight architectures confirm that excellent performance can be achieved without significantly increasing complexity.

---

## 📝 License

This project is licensed under the **MIT License**.

---

**Author:** Sayyed Hossein Hosseini DolatAbadi
