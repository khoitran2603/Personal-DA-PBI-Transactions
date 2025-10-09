# Introduction

### About the Project
This project analyses my personal bank transactions from January to August 2025 to evaluate whether I am living below my means — that is, whether my monthly spending consistently stays within my income.

### The Question
“If I earn around $4,000 per month, do I live below my means — or do my expenses exceed what I make?”

This report answers that by looking at monthly cash flow — how much money came in, how much went out, and whether I ended each month in surplus or deficit.

Rather than aiming for investment or savings targets, the focus here is cash behaviour realism — how money actually flows through daily life, influenced by events, convenience, and commitments.

### Project Challenge
Personal finance data is often **unstructured, inconsistent, and event-driven**, making meaningful analysis difficult.
My biggest challenge was to **standardise multiple bank exports** (ANZ, Westpac, etc.) into one consistent dataset and classify transactions that mix essentials (rent, utilities) with one-off events (travel, car insurance).

<p align="center">
  <table>
    <tr>
      <td align="center">
        <img src="docs/data_raw.png" width="100%"/><br />
        <em>Westpac raw dataset</em>
      </td>
      <td align="center">
        <img src="docs/data_raw_anz.png" width="100%"/><br />
        <em>ANZ raw dataset</em>
      </td>
    </tr>
  </table>
</p>

Therefore, instead of focusing on daily precision, I built a system designed for monthly accuracy, allowing me to observe realistic spending trends while accepting small timing delays in transaction posting.

# Project Building Summary (SQL)

- Merge multiple bank formats (ANZ, Westpac) into one unified dataset.
- Clean and normalise descriptions, removing card numbers and repeated prefixes.
- Automatically classify categories using pattern matching (e.g., “APPLE.COM” → Entertainment).
- Extract locations from text strings by matching against a Melbourne suburb dictionary.

  <p align="center">
  <img src="docs/dataset_clean.png" width="70%"/>
  <br />
  <em>Cleaned Dataset (combined)</em>
</p>

# Results
You can download the Power BI dashboard [here*](https://github.com/khoitran2603/Personal-DA-PBI-Transactions/blob/main/Spending%20Dashboard.pbix)

  <p align="center">
  <img src="docs/dashboard.png" width="80%"/>
  <br />
  <em>Monthly Transactions Dashboard</em>
</p>

## Income vs Expense Overview
(Linked to Visual 1: Monthly Income vs Expense Trend)

- Over 8 months, my total spending ($33,285) nearly equals my total income ($33,230), leaving a small deficit of -$55.
- While most months' expenses stayed below income, overspending would happen on occasion, for instance, from March-April, I spent approximately 25-45% more than my income for family travel and hosting when they come from overseas to visit. 

🟢This indicates tight balance control, in which I am essentially living within my means when not influenced by special events.
  
## Cash Flow Over Time
(Linked to Visual 2: Cumulative Net Cash Flow)

This chart tracks how my cash position evolved over eight months.
- The cumulative balance rose early in the year and reached its highest point in February ($1,536), then dipped sharply and reached its lowest point in May (-$3,000) before recovery onward.
  
"This shows strong control where short-term overspending doesn't create long-term imbalance."

- Even with high fluctuations but minor, the cumulative line ends still close to zero, confirming that I operated at or slightly below my means, with no sustained deficit.

## Spending Structure & Flexibility
(Linked to Visual 3: Expense Composition — Doughnut Chart)

To evaluate whether I’m living below my means, I grouped my spending into four structural types:

|**Type**|**Flexibility**|**Description**|
| :- | :- | :- |
|Fixed|None|Rent, utilities, subscriptions - unavoidable costs.|
|Semi-fixed|Low|Vehicle, groceries - somewhat controllable.|
|Flexible|High|Eating out, entertainment, retail - lifestyle-driven.|
|Other|Varies|New or irregular categories.|

- More than half of my budget is locked into predictable commitments, creating a reliable financial base cost.

🎯The flexible cost (27%) is the deciding factor in whether I live below my means. It represents my lifestyle and choice-driven spending.

- By trimming flexible costs by just 5-10%, I could ensure a consistent extra ~$100 per month without affecting essential comfort.

## Flexible Spending Breakdown
(Linked to Visual 4: Category Deep-Dive — Bar Chart)

Within flexible costs:
- Eating Out accounts for the largest share (39%), made by medium and frequent purchases (106 transactions)
- Fun & Vacation (26%) appears as one-time spikes (March-April)
- Retail Shopping (21%) follows, reflecting weekend and social spending

🍔 Most flexible spending ties to convenience or social activities, not impulsive luxury.

Visual 4 highlights how small daily choices (fast food, coffee, short outings) collectively influence whether I stay below my means. This visibility turns “overspending” into precise, measurable, and adjustable.

## Location Patterns
(Linked to Visual 5: Location-Aware Map)

Inner Melbourne (Melbourne + Southbank), Local Suburb (Caulfield), and Workplace Suburb (Springvale) are where I spent most of my money, which reflects how I live:
- **Inner Melbourne (CBD)**: Mainly on weekends, mostly for eating at restaurants, parking, and retail shopping such as clothes, electronics, and home furniture. 
- **Local Suburbs**: Over 80% spend on groceries for everyday needs, eating out (15%) mostly for fast food + convenience tied to daily walking habit.
- **Workplace Suburb**: For lunch break eating and after-work groceries.

Visual 5 shows that high-spend areas align with planned or convenient locations, not random or wasteful ones

🗺️ Location spending validates behaviour logic — even flexible spending is practical.

## Key Takeaways
1. **Housing dominates** at 43%, anchoring spending every month.
2. **Car costs were irregular but heavy** (insurance + plate renewal), not everyday fuel.
3. **Family visits** explain the sharpest spikes in March–April.
4. **Daily convenience** (fast food, local shops, subscriptions) shaped much of the flexible spending.
5. With a small net deficit (–$55), reducing flexible spend by 10–15% would easily bring me back into surplus.

# Conclusion
This project transformed eight months of personal transactions into clear spending insights. By cleaning, categorising, and automating the data in SQL, I uncovered how fixed costs anchor my budget while events and convenience choices shape the rest. It showed how real-life financial data can tell meaningful stories — and how small adjustments, like reducing flexible costs, can quickly improve stability.
