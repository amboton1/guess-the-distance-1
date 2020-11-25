# Guess The Distance

## Distance calculation

The goal of our game is to enable users to guess the distance between two cities, 
therefore we need to prepare our data and do some calculations.

### Step 1 - prepare data
Check out the resources directory in this task and you will find two json files.
One is countries.json and the other one is cities.json

We will use **countries.json** to get our target random cities (countires contain the capital city of each country) and we will use **cities.json** 
to find latitude and longitude for these cities so we can calculate the distance between them.

### Step 3 - write unit tests / specification
Before writing the function for calculation, let's write a sort of specification what do we expect that function will do.
We will do that by writing tests for the future calculation function. This approach is
so called [Test Driven Development (TDD)](https://en.wikipedia.org/wiki/Test-driven_development)

You are free to choose any testing tool you want but I recommend [Jest](https://jestjs.io/docs/en/getting-started) as it is very easy to get started and
it has very good documentation.

We are going to specify what the result should be when we input 2 specific latitudes and longitudes. So we need to know what we are looking for in advance.

- Go to https://www.distancecalculator.net/ and find latitudes and longitudes for 2 cities by entering cities in the fileds on the top of the page and also check 
what is the calculated distance (**note**: for some unknown reason the results on this site are not complete when entering cities in the fields on the top of the page so please append following to the root domain ```/from-zagreb-to-paris``` and then change the cities in URL)
- Write a few unit tests with sample latitude and longitude values and expected results (round up the values to be an integer and not decimal values,
for example, if the result from the page above is 105.54km round it up to be 106km)
- Make sure you write a test where the test fails if ```null``` values are provided in parameters and if values are not numbers and all those cases. 
Think of what could go wrong, cover all cases and define how should the future function behave in certain scenarios. Test all scenarios. For example, function should throw an error if a latitude of the first city is missing, or something like that.

### Step 3 - function for distance calculation
Once we specified desired behaviour and wrote unit tests, it's time to actually create the function itself.

Use [this function](https://www.geodatasource.com/developers/javascript) and clean it up a little bit and modify it so that it works only with kilometres
and that it rounds up that returned value so it is always an integer and not a decimal value.

For now, it doesn't matter where you are going to save the file and how you're going to name it as we can think of project architecture later, but for now it can 
be something like ```/utils/distance-calculator.js```

Make sure that all tests are passing.

