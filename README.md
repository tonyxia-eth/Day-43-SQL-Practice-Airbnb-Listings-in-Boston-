# Day 43 – SQL Practice: Airbnb Listings in Boston 🏙️

Today was a long workday, so I kept it light — but still productive. I tackled three small but effective SQL tasks using the Boston Airbnb listings and availabilities dataset as part of CS50's Introduction to Databases with SQL (Lesson 4).

## 🧠 Tasks Completed

### 1. Find the Top 10 Most Reviewed Listings
```sql
SELECT l.id, l.host_name, COUNT(r.id) AS review_count
FROM listings l
JOIN reviews r ON l.id = r.listing_id
GROUP BY l.id
ORDER BY review_count DESC
LIMIT 10;


✔️ Identified the listings with the highest engagement based on total review count.

SELECT property_type, avg_price
FROM (
  SELECT l.property_type, AVG(a.price) AS avg_price
  FROM listings l
  JOIN availabilities a ON l.id = a.listing_id
  GROUP BY l.property_type
)
WHERE avg_price > 150
LIMIT 10;

 Practiced subqueries and aggregation to filter high-cost property types.
✔️ Learned that in SQLite, an alias for subqueries is optional if unambiguous!


SELECT l.id, l.host_name, a.price, l.property_type
FROM listings l
JOIN availabilities a ON l.id = a.listing_id
WHERE l.property_type LIKE 'Private%' AND a.price < 100
LIMIT 10;


✔️ Used a LIKE clause for pattern matching property types and filtered for budget-friendly options.

💡 Takeaways
Subqueries can be clean and readable, especially in SQLite without requiring an alias.

Filtering on joined table fields (like price from availabilities) was crucial.

Keeping the daily habit alive matters more than intensity — even on long days.
Next Steps
Continue building views and practicing CREATE VIEW and INSTEAD OF triggers.

🗓️ Day 43 of #100DaysOfSQL
📚 Dataset: Airbnb Listings (Boston)
🏷️ #DataAnalytics #SQL #Subqueries #SQLite #TableJoins #PortfolioBuilding
