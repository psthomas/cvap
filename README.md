# cvap

Estimating annual county, state, and national Citizen Voting Age Population (CVAP) data from the census five year averages. This is used in some of my other [projects](https://github.com/psthomas/election-vis) where I need a CVAP estimate to calculate voter turnout by county/state.

This is the main approach:
1. Import all the census CVAP 5 year averages.
2. Assign the five year average to the central year (e.g. 2005-2009 is assigned to 2007).
3. Use linear regression to predict years not in sample (2004-2006, 2018-2021).

The estimates by county, state and nation are available in the [output](https://github.com/psthomas/cvap/tree/master/data/output) folder.

## Problems

* Assigning the five year average to the central year might over/under estimate the population if there's a rapid decline or growth in population.
* Also, the central "year" of e.g. 2005-2009 is actually 2006.5, not 2007. But I figured it would be better to use the actual data in place of a prediction if possible.