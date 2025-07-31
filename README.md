# 🌟 Aspect-Based Sentiment Analysis for Product Reviews 📱

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![SpaCy](https://img.shields.io/badge/SpaCy-v3+-green?style=for-the-badge&logo=spacy)
![Pandas](https://img.shields.io/badge/Pandas-lightgrey?style=for-the-badge&logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-orange?style=for-the-badge&logo=matplotlib)
![Seaborn](https://img.shields.io/badge/Seaborn-purple?style=for-the-badge&logo=seaborn)

---

## 👋 Welcome! What's This Project About?

Ever tried to understand customer feedback beyond just a "good" or "bad" review? This project tackles that challenge head-on! It's an **Aspect-Based Sentiment Analysis system** designed to dig into product reviews and tell you not just *if* someone liked a phone, but **what specific features** (like the camera 📸, battery 🔋, or performance 🚀) they felt positive or negative about.

### What Makes It Special? ✨

Unlike many heavy-duty ML projects that demand huge, pre-labeled datasets and complex model training, this system takes a refreshingly **agile, lexicon-driven approach**. This means:

* **No Training Data Needed!** Seriously. We don't need gigabytes of labeled data to get started. Just well-defined keywords!
* **Infinitely Customizable:** Want to analyze reviews for headphones? Laptops? Or even coffee makers? Simply update a few keyword lists, and you're good to go – no retraining models from scratch! 🛠️
* **Transparent & Interpretive:** Because it's rule-based, you always know *why* a certain sentiment was assigned to a specific feature.

It's a powerful, lightweight, and incredibly flexible way to extract deep, actionable insights from raw text data.

---

## 💡 How It Works (The Magic Behind the Scenes)

The process is intuitive and effective:

1.  **Crafting the Lexicons:** I hand-curate a dictionary of relevant product **features** (e.g., "screen," "speaker," "price") and extensive sets of **positive** and **negative** sentiment words. This is our system's "brain." 🧠
2.  **Smart Feature Detection:** Using `SpaCy`'s powerful `PhraseMatcher`, the system intelligently scans each sentence in a review. If it spots a word related to one of our predefined features, it flags it.
3.  **Sentiment Linkage:** Once a feature is identified, the system analyzes the surrounding sentence. It checks for positive or negative sentiment words from our curated lists to assign a specific polarity (Positive, Negative, or Neutral) to that particular feature.
4.  **Visualize the Insights:** All extracted aspect-sentiments are then aggregated, and I use `Matplotlib` and `Seaborn` to generate clear, insightful charts. These visuals quickly highlight overall sentiment and, more importantly, break down opinions feature-by-feature! 📊

---

## 🚀 Get Started (Installation & Usage)

Want to run this yourself or adapt it for your next project? Here's how:

### Prerequisites

* Python 3.x

### Installation

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git) # 👈 **IMPORTANT:** Replace with your actual GitHub repo URL!
    cd your-repo-name
    ```
2.  **Set up a Virtual Environment (Recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: `.\venv\Scripts\activate`
    ```
3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(If you don't have a `requirements.txt` yet, create one with `pandas`, `spacy`, `matplotlib`, `seaborn`, `tqdm`)*
4.  **Download SpaCy's English Model:**
    ```bash
    python -m spacy download en_core_web_sm
    ```

### Usage

1.  **Prepare Your Data:** Ensure your review data is in a CSV file (e.g., `Prediction.csv`) and contains a column named `"Cleaned Review"`. Place this CSV in the project directory.
2.  **Run the Notebook:**
    ```bash
    jupyter notebook 2_phone_reviews.ipynb
    ```
    Simply step through the cells in the notebook to perform the analysis, view the sentiment counts, and generate the insightful plots.

---

## 📊 Results & What You'll See

Upon running the notebook, you'll get:

* **Overall Sentiment Breakdown:** A chart showing the general positive/negative split across all reviews.
* **Feature-Specific Insights:** This is where it gets exciting! Bar charts will illustrate the sentiment distribution for each identified feature (e.g., how many people praised the 'camera' versus how many criticized the 'battery'). This instantly reveals product strengths and areas needing attention.

*(Consider adding a placeholder image here if you plan to upload screenshots of your plots: `![Example Feature-wise Sentiment Plot](images/feature_sentiment_plot.png)`)*

---

## 🔄 Customize It! (Make it Yours)

The beauty of this project is its flexibility. You can easily adapt it for *any* domain by modifying the Python code directly in `2_phone_reviews.ipynb`:

* **`FEATURES` Dictionary:** Change the keys and lists of terms to match the aspects of your new product or service.
    ```python
    FEATURES = {
        "screen_quality": ["screen", "display", "resolution", "panel"],
        "sound_output": ["sound", "speaker", "audio", "bass"],
        "customer_service": ["support", "service", "help", "staff"] # Example for a service review
    }
    ```
* **`positive_words` & `negative_words` Sets:** Expand these sets with more nuanced vocabulary relevant to your specific domain to improve sentiment detection.
* **Input Data:** Update the `csv_path` variable to point to your new review dataset.

---

## 🔭 Future Enhancements

* **Advanced Negation Handling:** Implement more sophisticated rules for phrases like "not good" or "didn't like".
* **Automated Aspect Discovery:** Explore techniques to automatically identify emerging aspect terms from large review datasets.
* **Interactive Dashboard:** Integrate with a framework like Streamlit or Dash to create a user-friendly web interface for real-time analysis.
* **Comparative Analysis:** Extend to compare sentiment across different products or models within the same category.

---


