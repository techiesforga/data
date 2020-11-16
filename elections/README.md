# elections

---

## - `2020_november`
#### Contains results data for all November 2020 elections in Georgia
Source: Georgia Secretary of State - http://results.enr.clarityelections.com/GA/105369/
##### Key data:
  - `all_counties_joined` - a CSV file for each race in the november 2020 elections (159 total counties)
    - data includes total votes for each candidate in each race, including the type of votes (advanced, absenteee, in-person)
    - also includes total number of registered voters in each county
  - `all_precincts_joined` - same as above, but much more granular (2,500+ total precincts)
    - includes total number of registered voters and number of votes for each candidate it each precinct

---

## - `recent_runoff_elections`
#### Contains voter participation data (including ethnic demographics) from the 3 most recent statewide elections with run-offs 
Source: GA Secretary of State -  0 https://sos.ga.gov/index.php/Elections/voter_registration_statistics
##### Key data:
  - `{election date}_cleaned` - contains demographic (race & sex) statistics comparing voter participation in regular vs. run-off elections based on three recent state-wide runoff elections in Georgia.   
  - Files contain data for both elections and calculated comparison features. There are three versions of each election for different levels of granularity: statewide, by county, and by electoral precinct.
    - columns starting with `init` hold data from the initial round of the given election 
    - columns starting with `runoff` hold data from the second, run-off round of the given election 
    - columns ending in `Change` are calculated differences in voter participation between both rounds of the election
      - percent change in participation (`ParticipationChange`) is calculated as (the difference between the number of voters in each election) divided by (the total number of registered voters at the time of the initial election)

