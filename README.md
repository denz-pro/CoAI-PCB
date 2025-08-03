# **Co.AI - PCB Inspection**

## **Co.AI - Overview**
<p align="center">
  <img src="https://github.com/rishn/CoAI-PCB/blob/main/assets/Co.AI.png?raw=true" alt="Co.AI Products" />
</p>

Co.AI is an advanced AI-driven platform designed to streamline and optimize various industrial processes. It offers a suite of modules tailored to specific use cases, enabling businesses to leverage cutting-edge AI technologies for enhanced efficiency and accuracy. One of the key modules of Co.AI is **PCB Inspection**, which focuses on automating and improving the quality assurance process for printed circuit boards (PCBs).

This project was developed as part of an internship, focusing on leveraging AI to enhance the efficiency and accuracy of industrial workflows.

---

## **PCB Inspection Module**

The **PCB Inspection** module is a critical component of Co.AI, designed to address the challenges faced in the manufacturing and quality control of PCBs. This module leverages state-of-the-art AI algorithms to detect defects, anomalies, and inconsistencies in PCBs with high precision. By integrating this module into their workflow, manufacturers can significantly reduce manual inspection efforts, minimize errors, and ensure the production of high-quality PCBs.

### **Key Features of the PCB Inspection Module**
- **Automated Defect Detection**: Identifies common PCB defects such as soldering issues, misaligned components, and broken traces.
- **High Accuracy**: Utilizes advanced machine learning models to achieve superior accuracy in defect detection.
- **Real-Time Analysis**: Provides instant feedback during the inspection process, enabling quick corrective actions.
- **Customizable Parameters**: Allows users to configure inspection criteria based on specific requirements.
- **Seamless Integration**: Easily integrates with existing manufacturing systems and workflows.

---
## **Hardware Prototype**

<p align="center">
  <img src="https://github.com/rishn/CoAI-PCB/blob/main/assets/Prototype.jpg?raw=true" alt="Prototype" />
</p>

The PCB Inspection module was developed as a full hardware prototype to demonstrate its capabilities in real-world scenarios. The prototype integrates AI-powered software with custom-built hardware components to provide a complete solution for PCB inspection.

### **Key Components**
1. **Inspection Chamber**: 
   - A custom-built enclosure with a closed interior housing a high-resolution camera, lighting, speaker, and PC.
   - Designed to capture high-quality images of PCBs for analysis.
   - Equipped with appropriate lighting to ensure consistent image quality.

2. **Camera System**:
   - Integrated with the LIC interface using GMSL2 Protocol and V4L2 driver.
   - Tested with OpenCV Python for capturing and processing images.

3. **Processing Unit**:
   - An i5 computer running Linux Ubuntu 20.04 LTS.
   - Handles image processing, model execution, and result generation.

4. **Speaker**:
   - Integrated for audio output using Microsoft Azure Text-to-Speech (TTS) SDK.
   - Provides real-time feedback on inspection results.

5. **User Interface**:
   - Built using React TypeScript.
   - Allows users to capture images, run inspection algorithms, and view results.

6. **Models**:
   - Custom-trained classification, object detection, and polarity models.
   - Detects board orientation, missing components, and capacitor polarities.

---

### **Application In Use**
Below are screenshots of the prototype and its functionality:
- **Landing Page**:
  <p align="center">
      <img src="https://github.com/rishn/CoAI-PCB/blob/main/assets/LandingPage.png?raw=true" alt="Landing Page" />
  </p>

- **Image of PCB from Prototype Camera**:
  <p align="center">
      <img src="https://github.com/rishn/CoAI-PCB/blob/main/assets/UndistortedPrototypeImage.png?raw=true" alt="PCB Image" />
  </p>

- **Page Displaying Models Trained**:
  <p align="center">
      <img src="https://github.com/rishn/CoAI-PCB/blob/main/assets/ModelsPage.png?raw=true" alt="Models" />
  </p>

- **PCB Inspection Results**:
  <p align="center">
      <img src="https://github.com/rishn/CoAI-PCB/blob/main/assets/PredictionPage.png?raw=true" alt="Predictions" />
  </p>

  <p align="center">
      <img src="https://github.com/rishn/CoAI-PCB/blob/main/assets/PredictionResults.jpg?raw=true" alt="Predictions" />
  </p>

---

## **Features**
- **Automated Defect Detection**: Uses Azure's Custom Vision API to identify defects in PCBs.
- **Annotation Management**: Upload and manage annotations for training datasets.
- **Project Management**: Create, manage, and delete vision projects for PCB inspection.
- **Performance Monitoring**: Retrieve and analyze model performance metrics.
- **Endpoint Management**: Publish and unpublish prediction endpoints for real-time defect detection.
- **Speech Integration**: Supports Azure Speech Services for voice synthesis to provide audio feedback.

---

## **Technologies Used**
- **Backend**: Django (Python)
- **Frontend**: React (TypeScript)
- **Cloud Services**: Azure Custom Vision API, Azure Blob Storage, Azure Speech Services
- **Containerization**: Docker
- **CI/CD**: GitHub Actions

---

## **UI Module**

The **UI Module** of Co.AI is built using React and TypeScript, providing an intuitive and user-friendly interface for managing PCB inspection workflows. It includes features such as project creation, image annotation, and real-time inspection feedback.

### **Key Features of the UI Module**
- **Project Management**: Create, delete, and manage projects directly from the UI.
- **Image Annotation**: Annotate images for training datasets using a drag-and-drop interface.
- **Real-Time Inspection**: View inspection results and predictions in real-time.
- **Model Management**: Train, publish, and unpublish models with a few clicks.
- **Streamlined Navigation**: Breadcrumbs and a responsive layout for easy navigation.

---

## **Setup Instructions**
### **Prerequisites**
- Python 3.11+
- Node.js 16+
- Docker
- Azure account with access to Vision API and Blob Storage
- Azure Speech Services enabled

### **Steps**
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/CoAI.git
   cd CoAI
   ```

2. Set up the backend:
   ```bash
   cd Django-Middleware
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. Set up the frontend:
   ```bash
   cd ../Typescript-UI
   npm install
   ```

4. Set up the `.env` file:
   - Add the following secrets to a `.env` file in both the backend and frontend directories:
     ```plaintext
     SECRET_KEY=your_django_secret_key
     ENDPOINT=your_azure_cognitive_services_endpoint
     TRAINING_KEY=your_training_key
     PREDICTION_KEY=your_prediction_key
     PREDICTION_RESOURCE_ID=your_prediction_resource_id
     TRAINING_ENDPOINT=your_azure_cognitive_services_training_endpoint
     PUBLISH_ITERATION_NAME=iteration_published
     AZURE_STORAGE_ACCOUNT_NAME=your_storage_account_name
     AZURE_STORAGE_ACCOUNT_KEY=your_storage_account_key
     AZURE_STORAGE_CONNECTION_STRING=your_storage_connection_string
     PROJECT_ID=your_project_id
     PROJECTS_TABLE=object_containing_project_details
     POLARITY_CHECK_MODEL=polarity_check_model_id
     GAL_POLARITY_MODEL=gal_polarity_model_id
     FANT_POLARITY_MODEL=fant_polarity_model_id
     SFHR_POLARITY_MODEL=sfhr_polarity_model_id
     CLASSIFICATION_ID=your_classification_model_id
     SPEECH_SUBSCRIPTION=subscription_key_for_speech_services
     SPEECH_REGION=geo_region_for_tts
     SPEECH_VOICE=speech_voice
     ```

5. Run the development servers:
   - Backend:
     ```bash
     cd Django-Middleware
     python manage.py runserver
     ```
   - Frontend:
     ```bash
     cd ../Typescript-UI
     npm start
     ```

6. (Optional) Build and run the Docker container:
   ```bash
   docker build -t coai-middleware .
   docker run -p 8000:8000 coai-middleware
   ```

---

## **Usage**
- Access the UI at `http://localhost:3000/`.
- Use the UI to create projects, annotate images, and inspect PCBs.
- Access the API at `http://localhost:8000/api/vision/` for backend operations.

---

## **Acknowledgments**
This project was developed as part of an internship at RoshAI Kochi focused on leveraging AI for PCB inspection. Special thanks to the mentors and team members who provided guidance and support throughout the development process.<br/>
*Source files are not shared via the repository. However, additional files used along with the project directory structure are displayed.*

---