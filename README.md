# 💰 Fullstack Expense Tracker

A full-stack web application to track your daily expenses, built using **Java (Spring Boot)**, **React (Node.js)**, and **MySQL**.

---

## 🧰 Prerequisites

Make sure the following are installed on your system:

- ☕ Java **17**  
- 🟩 Node.js **v22.15.0**  
- 🐬 MySQL **8.0.33**  
- 📦 Apache Maven **3.9.9**  

---

## 🚀 Setup Instructions

### 🔁 Step 1: Clone the Repository

git clone https://github.com/DharshiBalasubramaniyam/Fullstack-Expense-Tracker.git
cd Fullstack-Expense-Tracker

🛠️ Step 2: Configure the Database
Update the application.properties file inside the backend/src/main/resources/ directory:

application.properties

spring.datasource.url=jdbc:mysql://localhost:3306/expense_tracker
spring.datasource.username=your_username
spring.datasource.password=your_password

spring.mail.username=your_email
spring.mail.password=your_email_password
spring.mail.properties.mail.smtp.starttls.required=true

✅ Make sure your MySQL server is running and a database named expense_tracker is created.

🖥️ Running the Application

create the database first and start the backend service.
Start the Backend it will generate the tables in database & import the Dumb.sql file.


▶️ Start the Backend

cd backend
mvn spring-boot:run

▶️ Start the Frontend

cd ../frontend
npm install
npm start

http://localhost:3000/user/statistics

![image](https://github.com/user-attachments/assets/39b84cfc-0075-41ec-b33a-f99c96e62951)
![image](https://github.com/user-attachments/assets/dd1e6b98-91d3-433d-a7bf-26bce029a662)
![image](https://github.com/user-attachments/assets/e1aa8a72-a8e0-4f47-bbea-d85b7cec3850)
![image](https://github.com/user-attachments/assets/f84b4917-386f-4de0-8124-5aa6509293e2)



