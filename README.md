## Cannabis Data - United States - Washington

A collection of Jupyter Notebooks exploring public *Cannabis* data from the state of Washington.

### Usage

This repository is designed to reward exploration.  As [GitHub supports static rendering of Jupyter Notebooks](https://github.com/blog/1995-github-jupyter-notebooks-3), you can view the repository's `.ipynb` Notebook files directly on GitHub.

You can also clone the repository locally to experiment with the data.  You'll need [`pipenv`](https://github.com/pypa/pipenv) to install the project's requirements:

```bash
git clone git@github.com:CannabisData/cannabis_data-united_states-washington.git
cd cannabis_data-united_states-washington
pipenv install
pipenv shell
jupyter notebook
```

The last command starts up a local [Jupyter Notebook](https://jupyter.org/index.html) server and opens the repository root in your browser.  From there you can navigate the repository, open `.ipynb` Notebook files, and experiment at will.

### Highlights

* The Washington State Liquor and Cannabis Board (WSLCB) operates a Socrata-based open data portal.  You can [find details about that platform in the README.md file](organizations/washington_state_liquor_and_cannabis_board/open_data_portal/README.md) in the organization's directory. Take a look at the Notebooks to learn about these *Cannabis* datasets:
  * [Licensed Businesses](organizations/washington_state_liquor_and_cannabis_board/open_data_portal/wslcb-portal-licensed_businesses.ipynb)
  * [Compliance Checks](organizations/washington_state_liquor_and_cannabis_board/open_data_portal/wslcb-portal-compliance_checks.ipynb)
  * [Violations](organizations/washington_state_liquor_and_cannabis_board/open_data_portal/wslcb-portal-violations.ipynb)
  * [Enforcement Visits](organizations/washington_state_liquor_and_cannabis_board/open_data_portal/wslcb-portal-enforcement_visits.ipynb)
  * [Flower Lot Wholesales](organizations/washington_state_liquor_and_cannabis_board/open_data_portal/wslcb-portal-flower_lot_wholesales.ipynb)
  * [Extract Conversions](organizations/washington_state_liquor_and_cannabis_board/open_data_portal/wslcb-portal-extract_conversions.ipynb)
  * [Usable Conversions](organizations/washington_state_liquor_and_cannabis_board/open_data_portal/wslcb-portal-usable_conversions.ipynb)
