# CovidEnforcementScotland

## Todo

- [x] Do we have to remake the map twice, as we do not, triggered once by selection and again by final resting point
- [x] Recency of data, we talk about when the range of the data, we can do this programmatically
    - Redo the description
    - Make better reference of the classifications
- [x] Absolute handling:
    - Turn all mentions of absolute, into "Total"
    - Do it in the RHS text as well
- [ ] First release
    - Update readme
    - Binder setup
    - Finalise description on side bar of HTML
- [ ] Pull in data about police numbers
    - Put this in as an option for comparative visualisation
    - Data from: https://www.scotland.police.uk/about-us/police-scotland/police-scotland-officer-numbers/
- [ ] Check and download new data
    - Every time this runs, it should check to see if there's new data.
    - For the CVI enforcement
- [ ] Make text for the date range not be cut off
    - ❌ This can't be done, see: https://github.com/jupyter-widgets/ipywidgets/issues/2318

## Update Requirements

- We need to add in `voila`

### Now we use Conda

From our conda environment (my local one is called: `MAIN`), we can export the requirements to `environment.yml` using the command:

- `$ conda env export -n MAIN > environment.yml`

### Old Steps

Requirements are stored in `requirements.in` these are then generated into a frozen: `requirements.txt` file to be used by Binder. To Update Requirements:

- Take the new module and put into `requirements.in`
- Then run the console command: `$ pip-compile requirements.in`

## Data Providence

Covid Enforcement Data: 
- https://www.scotland.police.uk/about-us/covid-19-police-scotland-response/enforcement-and-response-data/

Police Scotland Divisions: 
- https://spatialdata.gov.scot/geonetwork/srv/eng/catalog.search;jsessionid=61F713CF39B3EE2F440F48E9C31BA806#/metadata/4364af71-167a-4236-b5a0-bd4109913231

