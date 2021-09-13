# CovidEnforcementScotland

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/groegercesg/CovidEnforcementScotland/HEAD?urlpath=voila%2Frender%2Fvoila_map.ipynb)

## Help

### *"Arrgh this is taking forever"*

- **This takes 70 seconds to load**
- Check "Build Logs", if it says: `failed to connect to event stream` then reload the website.
- Be a bit more patient, it does naturally take a while - there's a lot of data to crunch and metre accurate maps to create.

## Todo

- [x] Do we have to remake the map twice, as we do not, triggered once by selection and again by final resting point
- [x] Recency of data, we talk about when the range of the data, we can do this programmatically
    - Redo the description
    - Make better reference of the classifications
- [x] Absolute handling:
    - Turn all mentions of absolute, into "Total"
    - Do it in the RHS text as well
- [x] First release
    - Update readme
    - Binder setup
    - Finalise description on side bar of HTML
    - Change title
- [x] Pull in data about police numbers
    - Put this in as an option for comparative visualisation
    - Data from: https://www.scotland.police.uk/about-us/police-scotland/police-scotland-officer-numbers/
- [x] Average number of "enforcement type" per day
    - take Number of "enforcement type" in period given by slider
    - divide by number of days
    - to get average
- [ ] Implement a darkmode
    - Maybe we could use `--theme=dark` and then make the Cartopy output background transparent
- [ ] Check and download new data
    - Every time this runs, it should check to see if there's new data.
    - For the CVI enforcement
    - Maybe it should have always been transparent?
- [ ] Make text for the date range not be cut off
    - ❌ This can't be done, see: https://github.com/jupyter-widgets/ipywidgets/issues/2318

## Updating Packages

We have packages required for the deployment on [Binder](https://mybinder.org/), but due to the complexities of Cartopy being difficult we need to list our packages in two different ways: [Conda](https://docs.conda.io/en/latest/) and [requirements.txt](https://github.com/binder-examples/requirements)

### For Conda

#### Updating conda

`$ conda update -n MAIN --all`

From our conda environment (my local one is called: `MAIN`), we can export the requirements to `environment.yml` using the command:

- `$ conda env export -n MAIN > environment.yml`
- Next add the following line to the file:
    ```
    ...
    pip:
        ...
        voila==0.2.10
    ```

### For Requirements.txt

#### Updating PIP

`$ pip list --outdated --format=freeze | grep -v '^\-e' | cut -d = -f 1  | xargs -n1 pip install -U`

Requirements are stored in `requirements.in` these are then generated into a frozen: `requirements.txt` file to be used by Binder. To Update Requirements:

- Take the new module and put into `requirements.in`
- Next add the following line to the file:
    ```
    ...
    voila
    ```
- Then run the console command: `$ pip-compile requirements.in`

## Visualisation Explanations

### Officer Numbers

Police Scotland supplement local police officer resources by specialist resources that are organised at a regional and national level. As such exact numbers of individual officers within a Division may fluctuate due to operational demands. These allocations, understandably, aren't published and hence the decision has been taken to not include these supplemental regional and national resources in our officer numbers.

## File List

## Data Providence

Covid Enforcement Data: 
- https://www.scotland.police.uk/about-us/covid-19-police-scotland-response/enforcement-and-response-data/

Police Scotland Divisions: 
- https://spatialdata.gov.scot/geonetwork/srv/eng/catalog.search;jsessionid=61F713CF39B3EE2F440F48E9C31BA806#/metadata/4364af71-167a-4236-b5a0-bd4109913231

