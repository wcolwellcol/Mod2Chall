# Mod2Chall
___
This is a repo for the Module 2 Challenge, specifically a loan qualifier app.

The primary application file is 'app.py'.

This application interacts with the user in the CLI, accepts their personal informaiton inputs and determines loan qualification from a list of banks.
This determination is based upon 4 main filters: credit score, debt to income ratio, loan to value ratio, and the max loan size banks offer.

The [filters](url) folder contains the 4 notebooks used to filer out qualified loanees from unqualified loanees.

The [filters](url) folder contains functions that are stored in the [utils](folder), specifically [calculators.py](url)
____
### Specs on the 'app.py' notebook:

The 'app.py' notebook utilizes Python Fire and Questionary to make this application user friendly. They are used in conjunction to translate questions requiring specific "code syntax" to answer to common english, resulting in ease of use. After the user's information is processed, the code will check for the length of the qualifying loans list.

If the length of qualifying loans is greater than 0, the user will have the option of specifying a path to save the loans list as a CSV.




