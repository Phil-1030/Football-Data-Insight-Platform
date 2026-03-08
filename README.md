
```markdown
# Football Data Insight Platform 

A personalized football information portal developed using the **Django** framework. [cite_start]This platform provides enthusiasts and professional managers with tailored content, data visualization, and an interactive environment to track teams, players, and match statistics[cite: 1063, 1064].

---

##  Key Features

* **Dual-Role Ecosystem**: Separate interfaces and functions for **Regular Users** (subscription-focused) and **Team Managers** (recruitment-focused).
* **Smart Recommendation System**: A content-based filtering engine that suggests new teams based on tactical similarity to your followed clubs.
* **Interactive Player Guessing Game**: A high-performance mini-game optimized via database query reduction (SQL `values()`, `distinct()`, and `order_by('?')`) to ensure smooth real-time interaction[cite: 1086, 1091].
* **Asynchronous Interactions**: Utilizes **Ajax** for follow/unfollow actions, ensuring a seamless user experience without page reloads.
* **Comprehensive Data Pipeline**: Processes 10 years of European top-tier league data using **PySpark** for rigorous cleaning and validation.

---


```

---

##  Dataset & Data Source

The platform is powered by the **European Soccer Database** sourced from **Kaggle**.

* 
**Scale**: Contains ~10 years of data from top European leagues.


* 
**Scope**: Covers 7 sub-datasets: Countries, Leagues, Teams, Team Attributes, Players, Player Attributes, and Matches.


* 
**Integrity**: Data is validated to ensure every league has $\ge 15$ teams and every team has $\ge 11$ players.



---

##  Mathematical Foundation

### 1. User Preference Modeling

Each team is represented as a **7-dimensional tactical attribute vector**. The system computes a **User Preference Vector** ($\vec{v}$) by averaging the vectors of all teams currently followed by the user:

$$ \vec{v} = \frac{1}{n} \sum_{i=1}^{n} \vec{u}^{(i)} $$

### 2. Euclidean Similarity Metric

To recommend new teams, the system calculates the **Euclidean Distance** between the User Preference Vector ($\vec{v}$) and every candidate team vector ($\vec{u}$):

$$ distance(\vec{v}, \vec{u}) = \sqrt{\sum_{j=1}^{7} (v_j - u_j)^2} $$

Smaller distances indicate higher tactical similarity, and the top 10 closest matches are returned as recommendations.

---

##  Quick Start

### 1. Prerequisites

```bash
pip install django pyspark pandas sqlite3

```

### 2. Database Setup

```bash
python manage.py makemigrations
python manage.py migrate

```

### 3. Launch Platform

```bash
python manage.py runserver

```

Visit `http://127.0.0.1:8000/` to explore the dashboard.

---

##  License

Distributed under the **MIT License**.

---

Developed by **Group 18**: Zhang Junwei, Cao Yunhe, & Yang Xi (Phil-1030) 

```

---


```
