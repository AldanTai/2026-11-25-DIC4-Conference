# Experimental Setup

\section{Experimental Setup}
The DIC3 plan proposes approximately 20--30 ingredients, 20--30 recipes and 30 household scenarios  [citation: dic3plan]. Each scenario should specify inventory quantities, units, relevant dates, known storage conditions and a meal request. Human-reviewed expected outputs should be recorded before evaluation.

The baseline is a generic LLM recipe recommendation without access to actual inventory. Both systems should receive the same meal request; the proposed system additionally retrieves structured inventory as part of its design. The comparison therefore measures the value of the integrated workflow, not isolated model superiority. Use the same model and generation settings where possible, and record failures.

For each scenario, score the first recipe returned by each system against the same inventory snapshot. Recipe feasibility rate is the fraction of scenarios with a verified quantity-feasible first recipe. A missing recipe or a recipe with unverified quantities does not count as a success. Inventory matching rate is the fraction of required ingredient entries with sufficient stock, pooled across scorable recipes. Report the number of scorable recipes and the frequency of missing and unknown entries alongside that rate.

For reminder accuracy, prelabel each evaluated ingredient case as reminder warranted, no reminder warranted, or clarification needed. Divide the number of correct labels by the total number of labeled cases. A missing response is scored as incorrect. Report per-label counts so that accuracy can be interpreted in light of class imbalance. The annotation protocol and sample counts must be finalized before testing.
