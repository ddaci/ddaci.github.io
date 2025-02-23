---
date: 2024-04-10T11:00:59-04:00
description: "REST API aplication on Google Cloud Platform"
featured_image: "/images/coverrestapi.jpg"
tags: ["Google Cloud Platform"]
title: "REST API aplication on Google Cloud Platform"
---

# 📚 REST API for Book Data with Flask and Google Cloud

## 📝 1. Project Description  
The REST API application is built using **Python** and **Flask**, designed to retrieve book data from an **SQLite3** database.  
👉 [GitHub Repository](https://github.com/cpatrickalves/simple-flask-api)

A **REST API** exposes the functionalities of an application or database through a set of **endpoints (URLs)**. These endpoints allow clients (such as web or mobile apps) to perform **CRUD operations** (Create, Read, Update, Delete) via **HTTP requests**.  
The main REST principles rely on HTTP methods:
- **GET** – Retrieve data  
- **POST** – Create new data  
- **PUT/PATCH** – Update existing data  
- **DELETE** – Remove data  

This project demonstrates how to implement and deploy the REST API on **Google Cloud Platform (GCP)**.

---

## 📊 2. Data Model Description  
The database **`books.db`** contains information about books.  
Data is stored and managed using **SQLite**, a lightweight, serverless, file-based **relational database management system** (RDBMS).

---

## 🛠️ 3. Data Storage Solutions and Rationale  
For data storage, we chose **Google Cloud Storage (GCS)** and **BigQuery** for the following reasons:

### 🌤️ **Google Cloud Storage (GCS)**  
- Used to store the **`books.csv`** file generated from the initial SQLite database.  
- Provides **scalability**, **durability**, and **high availability**.  
- Ensures data is **secure**, **easily accessible**, and **cost-efficient**.  

### 🚀 **BigQuery**  
- Chosen for **loading the `books.csv` file** and querying the data.  
- Handles **large structured datasets** efficiently.  
- Supports **fast querying**, enabling quick insights from the datasets.  

Both **GCS** and **BigQuery** integrate seamlessly into the **Google Cloud Platform (GCP)** ecosystem, simplifying development while ensuring scalability and high performance.

---

## ⚙️ 4. Data Model Implementation  
The implementation involves the following GCP services: **App Engine**, **BigQuery**, and **Google Cloud Storage**.

### 🔄 **Workflow Overview:**
1. **User Request:** The user sends an **HTTP request** to the Flask application.  
2. **API Processing:** The **`app.py`** file processes the request and, if necessary, performs **queries in BigQuery**.  
3. **Dependencies:** The **`requirements.txt`** file ensures that all necessary libraries are installed for request processing.  
4. **Configuration:** The **`app.yaml`** file defines how the application is deployed and managed on **App Engine**, including how requests are routed.

---

## 📈 5. System Architecture Diagram  
The following diagram illustrates how users interact with the Flask application and how its components communicate:
![alt text](/images/image4.png "Overview")
**Figure 1:** User interaction flow with the Flask REST API and Google Cloud services.  

---

## 🌟 **Conclusion**  
This project demonstrates how to build a scalable, cloud-based **REST API** using **Flask**, **Google Cloud Storage**, and **BigQuery**.  
It ensures **efficient data storage**, **fast querying**, and **secure access** while leveraging **GCP's powerful ecosystem**.




![alt text](/images/image13.png "Overview")

These URLs are accessed by clients such as web, mobile apps, or other web services to perform CRUD operations (Create, Read, Update, Delete) or other actions using HTTP requests. The principles of REST and the use of HTTP methods (GET for reading, POST for creating, PUT/PATCH for updating, and DELETE for deleting) allow resources to be manipulated in a standardized and intuitive way.
Description of the Data Model Used
Our database “books.db” contains information about books. Data are stored and managed using SQLite - a serverless, file-based relational database management system.
Choosing Data Storage Solutions, Justifying the Decision
Since we are working with a relational database, with structured data, where each item ("book" in this case) has the same set of attributes with specific values, a good choice would be to use a combination of Google Cloud Storage and BigQuery.
Implementation of the Used Data Model
We will use App Engine, BigQuery, and Google Cloud Storage:
● The user sends an HTTP request to the Flask application.
● app.py receives the request and, if necessary, performs queries to BigQuery.
● app.py uses requirements.txt to ensure that all necessary libraries are available for processing the request.
● app.yaml plays a role in configuring how the application is deployed and managed on App Engine, influencing how requests are handled.


Fig: 1. The diagram illustrates the interaction of users with the Flask application and how its components interact with each other.
We activate App Engine Admin API, BigQuery API, and add roles to the App Engine service account: BigQuery Admin, BigQuery Data Viewer, BigQuery Job User.
We fork the project https://github.com/cpatrickalves/simple-flask-api on GitHub
In Cloud Shell, we clone the GitHub branch (where we make changes) and deploy.
![alt text](/images/image9.png "Overview")
App.yaml
![alt text](/images/image8.png "Overview")
Requirements.txt
![alt text](/images/image3.png "Overview")
Google Cloud Storage
We upload books.db to Google Cloud Storage - we create a bucket that contains the database in CSV format.
![alt text](/images/image6.png "Overview")
We allow public access to the bucket and create a publicly accessible URL for the database.
![alt text](/images/image7.png "Overview")
Big Query
We have created a dataset via Big Query. Then we created a table within the dataset and uploaded the data file (books.csv) from the storage bucket to the new table created.
![alt text](/images/image1.png "Overview")
We make the dataset public:
![alt text](/images/image5.png "Overview")
Testing a data retrieval operation from the chosen storage solution using a programming language.
This is what the data we work with looks like.
![alt text](/images/image12.png "Overview")
Code in app.py
![alt text](/images/image14.png "Overview")
Home route: https://proiectcc-419616.ew.r.appspot.com/
![alt text](/images/image11.png "Overview")
Route that shows all books: https://proiectcc-419616.ew.r.appspot.com/api/v2/resources/bigquery-data**
![alt text](/images/image10.png "Overview")
