# MSDS 460 Assignment 3: Integer Programming - Algorithmic Redistricting

This assignment gave us the chance to learn about constrained optimization and integer programming by attempting to optimize the redistricting of Tennessee's 95 counties into 9 distrcicts with linear and integer programming in Python. The key focuses for the optimization process are population balance, contiguity, and distance minimization. We used county and population data from the United States Census Bureau to better understand the problem of algorithmic redstricting and forming our constraints. The first constraint ensures that each county is assigned to exactly one district by requiring that the sum of its district assignments equals one. The second constraint enforces the principle of one-person-one-vote by requiring that the population of each district remains between 50% and 150% of the target population, which is the state's total population divided by the number of districts. This ensures equal representation across districts. The third constraint guarantees geographic contiguity by ensuring that a county can only be part of a district if at least one of its neighboring counties is also assigned to the same district. This prevents the formation of disjointed districts and maintains logical geographical boundaries. Finally, the fourth constraint ensures that the model properly tracks which pairs of counties belong to the same district, allowing the objective function to minimize intra-district distances accurately. The objective function itself aims to create geographically compact districts by minimizing the total distance between counties within each district, using geographic coordinates to calculate distances. Given the complexity of the problem, and multiple attempts to optimize the whole tate that lead to run times over 24 hours that never actually output a result, we split Tennessee into smaller groupings of contiguous counties to have the adjacency constraint apply. By iterating over smaller chunks and opening up the population minimum and maximum constraint, we were able to create a model that assigns most counties to districts. While the populations of the counties are fairly similar, there are a few outliers, District 6 has a population of 546,268 while District 9 has a population of 929,744. Overall, our model demonstrates how proper data-driven solutions can improve fair redistricting efforts. Future improvements could balance the districts further, adhering to political guidelines better and not requiring the manual assignment of any districts.



