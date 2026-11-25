# Methodology

\section{Methodology}
The proposed workflow maps a natural language request to a structured intent, retrieves inventory and recipe candidates, and checks ingredient availability and storage-related constraints. Let $q_i$ denote the required quantity of ingredient $i$ and $a_i$ the available quantity expressed in a compatible unit. A candidate is quantity-feasible if $a_i\geq q_i$ for every required ingredient. Missing or incompatible units are reported as unknown rather than assumed sufficient.

For each candidate, the agent returns a feasibility status, missing ingredients, relevant date or storage reminders and an explanation. A proposed priority policy favors suitable ingredients that need earlier use, subject to contextual constraints. The language model is responsible for interpreting requests and communicating findings; deterministic checks supply the factual inventory status. For example, the planner can check whether the recorded eggs and tomatoes suffice for a candidate dish. If the storage history of milk is missing, the explanation requests clarification and the candidate does not receive a priority boost for using that milk. A reminder is not a certification of food safety.

Algorithm~1 (Fig.~\ref{alg:guardian}) summarizes the proposed decision logic. Candidate ranking favors confirmed feasible options and counts urgency only for ingredients whose storage context supports prioritization.

\begin{figure}[t]
\footnotesize
\begin{enumerate}
\setlength{\itemsep}{1pt}
\setlength{\parsep}{0pt}
\item Parse the meal request into servings and constraints.
\item Retrieve the inventory snapshot and candidate recipes.
\item Scale each recipe to the requested servings.
\item For each ingredient, normalize compatible quantities and mark stock as sufficient, insufficient, or unknown.
\item Review label and storage context. Record a reminder or request clarification when evidence is missing.
\item Mark recipe feasibility from the ingredient checks. Exclude unsupported urgency from the priority score.
\item Rank candidates and return the stock evidence, missing items, reminders, and uncertainties.
\end{enumerate}
\caption{Algorithm 1. Proposed Food Guardian recommendation procedure.}
\label{alg:guardian}
\end{figure}
