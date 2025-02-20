# ✍️ **Signature Forgery Detection System**  

## 📋 **Overview**  
The system uses a neural network to detect signature forgery by analyzing features such as ratio, centroid, eccentricity, solidity, skewness, and kurtosis from signature images. It processes genuine and forged signature images, extracts key features, and trains a neural network to classify them.

## 🗂️ **Code Structure**  
### 📦 **Libraries Used:**  
- 🧮 `numpy` - Numerical operations  
- 💾 `os` - File handling  
- 📊 `matplotlib` - Image visualization  
- 🧩 `scipy.ndimage` - Image processing  
- 🖼️ `skimage` - Image reading and thresholding  
- 🤖 `tensorflow` - Neural network training  
- 🗃️ `pandas` - Data manipulation

### 🧩 **Functions:**  
- 🎨 **`rgbgrey(img)`**: Converts RGB to grayscale  
- ⚫ **`greybin(img)`**: Converts grayscale to binary  
- 🖼️ **`preproc(path, img=None, display=True)`**: Preprocesses signature images  
- 📏 **`Ratio(img)`**: Calculates pixel ratio  
- 📍 **`Centroid(img)`**: Calculates image centroid  
- 📐 **`EccentricitySolidity(img)`**: Extracts eccentricity and solidity  
- 📈 **`SkewKurtosis(img)`**: Measures skewness and kurtosis  
- 🗂️ **`getFeatures(path, img=None, display=False)`**: Extracts features from images  
- 📝 **`getCSVFeatures(path, img=None, display=False)`**: Saves features in CSV format  
- 🗃️ **`makeCSV()`**: Creates training and testing datasets  
- 🧩 **`testing(path)`**: Generates features for a single image  
- 📜 **`readCSV(train_path, test_path, type2=False)`**: Reads CSV data  
- 🧠 **`multilayer_perceptron(x)`**: Defines the neural network  
- 📊 **`evaluate(train_path, test_path, type2=False)`**: Trains and evaluates the model  
- 🚀 **`trainAndTest(rate=0.001, epochs=1700, neurons=7, display=False)`**: Runs training and testing

## ⚙️ **Workflow:**  
1. 🖼️ **Image Preprocessing:** Converts and extracts the signature part  
2. 📏 **Feature Extraction:** Calculates image properties  
3. 🗃️ **Data Preparation:** Stores features in CSV files  
4. 🧠 **Model Training:** Uses extracted features as input  
5. 🧩 **Evaluation:** Tests model performance on datasets

## 💻 **Usage:**  
1. 📁 **Prepare Data:** Store signature images in `real` and `forged` folders  
2. 📝 **Create CSV Files:** Run `makeCSV()` to generate datasets  
3. 🤖 **Train and Evaluate:** Use `trainAndTest()` to start training  
4. 📸 **Single Image Test:** Use `testing(path)` to evaluate one image  
5. ⚙️ **Customization:** Modify neural network structure in the code

## 💡 **Example:**  
```python
# Generate CSV files
makeCSV()

# Input test data
train_person_id = input("Enter person's ID: ")
test_image_path = input("Enter image path: ")

# Paths for training and testing
train_path = 'Features/Training/training_' + train_person_id + '.csv'
testing(test_image_path)
test_path = 'TestFeatures/testcsv.csv'

# Train and evaluate the model
train_accuracy, test_accuracy, evaluation_time = trainAndTest()

print("✅ Training Accuracy:", train_accuracy)
print("✅ Testing Accuracy:", test_accuracy)
print("⏱️ Time Taken:", evaluation_time)
```

## 📝 **Conclusion:**  
This system provides an efficient way to detect signature forgeries using neural networks. The modular code structure allows easy customization of neural network parameters, offering flexibility for different datasets.

