# Fine-tuning-GPT-3.5-for-real-time-customer-complaint-analysis

## Overview
This project fine-tunes the GPT-3.5 model to improve the efficiency and accuracy of extracting actionable insights from customer complaints. The goal was to automate complaint categorization, quantify dissatisfaction, and reduce manual intervention in customer support workflows.

---

## Research Questions
- How can a fine-tuned GPT-3.5 model improve the extraction of structured insights from unstructured customer complaints?
- Can a domain-specific fine-tuned model outperform general models (e.g., GPT-4)?
- How can automation reduce manual effort and enhance complaint resolution workflows?

---

## Dataset
- Source: csv file with historic customer complaints
- Structure: 
  - **Unstructured Text**: Customer complaints in free-text format.
  - **Structured Data**: Topics, problems, and dissatisfaction levels.
- Preprocessing: 
  - Converted complaints into a structured JSON format compatible with fine-tuning requirements.
  - Each entry included:
    - Role: `system`, `user`, and `assistant`.
    - Content: Context, input, and expected output.

---

## Exploratory Data Analysis (EDA)
- **Distribution Analysis**:
  - Identified common themes like "Internet issues," "Billing errors," and "TV signal problems."
- **Visualization**:
  - Used word clouds and frequency plots to analyze recurring complaints and dissatisfaction trends.
- Insights: Revealed significant patterns in complaint severity and frequently reported issues.

---

## Feature Engineering
- Created a **Customer Dissatisfaction Index** (scale: 0–100) to quantify the severity of complaints.
- Standardized unstructured text into structured formats for seamless model training.
- Enhanced embeddings using fine-tuned GPT-3.5 for improved domain-specific accuracy.

---

## Model Choice
- **Model**: Fine-tuned **GPT-3.5-turbo**.
- **Rationale**: Selected for its adaptability to domain-specific datasets and superior contextual handling.
- Compared Performance:
  - GPT-4: Provided generic responses but lacked dataset-specific nuance.
  - Fine-Tuned GPT-3.5: Tailored to extract actionable insights with higher accuracy.

---

## Validation Process
- **Metrics**:
  - **Accuracy**: Measured correct identification of topics, problems, and dissatisfaction levels.
  - **Consistency**: Validated edge cases to ensure responses aligned with the dataset's context.
- **Training Loss**:
  - Visualized the decrease in loss across steps, confirming model optimization.
  - Example: Loss reduced from 4.19 at step 1 to 0.067 at step 67.
- **Real-World Testing**:
  - Tested the model with novel complaints to evaluate generalization capabilities.

---

## Deployment
- **Model Deployment**:
  - Fine-tuned model: `ft:gpt-3.5-turbo`.
  - Integrated into a production environment via **REST APIs**.
- **Functionality**:
  - Processes customer complaints in real-time.
  - Extracts key insights: `Topic`, `Problem`, and `Customer Dissatisfaction Index`.
- **Scalability**:
  - Designed to handle concurrent requests with minimal latency.
- **Example Outputs**:
  ```json
  Input: "TV channels keep disappearing from my subscription!"
  Output: {
    "Topic": "TV",
    "Problem": "Missing channels",
    "Customer_Dissatisfaction_Index": "High"
  }

  ## Model Output and Metrics

### Performance
- **Outperformed GPT-4** in domain-specific tasks, delivering more accurate and contextually relevant responses.
- Improved accuracy and reduced ambiguity in complaint categorization and prioritization.

### Examples
**Complaint**: "Line is down! It is really annoying!"  
- **Fine-Tuned GPT-3.5**:  
  ```json
  {
    "Topic": "Network",
    "Problem": "Line down",
    "Customer_Dissatisfaction_Index": 5
  }
- **GPT-4:**
  ```json
  {
  "Topic": "Service Interruption",
  "Problem": "Line is down",
  "Customer_Dissatisfaction_Index": "High"
  }

## Feature Importance
- **Customer Dissatisfaction Index**: Played a critical role in prioritizing complaints based on severity, ensuring urgent issues were addressed promptly.  
- **Contextual Embeddings**: Enhanced response specificity and accuracy for nuanced complaints, improving overall model performance.

---

## Documentation

### Reproducibility
- Provided **clear and detailed steps** for data preprocessing, model fine-tuning, and deployment workflows.  
- Visualized **training loss trends** to ensure transparency and interpretability of the model optimization process.

### Comparison
- Highlighted significant **performance improvements** of the fine-tuned model over GPT-4 in handling dataset-specific edge cases and contextual challenges.

### Codebase
- Included **modular functions** for efficient data processing, fine-tuning, and real-time API integration, making the solution scalable and adaptable.

---

## Key Outcomes
- **Automated complaint analysis and categorization**, significantly reducing manual intervention and support team workloads.  
- **Improved complaint resolution workflows**, delivering actionable insights aligned with customer expectations.  
- **Scalable and deployable model**, tailored for real-world scenarios and capable of handling concurrent requests efficiently.

---

