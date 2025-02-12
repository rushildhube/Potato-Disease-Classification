### **1. What is the Project About?**  

This project is a **Flask-based web application** that classifies **potato leaf diseases** using a **deep learning model trained with TensorFlow**.  

#### **Purpose:**  
The goal of this project is to assist farmers and researchers in identifying potato plant diseases early, enabling better crop management and yield improvement.  

#### **How It Works:**  
1. Users **upload an image** of a potato leaf through the web interface.  
2. The **trained CNN model** processes the image and classifies it into one of the following categories:  
   - **Healthy**  
   - **Potato Early Blight**  
   - **Potato Late Blight**  
3. The model returns the **predicted disease label and confidence score** to the user.  
4. The interface displays the **uploaded image, prediction results, and confidence percentage**.  

This application integrates **Flask for the backend**, **Bootstrap for UI**, and **TensorFlow for deep learning-based image classification**. 🚀

### **2. Features**  

✅ **User-Friendly Web Interface** – Upload an image and get instant predictions.  
✅ **Deep Learning-Based Image Classification** – Uses a trained **CNN model** for accurate results.  
✅ **Displays Confidence Score** – Shows how confident the model is about its prediction.  
✅ **Responsive Design** – Built with **Bootstrap** for a clean and mobile-friendly UI.  
✅ **Flask Backend** – Handles image uploads and predictions efficiently.  
✅ **Supports Multiple Image Formats** – Accepts `.jpg`, `.jpeg`, and `.png` files.  
✅ **Jupyter Notebooks for Model Training and Testing** – Easily train and test new models.  
✅ **Secure File Handling** – Ensures only valid image files are processed.  
✅ **Expandable and Customizable** – Can be modified to classify other crop diseases in the future.  

### **3. Technology Used**  

🔹 **Flask** – Web framework for handling backend logic and request routing.  
🔹 **TensorFlow 2.10** – Deep learning library used for model training and prediction (GPU support enabled).  
🔹 **Bootstrap** – Frontend framework for a responsive and modern user interface.  
🔹 **HTML/CSS/JavaScript** – Used for designing the web interface and enhancing user experience.  
🔹 **Jupyter Notebook** – For training and testing the machine learning model.  
🔹 **Werkzeug** – Assists in secure file handling and uploads.  
🔹 **NumPy** – Handles numerical operations for image processing and model input preparation.  
🔹 **Matplotlib** – Used for data visualization and plotting model performance.  
🔹 **Scikit-learn (sklearn)** – Used for preprocessing, evaluation metrics, and model performance analysis.  

### **4. Python Libraries Used**  

Ensure the following libraries are installed before running the project:  
```sh
pip install flask 
pip install tensorflow==2.10
pip install numpy 
pip install scikit-learn
pip install matplotlib, seaborn
```

### **5. Folder Structure**  

```
├── app.py                  # Flask application entry point
├── model.keras             # Pretrained model weights
├── static/                 # Temporary storage for user uploads
├── templates/
│   └── index.html          # Main UI template with Bootstrap
├── Training.ipynb          # Model training notebook
├── Testing.ipynb           # Model evaluation notebook
├── requirements.txt        # Dependency list
└── README.md               # Documentation
```

### **6. Installation, Training, and Running the Project**  

#### **Prerequisites**  
Before running the project, make sure you have the following installed and ready:
- **Python 3.x** (Recommended: Python 3.8 or later)
- **TensorFlow 2.10** (Ensure you install the correct version, especially for GPU support if needed)
- **A trained model (`model.keras`)** (or train your own using the steps below)
- **A stable internet connection** (for installing dependencies and downloading datasets if needed)
- **A working GPU (Optional but recommended)** for faster training

---
### **Step 1: Clone the Repository**
First, download the project files by cloning the GitHub repository or manually downloading them.
```sh
# Clone the repository
git clone https://github.com/your-repo/crop-disease-classification.git

# Navigate to the project folder
cd crop-disease-classification
```

---
### **Step 2: Set Up the Virtual Environment (Recommended)**
Creating a virtual environment helps keep dependencies organized.
```sh
# Create a virtual environment (optional but recommended)
python -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

---
### **Step 3: Install Dependencies**
Install the required Python libraries using the `requirements.txt` file.
```sh
pip install -r requirements.txt
```
Alternatively, you can install dependencies manually:
```sh
pip install flask tensorflow==2.10 numpy scikit-learn matplotlib seaborn werkzeug
```

---
### **Step 4: Prepare the Dataset**
If you want to train the model from scratch, you need a dataset of potato leaf images.
- The dataset should contain images classified into **Healthy**, **Potato Early Blight**, and **Potato Late Blight**.
- You can use the **PlantVillage dataset** or any other reliable dataset.
- Store images in separate folders inside a main dataset folder (e.g., `dataset/train` and `dataset/test`).

Example structure:
```
├── dataset/
│   ├── train/
│   │   ├── Healthy/
│   │   ├── Early_Blight/
│   │   ├── Late_Blight/
│   ├── test/
│   │   ├── Healthy/
│   │   ├── Early_Blight/
│   │   ├── Late_Blight/
```

---
### **Step 5: Train the Model**
To train the deep learning model, run the **Training.ipynb** Jupyter notebook.

#### **Using Jupyter Notebook**
1. Open Jupyter Notebook:
   ```sh
   jupyter notebook
   ```
2. Navigate to `Training.ipynb` and open it.
3. Run each cell step by step:
   - Load and preprocess the dataset.
   - Define and compile the CNN model.
   - Train the model using the dataset.
   - Save the trained model as `model.keras`.
4. After training, ensure that the `model.keras` file is saved in the main directory.

#### **Alternative: Train Using Python Script**
If you prefer running training as a Python script, execute the following command:
```sh
python Training.py
```
Make sure `Training.py` contains all necessary preprocessing, training, and saving steps.

---
### **Step 6: Test the Model (Optional but Recommended)**
To verify the model's accuracy before deploying it:
1. Open the `Testing.ipynb` notebook in Jupyter Notebook.
2. Run all the cells to:
   - Load the trained model (`model.keras`)
   - Test the model using test images.
   - View accuracy, confusion matrix, and predictions.

---
### **Step 7: Run the Flask Web Application**
Now that you have a trained model, you can start the Flask server to make predictions.
```sh
python app.py
```
If the server starts successfully, you will see an output like this:
```
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

---
### **Step 8: Access the Web Application**
Open your browser and go to:
```sh
http://127.0.0.1:5000/
```

- Upload a **potato leaf image**.
- Click on **Predict**.
- The application will display the **Predicted Disease Class** and **Confidence Score**.

---
### **Troubleshooting & Common Issues**
#### **1. Flask App Not Running?**
- Ensure you have all dependencies installed (`pip install -r requirements.txt`).
- Check for errors in `app.py`.
- If using a virtual environment, activate it before running.

#### **2. Model Not Found?**
- Ensure `model.keras` is in the project directory.
- If missing, retrain the model using `Training.ipynb`.

#### **3. CUDA/GPU Not Working?**
- Ensure TensorFlow is installed correctly (`pip list | grep tensorflow`).
- Check if your GPU supports TensorFlow (`nvidia-smi`).
- Use CPU version if GPU issues persist (`pip install tensorflow-cpu`).

---

### **7. Outputs**  

#### **1. Upload an image:**  
The user uploads an image of a potato leaf through the web interface.  

![alt text](<outputs/Screenshot 2025-02-12 155444.png>)

#### **2. Prediction Result:**  
After processing, the model provides the **Predicted Label** and **Confidence Score**.  

![alt text](<outputs/Screenshot 2025-02-12 155524.png>)

The output displays:  
- **Uploaded Image**  
- **Predicted Class (e.g., Healthy, Early Blight, Late Blight)**  
- **Confidence Score (%)**  

### License

This project is licensed under the MIT License. For more details, refer to the [LICENSE](LICENSE.txt) file.

