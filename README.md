# Connect papers

## Description

**ResearchGate Scraper for visualizing reference relationships among papers from the input list**

## Usage
Put the surveyed papers in papers.txt. After running the notebook the graph is going to be saved in test.html and graph.html

Make sure to set the is_first_run variable to True when running the code for the first time. 

## Implementation details

Firstly, the paper names are checked if they are found in researchgate. If there is only a slight discrepancy between the name in ResearchGate (RG) the name is "fixed" (set to the one in RG). Further the list of names which are present in RG is made and called `ok_and_fixed`.

After that the network is built. Nodes are initialized to `ok_and_fixed` papers. For each paper in that list the scraper retrieves its citations and references and for each paper that is in `ok_and_fixed` and in the current paper's citations or references it adds a corresponding edge. For example a -> b means b is in references of a OR a is in citations of b.
