# Final Report: AI-Powered Chatbot for Local Businesses

## Introduction
Small businesses in Africa often face challenges in providing quick and consistent answers to customer questions. Many lack dedicated customer service teams, which can lead to delays and missed opportunities. Our project aims to solve this by building a simple AI-powered chatbot that can answer frequently asked questions using a small, well-structured dataset.

## Project Objective
The main goal is to create a chatbot that helps local businesses respond to customer inquiries efficiently. We use a rule-based approach with basic Natural Language Processing (NLP) techniques to match customer questions to the right answers.

## Dataset Overview
Our dataset contains four key columns:
- **Main Question:** The typical way a customer might ask something.
- **Alternative Ways to Ask:** Other ways the same question might be phrased.
- **Simplified Phrasings:** Even simpler or more direct versions of the question.
- **Simplified Response:** The answer the chatbot should give.

This structure ensures the chatbot can recognize and respond to different ways customers might ask the same thing.

## Data Pipeline
1. **Load and Inspect Data:** We read the CSV file and preview the first few rows to check for missing values and data types.
2. **Build Dictionary:** We create a dictionary mapping all possible question phrasings to their answers.
3. **Text Cleaning:** All text is converted to lowercase and punctuation is removed to improve matching.
4. **Fuzzy Matching:** If a customer’s question isn’t an exact match, we use SequenceMatcher to find the closest known question.
5. **Evaluation:** We split the data into training and test sets (80/20) and measure how accurately the chatbot answers questions it hasn’t seen before.

## Exploratory Data Analysis (EDA) and Visualizations

### 1. Distribution of Main Question Lengths
**Visualization:** Histogram of the number of words in each main question.

**Explanation:**
This chart shows how long customer questions typically are. Most questions are short and direct, usually between 6 and 9 words, with a peak at 7 words. This suggests users prefer clear, concise questions, which is ideal for a rule-based chatbot.

---

### 2. Top 10 Most Frequent Responses
**Visualization:** Bar chart of the most common answers.

**Explanation:**
A few responses cover the majority of customer questions. For example, answers about return policies and delivery times appear most frequently. This means the chatbot can handle many queries with a small set of well-crafted replies, making it efficient and easy to maintain.

---

### 3. Alternative & Simplified Phrasing Coverage
**Visualization:** Overlapping histograms showing the number of alternative and simplified phrasings per question.

**Explanation:**
Most questions have 2 or 3 alternative ways to ask and simplified versions. This coverage ensures the chatbot can recognize and respond to different phrasings, improving its ability to help users who ask questions in various ways.

---

### 4. Similarity Between Main Questions and Alternatives
**Visualization:** Histogram of average similarity scores between main questions and their alternatives.

**Explanation:**
We use a similarity score to measure how closely related alternative phrasings are to the main question. Most scores fall between 0.4 and 0.6, meaning alternatives are meaningfully reworded rather than being near-duplicates. This helps the chatbot understand paraphrased questions and improves its robustness.

---

### 5. Summary Table
**Visualization:** Table showing key dataset statistics.

**Explanation:**
- **Total Questions:** Number of questions in the dataset.
- **Unique Responses:** Number of unique answers.
- **Avg Alternatives per Question:** Average number of alternative phrasings.
- **Avg Simplified Phrasings per Question:** Average number of simplified versions.
- **Avg Similarity Score:** Average similarity between main questions and alternatives.

This summary confirms the dataset is well-structured and suitable for building a chatbot.

---

## Chatbot Implementation
- We use a rule-based system with a dictionary of question-answer pairs.
- Text cleaning and fuzzy matching help the chatbot handle different phrasings.
- The chatbot is tested using a train-test split to simulate real-world performance.
- Example interactions show the chatbot answering various customer questions.

## Evaluation
- **Accuracy Calculation:** The chatbot’s accuracy is the percentage of test questions answered correctly. For example, 75% accuracy means it got 3 out of 4 questions right.
- The chatbot performs well, especially for common questions and well-covered phrasings.

## Challenges & Limitations
- **Limited Data:** The chatbot can only answer questions it has seen before or close matches.
- **Local Language Support:** The dataset is mostly in English; local languages and slang are harder to cover.
- **Rule-Based Simplicity:** The chatbot doesn’t “understand” questions, it just matches patterns.
- **No Context Awareness:** It can’t handle follow-up questions or remember previous conversations.

## Possible Improvements
- Collect more data, especially in local languages.
- Use more advanced NLP models for better generalization.
- Add context handling and user feedback to improve responses.

## Conclusion
This project demonstrates how a simple AI chatbot can help local businesses answer customer questions quickly and consistently. The dataset is well-structured, and the chatbot achieves good accuracy using rule-based and basic NLP techniques. The visualizations provide insights into the strengths of the dataset and guide future improvements. With more data and smarter techniques, the chatbot can become even more helpful for local retail businesses.

---

