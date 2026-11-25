# Related Work

\section{Related Work}
\subsection{Tool Use and Inventory-Aware Planning}
ReAct interleaves language-model reasoning with actions that retrieve evidence from an external environment  [citation: yao2023]. Its benchmarks motivate using tools to ground responses. MealMind extends that general idea to household planning through camera-based stock capture, spoilage prioritization, and an LLM planner  [citation: mealmind2025]. Its preprint reports a survey, interviews, and a prototype. The proposed reductions in planning time and waste still require outcome validation.

\subsection{Household Food Management}
Van Rooijen et al.\ formulate weekly meal planning as a mathematical program that accounts for recipe requirements, package sizes, costs, and environmental impact  [citation: rooijen2024]. Their modeled outcomes illustrate why the unit of measurement matters when evaluating waste. The Food Waste Index describes how to measure waste at household scale  [citation: unep2024], and FDA consumer guidance motivates distinguishing quality dates from storage context in reminders  [citation: fdafoodwaste].

\begin{table*}[t]
\caption{Comparison of prior methods and their evidence.}\label{tab:prior-work}
\centering\footnotesize
\begin{tabular}{@{}p{.13\textwidth}p{.14\textwidth}p{.18\textwidth}p{.20\textwidth}p{.24\textwidth}@{}}
\toprule
Reference & Problem & Method and domain inputs & Evaluation data & Findings and scope \\
\midrule
ReAct (2023)  [citation: yao2023] & Ground language-model decisions & Reasoning and external actions & Question answering, fact verification, and interactive benchmarks & Demonstrates tool-grounded reasoning on benchmark tasks. Household inventory and storage are outside its scope. \\
Van Rooijen et al.\ (2024)  [citation: rooijen2024] & Plan meals and shopping to reduce waste & Mathematical programming with recipes, package sizes, nutrition, and environmental measures & Modeled weekly meal plans with retail package sizes & Shows that modeled meal plans can avoid unused food under specified constraints. Outcomes come from the model. \\
MealMind (2025 preprint)  [citation: mealmind2025] & Reduce meal-planning burden and prevent waste & Camera inventory, spoilage ranking, and LLM planning & 82 complete survey responses, five interviews, and a mobile prototype & Reports user needs and demonstrates a prototype. Waste reduction remains a hypothesis. \\
\bottomrule
\end{tabular}
\end{table*}

\subsection{Research Gap}
Table~\ref{tab:prior-work} shows how these approaches address tool use, weekly optimization, and stock-aware planning. Food Guardian focuses on auditable, request-level decisions with a recorded inventory snapshot, ingredient quantities, and explicit storage uncertainty. Its evaluation asks whether these checks yield feasible suggestions and accurate reminders relative to an inventory-unaware baseline.
