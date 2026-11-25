# Introduction

\section{Introduction}
The 2024 Food Waste Index estimates that households generated approximately 60\% of the food wasted across households, food service, and retail in 2022  [citation: unep2024]. Meal planning depends on knowing which ingredients are on hand, how much is available, and how they have been stored. The U.S. Food and Drug Administration identifies confusion about date labels as a contributor to consumer food waste  [citation: fdafoodwaste].

Inventory tracking gives households a record of available ingredients. Date-label guidance helps users interpret package dates, while storage guidance addresses conditions that a date alone cannot capture  [citation: fdafoodwaste]. Tool-using language models can retrieve external information during reasoning, as demonstrated by ReAct  [citation: yao2023]. For this application, inventory records and date guidance each answer part of the meal-planning question. An inventory-unaware language model can generate recipes, but its input supplies no structured evidence that the household has enough of each ingredient.

Food Guardian combines four elements from the DIC3 plan: natural language interaction, agentic decision-making, food safety and context awareness, and data-driven food management  [citation: dic3plan]. The proposed planner retrieves household inventory and recipe candidates. Structured checks assess quantities and storage context, and the response exposes missing information. The paper contributes this design and a protocol for evaluating recommendation feasibility, inventory matching, and reminder accuracy.

The remainder of the paper reviews related work, describes the decision method and system design, and presents the experimental setup and pending results. It then discusses limitations and future validation.
