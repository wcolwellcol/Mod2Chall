# Mod2Chall
___
This is a repo for the Module 2 Challenge, specifically a loan qualifier app.

The primary application file is `app.py`.

This application interacts with the user in the CLI, accepts their personal informaiton inputs and determines loan qualification from a list of banks.
This determination is based upon 4 main filters: credit score, debt to income ratio, loan to value ratio, and the max loan size banks offer.

The [qualifier](https://github.com/wcolwellcol/Mod2Chall/tree/main/qualifier) folder contains two main folders: filters and utilities

The [filters](https://github.com/wcolwellcol/Mod2Chall/tree/main/qualifier/filters) folder contains the 4 notebooks used to filter out qualified loanees from unqualified loanees.

The [utils](https://github.com/wcolwellcol/Mod2Chall/tree/main/qualifier/utils) contains functions called upon in the various filter notebooks, mainly those in [calculators.py](https://github.com/wcolwellcol/Mod2Chall/blob/main/qualifier/utils/calculators.py)
____
### Specs on the `app.py` notebook:

The 'app.py' notebook utilizes Python Fire and Questionary to make this application user friendly. They are used in conjunction to translate questions requiring specific "code syntax" to answer to common english, resulting in ease of use. After the user's information is processed, the code will check for the length of the qualifying loans list.

If the length of qualifying loans is greater than 0, the user will have the option of specifying a path to save the loans list as a CSV.




