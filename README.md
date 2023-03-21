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


***Note to grader: I bypassed the save_csv function because I felt that the save_qualifying_loans function did everything save_csv asked but with higher user functionality. As such, I saw no reason to keep the save_csv function. 

The `app.py` notebook utilizes `Python Fire` and `Questionary` to make this application user friendly. They are used in conjunction to translate questions requiring specific "code syntax" to answer to common english, resulting in ease of use. 

# General overview

User inputs financial details.

User's financial details are processed to see whether any banks would give loans matching the user's financial background.

If there are qualifying loans, the user is asked if they want to save a csv (and where). If so, a csv is saved. Otherwise, no csv is saved.

If there are no qualifying loans, the user is notified and exited from the program.




