# Module 2 Challenge- Loan Qualifier App
___
This is a repo for the Module 2 Challenge, specifically a loan qualifier app. The problem I am attempting to solve is for a user to to identify banks from which they can successfully apply for loans from given certain financial background details.

## Technologies
This code was written using Python 3.7.13.
My OS is Ventura 13.2.1 though it should be fine on most others. Note that the CLI in any screenshots may look different on different OSs.
I used conda to manage all of my packages.
Packages used:
fire 0.5.0
csv 1.0
quesitonary 1.10.0

Note: I also utilized built-in modules for Python (sys)

## Installation
All of these can be installed using `pip install <package here>` in your CLI.
For example,
`pip install questionary`
`pip install fire`

If you are unsure of what python version (if any) you have, here is a handy link to troubleshoot those issues. 
[Installing python](https://realpython.com/installing-python/)



The primary application file is `app.py`.

This application interacts with the user in the CLI, accepts their personal information inputs and determines loan qualification from a list of banks.
This determination is based upon 4 main filters: credit score, debt to income ratio, loan to value ratio, and the max loan size banks offer.

The [qualifier](https://github.com/wcolwellcol/Mod2Chall/tree/main/qualifier) folder contains two main folders: filters and utilities

The [filters](https://github.com/wcolwellcol/Mod2Chall/tree/main/qualifier/filters) folder contains the 4 notebooks used to filter out qualified loanees from unqualified loanees.

The [utils](https://github.com/wcolwellcol/Mod2Chall/tree/main/qualifier/utils) contains functions called upon in the various filter notebooks, mainly those in [calculators.py](https://github.com/wcolwellcol/Mod2Chall/blob/main/qualifier/utils/calculators.py). [fileio.py](https://github.com/wcolwellcol/Mod2Chall/blob/main/qualifier/utils/fileio.py) contains csv reader and writer functions.

At the core of `calculators.py` are two calculations: the monthly debt ratio and loan to value ratio. These are calculated as follows:
```
def calculate_monthly_debt_ratio(monthly_debt_payment, monthly_income):
    """Calculates users monthly debt to income ratio.

    Args:
        monthly_debt_payment (int): The total monthly debt.
        monthly_income (int): The total monthly income.

    Returns:
        The monthly debt ratio
    """
    monthly_debt_ratio = int(monthly_debt_payment) / int(monthly_income)
    return monthly_debt_ratio


def calculate_loan_to_value_ratio(loan_amount, home_value):
    """Calculates users loan to value ratio based on inputs.

    Args:
        loan_amount (int): The requested loan amount.
        home_value (int): The home value.

    Returns:
        The loan-to-value ratio.
    """
    loan_to_value_ratio = int(loan_amount) / int(home_value)
    return loan_to_value_ratio
```
____
# Specs on the `app.py` notebook:

The `app.py` notebook utilizes [Python Fire](https://github.com/google/python-fire) and [Questionary](https://github.com/tmbo/questionary) to make this application user friendly and able to run from the CLI. They are used in conjunction to translate questions requiring specific "code syntax" to answer to common english, resulting in ease of use. 

### `app.py` workflow

1. User inputs financial details.

2. User's financial details are checked against the details held in [daily_rate_sheet.csv](https://github.com/wcolwellcol/Mod2Chall/tree/main/data) to see whether any banks would give loans matching the user's financial background..

3a. If there are qualifying loans, the user is asked if they want to save a csv (and where). If so, a csv is saved (calling a function from fileio.py). Otherwise, no csv is saved.

3b. If there are no qualifying loans, the user is notified and exited from the program.

This workflow looks like this in the user's terminal:

![workflow of CLI](/Users/willcolwell/Desktop/Screenshot 2023-03-26 at 11.16.37 PM.png)


## Contributors

This code was written by me, but the framework was provided by the Columbia Fintech Bootcamp

## License

MIT License

Copyright (c) [year] [fullname]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

