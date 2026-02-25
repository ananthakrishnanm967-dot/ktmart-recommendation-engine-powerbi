KT Mart Product Recommendation Engine
Project Overview

KT Mart is a Melbourne-based Asian grocery retailer whose website organizes products primarily by category (e.g., noodles, sauces, snacks, frozen foods). While this enables structured browsing, it does not support intelligent cross-selling or complementary product discovery. Customers are not guided toward relevant add-ons, basket expansion opportunities remain underutilized, and no structured visibility exists into product relationships across the catalog.

This project designs a content-based product recommendation engine using publicly available catalog data to uncover meaningful product associations without relying on transaction history.

Business Objective and Strategic Value

The objective of this project is to identify logical product relationships and transform static catalog data into actionable retail intelligence.

The system enables:

Cross-selling opportunities

Increased average basket size

Improved product discoverability

A scalable recommendation layer independent of historical purchase data

This approach is particularly valuable for small-to-medium retailers that lack structured transaction datasets. It demonstrates that even without behavioral logs, product metadata alone can reveal structured relationships capable of driving commercial value.

Recommendation Approach

The system uses a content-based filtering framework. Instead of modeling customer purchase history, it evaluates intrinsic product attributes such as:

Category

Keywords within product descriptions

Product naming structure

Each product is transformed into a numerical feature vector using TF-IDF vectorization and structured category encoding. Cosine similarity is applied across product vectors to compute pairwise similarity scores ranging from 0 to 1.

Similarity interpretation:

High similarity indicates close substitutes or highly related items

Moderate similarity suggests complementary or context-based relationships

Low similarity reflects weak association

For each product, the model ranks all other products and returns the top five most similar items.

Key Analytical Insights
Appliance Products (Rice Cookers)

Appliance products form tightly clustered substitution groups. Recommendations primarily surface alternative models or upgrades within the same appliance category.

Business interpretation:
These products behave as substitution clusters rather than cross-selling drivers. They are ideal for price or feature comparison strategies.

Honey Strength Variants (UMF 5+, 10+, 15+)

Different strength variants exhibit extremely high similarity scores and strong internal clustering.

Business interpretation:
These products are well suited for comparison-based recommendation modules, enabling customers to evaluate grade differentiation clearly.

Noodles and Sauces

Moderate similarity patterns emerge between noodle products and sauce items due to shared culinary context in product descriptions.

Business interpretation:
This reveals bundling potential, such as:

Noodles paired with sauces

Kimchi paired with meat

Dumplings paired with dipping sauces

These represent cross-category expansion opportunities.

Category Diversity Indicator

Some products generate recommendations confined to a single category, while others extend across multiple categories.

Business implication:
Products with broader category spread act as stronger cross-sell anchors. Identifying these anchors supports smarter merchandising and promotional placement.

Simulated Commercial Impact

A simplified revenue uplift simulation was conducted under conservative assumptions:

Five percent recommendation engagement rate

Thirty-five dollar average basket value

Even under modest engagement, recommendation exposure produces measurable incremental uplift per interaction. While simulated, the model demonstrates how recommendation logic can scale into meaningful revenue impact with real traffic volumes.

Methodology
Data Collection

Publicly available catalog data was structured into a unified dataset including:

Product name

Category

Product description

Source links

No internal sales or confidential data was used.

Feature Engineering

Text preprocessing on product descriptions

Category encoding

TF-IDF vectorization to convert text into numerical feature space

Similarity Modeling

Cosine similarity applied across product vectors

Full similarity matrix generated

Top five recommendations extracted per product

Business Interface

Results were exported into a structured dataset and visualized in Power BI.

Dashboard components include:

Product selection filter

Ranked recommendation table

Similarity strength indicators

Cross-category diversity metric

Simulated uplift indicator

Limitations

This model does not incorporate:

Transaction-level purchase data

Customer behavior modeling

Collaborative filtering

Validated revenue experimentation

The uplift metric is simulated rather than empirically tested.

The system focuses strictly on catalog-based intelligence.

Future Enhancements

Integration with real basket transaction data

Collaborative filtering implementation

Real-time API deployment

A/B testing for conversion measurement

Bundle optimization logic

Conclusion

This project demonstrates how structured product relationship mapping can be built using only publicly available catalog data.

It provides:

Actionable cross-selling insight

A scalable recommendation framework

A bridge between data science and retail strategy

The system functions as a foundational recommendation layer capable of evolving into a full-scale behavioral engine once transactional data becomes available.

It illustrates how analytical rigor can transform static retail catalogs into intelligent merchandising systems.
