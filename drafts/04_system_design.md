# System Design

\section{System Design}
The DIC3 proposal specifies Streamlit for interaction, SQLite for inventory and usage records, Pandas for analysis, and a JSON knowledge base with Python rules for domain checks  [citation: dic3plan]. A tool-capable language model coordinates inventory retrieval, recipe search and contextual analysis. Fig.~\ref{fig:arch} illustrates the proposed flow.
\begin{figure}[t]
\centering
\setlength{\fboxsep}{5pt}
\begin{tabular}{c}
\fbox{Natural language request / Streamlit}\\[2pt]
$\downarrow$\\[2pt]
\fbox{LLM planner and tool selection}\\[2pt]
$\downarrow$\\[2pt]
\fbox{SQLite inventory + recipe retrieval}\\[2pt]
$\downarrow$\\[2pt]
\fbox{Pandas analytics + domain rules}\\[2pt]
$\downarrow$\\[2pt]
\fbox{Recommendation + uncertainty + feedback}
\end{tabular}
\caption{Proposed Food Guardian decision pipeline.}\label{fig:arch}
\end{figure}
The inventory layer is intended to store names, quantities, dates and usage events. The analytics layer aggregates consumption and disposal records. The knowledge layer considers labeling and storage context, while the decision layer checks recipe feasibility. These are proposal-level components; the source repository does not establish their implementation status.
