# AI-Powered Fraud Detection System

This Java-based desktop application detects potentially fraudulent financial transactions using machine learning. It provides separate dashboards for *Admin* and *User* roles, built with JavaFX. The system uses a pre-trained ML model (e.g. a random forest) to score incoming transactions for fraud probability.

## Features

- *Admin Dashboard:* 
  - Configure detection settings (e.g. probability threshold).
  - View reports and graphs of detected fraud cases.
  - Retrain or update the detection algorithm as needed.
- *User Dashboard:* 
  - Monitor individual transaction history.
  - Receive real-time alerts on transactions flagged as suspicious.

The system uses ML algorithms (e.g. decision trees, neural nets) trained on historical data to identify anomalies:contentReference[oaicite:44]{index=44}:contentReference[oaicite:45]{index=45}. It employs Java libraries like Weka and JavaFX:contentReference[oaicite:46]{index=46}:contentReference[oaicite:47]{index=47}.

## Installation

1. *Prerequisites:* Java 11+ must be installed.  
2. *Clone the repository:*
3. *Dependencies:* Ensure the following libraries are on the classpath (using Maven or manual jars):  
- Weka (for ML algorithms):contentReference[oaicite:48]{index=48}  
- JavaFX (for GUI) – if using JDK 11+, include JavaFX modules.  
4. *Prepare the model:* Place a trained model file (e.g. randomForest.model) in src/main/resources/model/ or configure the path in FraudDetector.java.  

## Usage

- *Admin:* Run the application and open the Admin Dashboard window. Enter the desired fraud threshold and click *Update*. View live graphs of fraud statistics or manually retrain the model (button provided).  
- *User:* Enter a user ID to log into the User Dashboard. All recent transactions for that user will display, with "Suspicious" marked next to any transaction exceeding the fraud threshold.

The GUI uses JavaFX GridPane layouts for forms, as recommended in Oracle’s docs:contentReference[oaicite:49]{index=49}. The ML model is consulted for each transaction; if the model’s fraud score exceeds the threshold, the transaction is flagged. Alerts and reports are generated based on these detections.

## Code Structure

- src/main/java/: Contains Java source code:  
- Transaction.java – data class for transactions.  
- FraudDetector.java – ML model wrapper (loads and queries Weka model).  
- AdminDashboard.java, UserDashboard.java – JavaFX UIs for each role.  
- MainApp.java – application entry point.  
- src/main/resources/: Place for config files, the serialized ML model, and example datasets.  

## Implementation Notes

- The ML algorithms are implemented in Java. Libraries like Weka and DL4J are suitable choices:contentReference[oaicite:50]{index=50}:contentReference[oaicite:51]{index=51}. Weka includes many classifiers (J48, RandomForest, etc.) out of the box:contentReference[oaicite:52]{index=52}.  
- The UI is built with JavaFX. We use charts and tables to visualize alerts and transactions. The GridPane layout is used for input forms:contentReference[oaicite:53]{index=53}.  
- For demonstration, a simple threshold-based classifier is shown. In a production system, you would train the model on real transaction data and possibly integrate streaming (e.g. Kafka) for real-time ingestion:contentReference[oaicite:54]{index=54}.

## References

- Hemasree Koganti, AI Anomaly Detection in Real-Time Java Financial Systems:contentReference[oaicite:55]{index=55} – Discusses using ML (Isolation Forest, Kafka, etc.) for fraud detection.  
- Itransition, Machine learning for fraud detection: Overview:contentReference[oaicite:56]{index=56}:contentReference[oaicite:57]{index=57} – Explains ML approaches (supervised/unsupervised) in fraud systems.  
- StepMedia, Top Java ML Libraries:contentReference[oaicite:58]{index=58}:contentReference[oaicite:59]{index=59} – Describes Java libraries (DL4J, Weka, MOA) for ML in fraud use-cases.  
- Oracle JavaFX Docs, Creating a Form in JavaFX:contentReference[oaicite:60]{index=60} – Guidance on building GUI forms with GridPane.
