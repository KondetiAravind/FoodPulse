# ⚡ FoodPulse

## AI-Powered Restaurant Recommendation & Experimentation

FoodPulse is an AI-powered restaurant recommendation system designed to reduce decision fatigue and improve restaurant discovery through personalized, context-aware recommendations.

The system combines **collaborative filtering, content-based filtering, contextual personalization, hybrid ranking, cold-start handling, explainable recommendations, and product experimentation** into a unified recommendation experience.

> **Project Date:** June 2026  
> **Author:** Kondeti Aravind  
> **Institution:** Indian Institute of Technology Bhubaneswar

---

## 🚀 Project Overview

Choosing a restaurant on a food-delivery platform can involve a large number of options, making the decision process time-consuming.

FoodPulse addresses this problem by ranking restaurants according to:

- User ordering history
- Restaurant characteristics
- Cuisine preferences
- Price sensitivity
- Dietary preferences
- Ratings
- Delivery characteristics
- Location and distance
- Meal-time context
- Similar-user behavior

The system also provides explanations for recommendations instead of presenting users with an unexplained ranked list.

---

## 🎯 Product Objective

FoodPulse is designed around a product hypothesis:

> **Personalized restaurant recommendations can reduce the time users spend deciding what to order while improving restaurant discovery and conversion.**

### Primary Product Metric

**Time to Order**

The target is to reduce the user's decision time by approximately **40%**.

### Secondary Metrics

- Conversion rate
- Restaurant discovery frequency
- Recommendation engagement
- User satisfaction

### Guardrail Metrics

- Delivery experience
- Cancellation rate
- Negative user feedback

---

# 🧠 Recommendation Architecture

FoodPulse uses a hybrid recommendation architecture combining three signals:

```text
                    User
                     │
        ┌────────────┼────────────┐
        │            │            │
        ▼            ▼            ▼
   Order History  Preferences   Context
        │            │            │
        ▼            ▼            ▼
 Collaborative   Content-Based  Contextual
  Filtering       Filtering     Scoring
        │            │            │
        └────────────┼────────────┘
                     ▼
               Hybrid Ranker
                     │
                     ▼
          Filtering & Diversification
                     │
                     ▼
              Explainability
                     │
                     ▼
              FoodPulse UI
````

### Recommendation Components

| Component               | Purpose                                                 |
| ----------------------- | ------------------------------------------------------- |
| Collaborative Filtering | Learns preferences from similar users                   |
| Content-Based Filtering | Matches restaurants to user and restaurant attributes   |
| Contextual Scoring      | Incorporates meal time, location and contextual signals |
| Hybrid Ranking          | Combines recommendation signals                         |
| Cold-Start Handler      | Handles users without sufficient history                |
| Explainability          | Generates human-readable recommendation reasons         |

---

# 🔀 Hybrid Recommendation

FoodPulse combines recommendation signals using a weighted hybrid ranking approach.

### Standard User Flow

```text
Collaborative Filtering     40%
Content-Based Filtering     35%
Contextual Signals           25%
────────────────────────────────
Hybrid Recommendation       100%
```

Collaborative filtering contributes behavioral similarity, while content-based and contextual signals help personalize recommendations when behavioral information is limited.

For users without sufficient interaction history, the system relies more heavily on content and contextual information.

---

# 🧊 Cold-Start Recommendation

A recommendation system needs to handle users who have little or no historical interaction data.

FoodPulse provides a dedicated cold-start flow using:

* Dietary preference
* Budget
* Cuisine preference
* Restaurant popularity
* Restaurant rating
* User preference similarity

This allows new users to receive recommendations without requiring an existing order history.

---

# 💡 Explainable Recommendations

FoodPulse does not only return restaurant rankings.

The system also generates recommendation explanations based on signals such as:

* Previous ordering behavior
* Similar users
* Cuisine preference
* Restaurant rating
* Contextual compatibility
* Distance
* Value
* Trending/popularity signals

Example:

> ⭐ Highly rated restaurant matching your preferred cuisine and budget.

This helps make recommendations more understandable to users.

---

# 📊 Product Experimentation

FoodPulse includes an A/B experimentation framework for evaluating the impact of personalized recommendations.

### Experiment Design

```text
                 Eligible Users
                      │
             ┌────────┴────────┐
             ▼                 ▼
          Control           Treatment
            50%                50%
             │                 │
             ▼                 ▼
       Existing Flow     FoodPulse Recommendations
             │                 │
             └────────┬────────┘
                      ▼
                 Measure KPIs
```

### Primary Metric

**Time to Order**

### Secondary Metrics

* Conversion
* Discovery
* User satisfaction
* Recommendation engagement

### Guardrails

* Delivery experience
* Cancellation
* Negative feedback

The experimentation framework is designed to evaluate whether personalized recommendations improve user decision-making without negatively affecting the overall customer experience.

---

# 📈 ML Evaluation

The recommendation pipeline includes standard recommendation-system evaluation metrics.

### Ranking Metrics

* Precision@K
* Recall@K
* Hit Rate@K
* NDCG@K

### Recommendation Quality

* Diversity
* Novelty
* Coverage

These metrics provide multiple perspectives on recommendation quality rather than relying on a single metric.

---

# 🏗️ Project Structure

```text
FoodPulse/
│
├── app/
│   └── streamlit_app.py
│
├── data/
│   ├── raw/
│   ├── synthetic/
│   └── processed/
│
├── docs/
│   ├── architecture.md
│   ├── lab_logbook.md
│   └── methodology.md
│
├── models/
│   ├── collaborative_model.pkl
│   ├── content_based_model.pkl
│   └── hybrid_model.pkl
│
├── outputs/
│   ├── dashboards/
│   ├── figures/
│   └── reports/
│
├── prd/
│   ├── ab_test_plan.md
│   ├── edge_cases.md
│   └── restaurant_recommendations_prd.md
│
├── scripts/
│   └── train_models.py
│
├── sql/
│   ├── recommendations_tracking.sql
│   ├── restaurant_features.sql
│   └── user_features.sql
│
├── src/
│   ├── collaborative_filtering.py
│   ├── config.py
│   ├── content_based_filtering.py
│   ├── cold_start_handler.py
│   ├── data_generator.py
│   ├── evaluation.py
│   ├── explainability.py
│   ├── feature_engineering.py
│   └── hybrid_recommender.py
│
├── tests/
│   ├── test_cold_start.py
│   ├── test_explainability.py
│   └── test_recommender.py
│
├── requirements.txt
├── LICENSE
└── README.md
```

---

# 🛠️ Technology Stack

### Programming

* Python 3.10+

### Machine Learning

* NumPy
* Pandas
* Scikit-learn
* SciPy

### Recommendation Systems

* Collaborative Filtering
* Content-Based Filtering
* Hybrid Recommendation
* Cosine Similarity
* Contextual Ranking

### Application

* Streamlit

### Visualization

* Matplotlib
* Seaborn
* Plotly

### Testing

* Pytest

### Data / Query Layer

* CSV
* SQL

### Model Storage

* Pickle
* Git LFS

---

# ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/KondetiAravind/FoodPulse.git
cd FoodPulse
```

Create a virtual environment:

### Windows

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

---

# ▶️ Running FoodPulse

Launch the Streamlit application:

```powershell
streamlit run app\streamlit_app.py
```

The application will be available locally at:

```text
http://localhost:8501
```

---

# 🧪 Running Tests

Run the automated test suite:

```powershell
pytest -q
```

---

# 👤 User Flows

FoodPulse supports two primary recommendation scenarios.

## Existing User

Users with historical interactions receive personalized recommendations based on:

* Historical orders
* Similar users
* Restaurant attributes
* Context
* Previous interactions

## New User

Users without sufficient historical interactions can provide:

* Dietary preference
* Cuisine preference
* Budget

FoodPulse then generates recommendations using the cold-start strategy.

---

# 🔍 Recommendation Pipeline

```text
Data Generation
      │
      ▼
Feature Engineering
      │
      ├───────────────┐
      ▼               ▼
User Features    Restaurant Features
      │               │
      └───────┬───────┘
              ▼
       Model Training
              │
       ┌──────┼──────┐
       ▼      ▼      ▼
      CF   Content  Context
       │      │      │
       └──────┼──────┘
              ▼
       Hybrid Ranking
              │
              ▼
      Recommendation Filters
              │
              ▼
        Explanations
              │
              ▼
        Streamlit UI
```

---

# 📦 Dataset

FoodPulse uses a synthetic food-delivery dataset for experimentation and demonstration.

The project models:

* Users
* Restaurants
* Historical orders
* User preferences
* Restaurant attributes
* Interaction data

The synthetic dataset enables experimentation without exposing real customer or transaction information.

---

# 🧪 Experimentation Philosophy

FoodPulse treats recommendation quality as a **product problem**, not only an ML problem.

A model can achieve strong offline ranking metrics while failing to improve the actual user experience.

Therefore, FoodPulse combines:

```text
Offline ML Evaluation
        +
Product Metrics
        +
A/B Experimentation
        +
Guardrail Monitoring
```

This provides a framework for evaluating whether recommendation improvements translate into meaningful product outcomes.

---

# 📚 Documentation

Detailed project documentation is available in:

* [`docs/architecture.md`](docs/architecture.md)
* [`docs/methodology.md`](docs/methodology.md)
* [`docs/lab_logbook.md`](docs/lab_logbook.md)
* [`prd/restaurant_recommendations_prd.md`](prd/restaurant_recommendations_prd.md)
* [`prd/ab_test_plan.md`](prd/ab_test_plan.md)
* [`prd/edge_cases.md`](prd/edge_cases.md)

---

# 🚧 Future Improvements

Potential extensions include:

* Real-time recommendation serving
* Online feature stores
* Session-based recommendations
* Deep learning recommendation models
* Restaurant availability integration
* Real-time experimentation dashboards
* Recommendation feedback loops
* Automated experiment monitoring
* Personalized notification strategies
* Production-scale API deployment

---

# 👤 Author

## Kondeti Aravind

Dual Degree — Computer Science & Engineering
Indian Institute of Technology Bhubaneswar

**Project:** FoodPulse
**Project Date:** June 2026

* 🔗 LinkedIn: [https://www.linkedin.com/in/aravind-kondeti/](https://www.linkedin.com/in/aravind-kondeti/)
* 🐙 GitHub: [https://github.com/KondetiAravind](https://github.com/KondetiAravind)

---

# 📄 License & Attribution

FoodPulse is distributed under the MIT License.

This repository is a derivative work based on an MIT-licensed restaurant recommendation project. The original copyright and license notice are preserved in the repository's `LICENSE` file.

FoodPulse includes project-specific branding, documentation, experimentation framing, deployment configuration, and portfolio presentation.

See [`LICENSE`](LICENSE) for the complete license and attribution information.

---

## ⭐ FoodPulse

**AI-Powered Restaurant Recommendation & Experimentation**

Built to explore the intersection of:

**Machine Learning × Product Analytics × Recommendation Systems × A/B Testing**

````
