# data-wrangling
Data Wrangling
We can see below that some of the rows are missing values in our dataset.

data_falcon9.isnull().sum()
FlightNumber       0
Date               0
BoosterVersion     0
PayloadMass        5
Orbit              0
LaunchSite         0
Outcome            0
Flights            0
GridFins           0
Reused             0
Legs               0
LandingPad        26
Block              0
ReusedCount        0
Serial             0
Longitude          0
Latitude           0
dtype: int64
Before we can continue we must deal with these missing values. The LandingPad column will retain None values to represent when landing pads were not used.

Task 3: Dealing with Missing Values
Calculate below the mean for the PayloadMass using the .mean(). Then use the mean and the .replace() function to replace np.nan values in the data with the mean you calculated.

# Calculate the mean value of PayloadMass column
payload_mean = data_falcon9['PayloadMass'].mean()
# Replace the np.nan values with its mean value
data_falcon9['PayloadMass'] = data_falcon9['PayloadMass'].replace(np.nan, payload_mean)
print(data_falcon9['PayloadMass'].isnull().sum())
0
You should see the number of missing values of the PayLoadMass change to zero.

Now we should have no missing values in our dataset except for in LandingPad.
