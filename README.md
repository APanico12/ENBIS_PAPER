# ⚡ Extreme Tail Risk in European Electricity Markets

## ❗ Why It Matters

In a context of growing **instability in European energy markets**, understanding how **extreme shocks** affect the **joint behavior of electricity prices** is critical.

Traditional correlation measures (like **Pearson** or **Spearman**) fail to capture what really matters during a crisis: the **co-movement of extreme negative returns**. These are the moments when **systemic risk** emerges, threatening the stability of the entire energy system.

Electricity markets are especially sensitive due to:

- **Nonlinear and volatile price dynamics**
- Exposure to **exogenous shocks** (e.g., geopolitical tensions, weather anomalies, fuel shortages)
- Strong interconnections across countries

Monitoring these tail co-dependencies is crucial for:

- Identifying vulnerabilities in the energy system  
- Supporting **risk allocation and management**
- Designing **resilient, evidence-based energy policies**

---

## 🧠 Methodology

This study applies a **nonparametric network-based approach** to measure **tail dependence** between country-level electricity prices, focusing on the **lower tail** (i.e., extreme negative returns) using the **Extreme Downside Correlation (EDC)**.

### 🔢 Step 1: Daily Log Returns

For each country $i$, we define the **daily log return** as:

$$
R_{i,t} = 100 \times (\log P_{i,t} - \log P_{i,t-1})
$$

Where:
- $P_{i,t}$ is the day-ahead electricity price
- Returns are expressed in percentage terms

---

### ⚠️ Step 2: Tail Risk with Value-at-Risk (VaR)

To isolate extreme events, we compute the **Value-at-Risk (VaR)** at a given confidence level $\tau \in (0, 1)$:

$$
VaR_{i,\tau} = F^{-1}_{R_i}(\tau)
$$

Where:
- $F_{R_i}$ is the cumulative distribution function (CDF) of returns
- $\tau$ controls the severity (e.g., $\tau = 0.01$ captures the worst 1%)

---

### 🌐 Step 3: Extreme Downside Correlation (EDC)

The **EDC** between two countries $i$ and $j$ is defined as:

$$
EDC_{\tau,ij} = \frac{\sum_t (R_{i,t} - \mu_i)^\tau \cdot (R_{j,t} - \mu_j)^\tau}{\sqrt{\sum_t (R_{i,t} - \mu_i)^{2\tau}} \cdot \sqrt{\sum_t (R_{j,t} - \mu_j)^{2\tau}}}
$$

With:

$$
(R_{i,t} - \mu_i)^\tau = 
\begin{cases}
R_{i,t} - \mu_i, & \text{if } R_{i,t} < VaR_{i,\tau} \\
0, & \text{otherwise}
\end{cases}
$$

This metric captures **how strongly two countries move together during extreme downside periods**, which is what matters most for energy stability and crisis management.

---

### 🔗 Step 4: Network Construction

- Each country = a **node**
- Each EDC value = a **weighted edge**

From these EDC matrices, we construct **networks** to visualize and analyze how strongly countries are connected during extreme price drops.

---

### 📊 Step 5: Network Density

To measure overall interconnectedness during crises, we compute the **network density**:

$$
\text{Density}(W) = \frac{1}{n(n-1)} \sum_{i \neq j} |W_{ij}|
$$

Where $W_{ij}$ is the EDC value between country $i$ and $j$, and $n$ is the number of countries.

A higher density indicates more **simultaneous extreme events**, suggesting increased systemic risk.

---

### 🔁 Step 6: Rolling Window Analysis

To capture the **evolution of tail risk** over time, we use a **rolling window approach**:

- **Window size**: 365 days
- **Period analyzed**: 01/01/2020 – 01/01/2024
- **Total windows**: 1,365

This approach reveals how **interconnections and vulnerabilities change dynamically**, especially around major events (e.g., the 2022 gas crisis).

---

## 📌 Summary

| Feature                  | Description                                       |
|--------------------------|---------------------------------------------------|
| Focus                   | Tail co-movements in electricity markets          |
| Metric Used             | Extreme Downside Correlation (EDC)                |
| Tail Risk Quantification| Value-at-Risk (VaR) method                        |
| Network Tool            | EDC-based dynamic networks                        |
| Time Dynamics           | Rolling 365-day window                            |
| Output                  | Evolving EDC matrices and network densities       |

---

## 📈 Applications

- **Energy system monitoring**
- **Policy stress testing**
- **Portfolio risk management**
- **Market integration analysis**

---

## 📬 Contact

For questions or collaboration, feel free to reach out or open an issue in the repository.

# ⚡ Extreme Tail Risk in European Electricity Markets

## ❗ Why It Matters

In a context of growing **instability in European energy markets**, understanding how **extreme shocks** affect the **joint behavior of electricity prices** is critical.

Traditional correlation measures (like **Pearson** or **Spearman**) fail to capture what really matters during a crisis: the **co-movement of extreme negative returns**. These are the moments when **systemic risk** emerges, threatening the stability of the entire energy system.

Electricity markets are especially sensitive due to:

- **Nonlinear and volatile price dynamics**
- Exposure to **exogenous shocks** (e.g., geopolitical tensions, weather anomalies, fuel shortages)
- Strong interconnections across countries

Monitoring these tail co-dependencies is crucial for:

- Identifying vulnerabilities in the energy system  
- Supporting **risk allocation and management**
- Designing **resilient, evidence-based energy policies**

---

## 🧠 Methodology

This study applies a **nonparametric network-based approach** to measure **tail dependence** between country-level electricity prices, focusing on the **lower tail** (i.e., extreme negative returns) using the **Extreme Downside Correlation (EDC)**.

### 🔢 Step 1: Daily Log Returns

For each country $i$, we define the **daily log return** as:

$$
R_{i,t} = 100 \times (\log P_{i,t} - \log P_{i,t-1})
$$

Where:
- $P_{i,t}$ is the day-ahead electricity price
- Returns are expressed in percentage terms

---

### ⚠️ Step 2: Tail Risk with Value-at-Risk (VaR)

To isolate extreme events, we compute the **Value-at-Risk (VaR)** at a given confidence level $\tau \in (0, 1)$:

$$
VaR_{i,\tau} = F^{-1}_{R_i}(\tau)
$$

Where:
- $F_{R_i}$ is the cumulative distribution function (CDF) of returns
- $\tau$ controls the severity (e.g., $\tau = 0.01$ captures the worst 1%)

---

### 🌐 Step 3: Extreme Downside Correlation (EDC)

The **EDC** between two countries $i$ and $j$ is defined as:

$$
EDC_{\tau,ij} = \frac{\sum_t (R_{i,t} - \mu_i)^\tau \cdot (R_{j,t} - \mu_j)^\tau}{\sqrt{\sum_t (R_{i,t} - \mu_i)^{2\tau}} \cdot \sqrt{\sum_t (R_{j,t} - \mu_j)^{2\tau}}}
$$

With:

$$
(R_{i,t} - \mu_i)^\tau = 
\begin{cases}
R_{i,t} - \mu_i, & \text{if } R_{i,t} < VaR_{i,\tau} \\
0, & \text{otherwise}
\end{cases}
$$

This metric captures **how strongly two countries move together during extreme downside periods**, which is what matters most for energy stability and crisis management.

---

### 🔗 Step 4: Network Construction

- Each country = a **node**
- Each EDC value = a **weighted edge**

From these EDC matrices, we construct **networks** to visualize and analyze how strongly countries are connected during extreme price drops.

---

### 📊 Step 5: Network Density

To measure overall interconnectedness during crises, we compute the **network density**:

$$
\text{Density}(W) = \frac{1}{n(n-1)} \sum_{i \neq j} |W_{ij}|
$$

Where $W_{ij}$ is the EDC value between country $i$ and $j$, and $n$ is the number of countries.

A higher density indicates more **simultaneous extreme events**, suggesting increased systemic risk.

---

### 🔁 Step 6: Rolling Window Analysis

To capture the **evolution of tail risk** over time, we use a **rolling window approach**:

- **Window size**: 365 days
- **Period analyzed**: 01/01/2020 – 01/01/2024
- **Total windows**: 1,365

This approach reveals how **interconnections and vulnerabilities change dynamically**, especially around major events (e.g., the 2022 gas crisis).

---

## 📌 Summary

| Feature                  | Description                                       |
|--------------------------|---------------------------------------------------|
| Focus                   | Tail co-movements in electricity markets          |
| Metric Used             | Extreme Downside Correlation (EDC)                |
| Tail Risk Quantification| Value-at-Risk (VaR) method                        |
| Network Tool            | EDC-based dynamic networks                        |
| Time Dynamics           | Rolling 365-day window                            |
| Output                  | Evolving EDC matrices and network densities       |

---

## 📈 Applications

- **Energy system monitoring**
- **Policy stress testing**
- **Portfolio risk management**
- **Market integration analysis**

---

## 📬 Contact

For questions or collaboration, feel free to reach out or open an issue in the repository.



