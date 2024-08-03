---
layout: ../../layouts/post.astro
title: "PreProd : AutoML made simple"
pubDate: 2023-12-23
description: "iOS app to track personal finances"
author: "Pranav"
excerpt: Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et
image:
  src:
  alt:
tags: ["iOS", "MVVM", "finance"]
---

### AutoML Hackathon
> Team PipeDreamers


> [!NOTE] Objective
- Receive file inputs from users.
- Perform data cleaning and preprocessing.
- Format data for various machine learning classification algorithms.
- Pass necessary parameters to train data
- Ensuring scalability, reliability, and efficiency in data handling.
### Project Plan

#### 1. Architecture
The system is designed using a micro-services architecture to ensure modularity, scalability, and ease of maintenance. The architecture is composed of the following components:


![[Screenshot 2024-08-02 at 9.37.19 AM.png]]
 
* ##### Frontend (Next.js)

- **Description**: The frontend is developed using Next.js, a React-based framework. It provides a user-friendly interface for users to upload files and view the processing status.
- **Features**:
    - File upload functionality
    - Status dashboard for tracking the data processing pipeline
    - User authentication and session management
    - Parameters to train model

##### Backend Services
##### File Upload and Management

- **Description**: This microservice handles the ingestion of files uploaded by users. It stores the files temporarily and initiates the data processing pipeline.
- **Technologies**: JavaScript
- **Responsibilities**:
    - Receive and validate file uploads
    - Store files in a temporary location on Google Cloud Storage
    - Adds files metadata in Mongo DB
    - Adds new event to RabbitMQ queue

##### Data Cleaning and Preprocessing (Python)

- **Description**: This service is responsible for cleaning and preprocessing the uploaded data.
- **Technologies**: Python, Pandas, NumPy, Scikit-Learn
- **Responsibilities**:
    - Detect and handle missing values
    - Normalise and standardise data
    - Convert categorical data into numerical formats (one-hot encoding, label encoding)
    - Handle data anomalies and inconsistencies


##### Machine Learning Preprocessing (Python)

- **Description**: This service formats the cleaned data into trainable formats for various machine learning algorithms.
- **Technologies**: Python, scikit-learn
- **Responsibilities**:
    - Split data into training and testing sets
    - Scale and transform data as required by specific algorithms
    - Train various ML models on the uploaded dataset
    - Save the trained models in pickled file formats


##### Data Storage (MongoDB, Google Cloud Storage)

- **Description**: MongoDB is used as the primary database for storing metadata about the files and their processing status.
- **Responsibilities**:
    - Store user information and authentication data
    - Track file upload and processing status
    - MongoDB stores files metadata. 
    - GCS stores uploaded datasets 

##### Message Queue (RabbitMQ)

- **Description**: RabbitMQ is utilised for asynchronous communication between microservices.
- **Responsibilities**:
    - Queue messages for file processing tasks
    - Ensure reliable delivery of tasks to the appropriate microservices
    - Enable scalability by distributing workloads among multiple instances of processing services

#### 2. Skill Matrix

| *skills*      | Manomay | Sudhith | Pranav | Jaiyank |
| ------------- | ------- | ------- | ------ | ------- |
| Front end     |         |         |    ✔️   |         |
| Backend       |    ✔️    |         |        |         |
| AI/ML         |         |    ✔️    |        |    ✔️    |
| Documentation |         |         |    ✔️   |         |

#### 3. Timeline 

To tackle the project efficiently, the team divided the work into two parallel streams: Web Development and Backend Development using Python.

**Day 1**

> **TL;DR** 
	The first day focused on groundwork for both the frontend and backend systems. The web development efforts concentrated on building a functional user interface, while backend work established essential data processing and machine learning capabilities.
##### Web Development: Day 1
**Tasks and Progress**:
1. **Authentication/Login Page**:
   - **Goal**: Implement a secure login system to manage user access.
   - **Implementation**: 
     - Built using Next.js and integrated with a user authentication service.
     - Implemented secure token-based authentication to ensure user data privacy.
     - Developed a responsive design to ensure usability across various devices.

2. **Dashboard for File Upload**:
   - **Goal**: Provide a user-friendly interface for uploading data files.
   - **Implementation**:
     - Designed and developed a dashboard interface with Next.js.
     - Added functionality to allow users to upload files easily.
     - Provided a section for users to view the status of their uploaded files and processing.

3. **Backend Connection**:
   - **Goal**: Connect the frontend to the backend services for data storage and processing.
   - **Implementation**:
     - Established an API to communicate between the frontend and the backend.
     - Implemented a system to store metadata (such as file names) in MongoDB.
     - Configured Google Cloud Storage to securely store the uploaded files.

##### Python Backend Development: Day 1
**Tasks and Progress**:
1. **Preprocessor Functionality**:
   - **Goal**: Develop a module for data cleaning and preparation.
   - **Implementation**:
     - Created a Python script using Pandas and NumPy to handle missing values, normalise data, and perform other preprocessing tasks.
     - Established a modular design to easily extend the preprocessing capabilities as needed.

2. **Machine Learning Algorithms**:
   - **Goal**: Implement initial models for training.
   - **Implementation**:
     - Developed functions for training Support Vector Machine (SVM) and Random Forest classifiers.
     - Utilised scikit-learn for model training and evaluation.
     - Ensured that the models could take the preprocessed data and output trained models ready for deployment.


**Day2**

> **TL;DR** 
	 On Day 2, our team made significant progress in various aspects of the project, focusing on UI development, frontend implementation, model training, data preprocessing, integrating a new machine learning model, and setting up communication between micro-services. Additionally, we containerised the application for improved deployment and scalability.

**1. UI Development**

- **Objective:** Enhance the user interface for better user experience and functionality.
- **Tasks Completed:**
    - Designed and implemented key UI components based on the project specifications.
    - Improved the responsiveness and aesthetics of the application, ensuring it works seamlessly across different devices and screen sizes.
    - Added interactive elements and navigation features to improve user interaction.

**2. Frontend Implementation**

- **Objective:** Develop and integrate the frontend elements with the backend services.
- **Tasks Completed:**
    - Implemented frontend logic and integrated it with the backend API.
    - Ensured data flows correctly between the frontend and backend, providing a smooth user experience.
    - Conducted testing to validate the functionality and performance of the frontend components.

**3. Model Training and Hyper-parameter Tuning**

- **Objective:** Train machine learning models and optimise their performance through hyper-parameter tuning.
- **Tasks Completed:**
    - Trained several machine learning models using the available dataset.
    - Conducted hyper-parameter tuning to enhance model accuracy and efficiency.
    - Recorded the best-performing models and their respective hyper-parameters for further evaluation.

**4. Data Preprocessing**

- **Objective:** Prepare the data for model training by cleaning and handling missing values.
- **Tasks Completed:**
    - **Check for Null Values:** Identified and addressed any missing data in the dataset.
    - **Data Cleaning:** Cleaned the dataset by removing irrelevant information, handling missing values, and normalising data where necessary.
    - **Feature Engineering:** Created new features and selected the most relevant ones to improve model performance.

**5. Addition of Gaussian Naive Bayes**

- **Objective:** Introduce Gaussian Naive Bayes as a classification model to the existing set of models.
- **Tasks Completed:**
    - Implemented the Gaussian Naive Bayes algorithm.
    - Trained the model on the preprocessed dataset.
    - Evaluated its performance against other models to determine its efficacy.

 **6. Setup RabbitMQ for Micro-services Communication**

- **Objective:** Establish a reliable communication channel between micro-services using RabbitMQ.
- **Tasks Completed:**
    - Installed and configured RabbitMQ as a message broker.
    - Implemented message queues for efficient communication between different micro-services.
    - Tested the message flow to ensure reliable and timely delivery of messages across services.

**7. Dockerisation of the Application**

- **Objective:** Containerise the application for consistent deployment and scalability.
- **Tasks Completed:**
    - Created Docker files for the different components of the application.
    - Built Docker images for each component and verified their functionality.
    - Deployed the Dockerized application, ensuring it runs smoothly in the containerised environment.

#### 4. UserManual

 ### **1. Introduction** 

- Welcome to the **Pickler** User Manual. This guide provides all the information you need to effectively use *Pickler*. Whether you're a beginner or an experienced user, this manual will help you navigate the software's features and functionalities and get the most of *Pickler*, we've got all the tips and tricks you need.

- **Pickler** is a solution to upload your dataset and get pickle file trained using your desired classification model.

**2. Getting Started**

**System Requirements** 
**Pickler** is modular, it is available across desktops, laptops and tablets.

**Account Setup** 

To start using **Pickler** you'll need to set up an account:
1. Open the application and click on "Sign Up."
2. Fill in your details and verify your email address.
3. Log in with your credentials.
![[Screenshot 2024-08-02 at 5.06.30 PM.png]]


**3. User Interface Overview**

**Main Dashboard** 
The main dashboard provides an overview of the key features and data while keeping the UI simple 

*Buttons*
- Top right corner 
	- Files - View uploaded files
	-  Models - View all supported Machine Learning classification models
	-  Upload file - upload desired files of formats (.csv, .xslx, JSON, .parquet)
- Top left corner
	- Account holder

*Dashboard*
- View all uploaded files - Name, status (cleaned/uncleaned), size, type, actions (clean/train/delete)

![[Screenshot 2024-08-02 at 5.06.34 PM.png]]
**Upload files**

![[Screenshot 2024-08-02 at 5.06.41 PM.png]]

**Clean uploaded files**
![[Screenshot 2024-08-02 at 5.06.50 PM.png]]
**Train dataset**
![[Screenshot 2024-08-02 at 5.07.03 PM.png]]
 
#### **5. Features and Functionalities**
##### **Feature 1: [Data Ingestion]** 
1. Upload file of any type 
##### **Feature 2: [Data Transformation]**
1. Clean data for nulls
2. Get resultant rows and columns to proceed with model training

##### **Feature 3: [AutoTrain]** 
1. Train models using the given dataset as per your choice
2. Get enhanced experience with hyper-parameters to tune your model

#### **6. Troubleshooting and FAQs** 

##### **1. What file types are supported for upload?**
**Answer:** Pickler supports a variety of common file types, including .csv, .xslx, .parquet and JSON files. Please ensure that your data is properly formatted according to the system's requirements for seamless processing.

##### **2. How do I handle missing data in my dataset?**
**Answer:** Pickler includes a data cleaning and preprocessing module that automatically detects and handles missing values. You can choose to remove rows with missing data, replace them with a default value, or use statistical methods such as mean or median imputation.

###### **3. What machine learning models can I train using Pickler?**
**Answer:** Pickler supports various classification algorithms, including Support Vector Machines (SVM), Random Forest, and Gaussian Naive Bayes. You can select the model that best suits your data and use hyper-parameter tuning to optimise its performance.

##### **4. Can I upload multiple files at once?**
**Answer:** Currently, Pickler allows the upload of one file at a time. If you have multiple datasets, you will need to upload them separately. The system stores each file's metadata for easy access and management.

##### **5. How do I monitor the status of my uploaded files and model training?**
**Answer:** The status dashboard in the Pickler application provides real-time updates on the progress of file uploads and model training. You can view the current state of your data processing and receive notifications when tasks are completed.

##### **6. What is the role of the temporary file storage in Google Cloud Storage?**
**Answer:** Google Cloud Storage temporarily stores the uploaded files during the data processing pipeline. This secure storage solution ensures that your data is safely retained while being processed and that it can be accessed by the necessary backend services.

##### **7. How do I access the trained machine learning models?**
**Answer:** Once the models are trained, they are saved in a pickled file format. You can download these models for further use, such as making predictions on new data or integrating them into your applications.

##### **8. Is it possible to customise the data preprocessing steps?**
**Answer:** Yes, Pickler offers options for customising data preprocessing steps. You can specify how to handle missing values, choose data normalisation methods, and select encoding techniques for categorical variables. This flexibility allows you to tailor the preprocessing to your specific dataset needs.

##### **9. How does RabbitMQ enhance the system's functionality?**
**Answer:** RabbitMQ facilitates asynchronous communication between micro-services in the Pickler architecture. It helps manage the task queue, ensuring that data processing tasks are efficiently distributed and handled by the appropriate services. This setup improves the scalability and reliability of the system.

##### **10. How can I ensure my data is secure while using Pickler?**
**Answer:** Pickler employs several security measures, including secure token-based authentication, encryption of data in transit and at rest, and secure storage in Google Cloud Storage and MongoDB. These measures protect your data from unauthorised access and ensure its confidentiality.

##### **11. What should I do if I encounter an error during file upload?**
**Answer:** If you encounter an error during file upload, check the file format and size to ensure they meet the system's requirements. If the problem persists, consult the troubleshooting section in the user manual or contact Pickler support at [PicklerSupport](mailto:manomay111@gmail.com) for assistance.

##### **12. Can I use Pickler on any device?**
**Answer:** Yes, Pickler is designed to be accessible on various devices, including desktops, laptops, and tablets. The responsive design ensures a consistent user experience across different screen sizes.

##### **13. How can I get help if I have questions not covered in the FAQ?**
**Answer:** For additional questions or support, you can contact the Pickler support team via email at [PicklerSupport](mailto:manomay111@gmail.com). Our team is available to assist with any issues or inquiries you may have.

#### **7. Contact Support** 

If you encounter any issues or have questions not covered in this manual, please contact us:
Write to us at [PicklerSupport](mailto:manomay111@gmail.com)











