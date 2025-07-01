# Aviation Risk Assessment

## Loading and Pre-processing




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Event.Id</th>
      <th>Investigation.Type</th>
      <th>Accident.Number</th>
      <th>Event.Date</th>
      <th>Location</th>
      <th>Country</th>
      <th>Latitude</th>
      <th>Longitude</th>
      <th>Airport.Code</th>
      <th>Airport.Name</th>
      <th>...</th>
      <th>Purpose.of.flight</th>
      <th>Air.carrier</th>
      <th>Total.Fatal.Injuries</th>
      <th>Total.Serious.Injuries</th>
      <th>Total.Minor.Injuries</th>
      <th>Total.Uninjured</th>
      <th>Weather.Condition</th>
      <th>Broad.phase.of.flight</th>
      <th>Report.Status</th>
      <th>Publication.Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>20001218X45444</td>
      <td>Accident</td>
      <td>SEA87LA080</td>
      <td>1948-10-24</td>
      <td>MOOSE CREEK, ID</td>
      <td>United States</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>Personal</td>
      <td>NaN</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>UNK</td>
      <td>Cruise</td>
      <td>Probable Cause</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>20001218X45447</td>
      <td>Accident</td>
      <td>LAX94LA336</td>
      <td>1962-07-19</td>
      <td>BRIDGEPORT, CA</td>
      <td>United States</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>Personal</td>
      <td>NaN</td>
      <td>4.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>UNK</td>
      <td>Unknown</td>
      <td>Probable Cause</td>
      <td>19-09-1996</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20061025X01555</td>
      <td>Accident</td>
      <td>NYC07LA005</td>
      <td>1974-08-30</td>
      <td>Saltville, VA</td>
      <td>United States</td>
      <td>36.922223</td>
      <td>-81.878056</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>Personal</td>
      <td>NaN</td>
      <td>3.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>IMC</td>
      <td>Cruise</td>
      <td>Probable Cause</td>
      <td>26-02-2007</td>
    </tr>
    <tr>
      <th>3</th>
      <td>20001218X45448</td>
      <td>Accident</td>
      <td>LAX96LA321</td>
      <td>1977-06-19</td>
      <td>EUREKA, CA</td>
      <td>United States</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>Personal</td>
      <td>NaN</td>
      <td>2.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>IMC</td>
      <td>Cruise</td>
      <td>Probable Cause</td>
      <td>12-09-2000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>20041105X01764</td>
      <td>Accident</td>
      <td>CHI79FA064</td>
      <td>1979-08-02</td>
      <td>Canton, OH</td>
      <td>United States</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>Personal</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>NaN</td>
      <td>0.0</td>
      <td>VMC</td>
      <td>Approach</td>
      <td>Probable Cause</td>
      <td>16-04-1980</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 31 columns</p>
</div>



    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 88889 entries, 0 to 88888
    Data columns (total 31 columns):
     #   Column                  Non-Null Count  Dtype  
    ---  ------                  --------------  -----  
     0   Event.Id                88889 non-null  object 
     1   Investigation.Type      88889 non-null  object 
     2   Accident.Number         88889 non-null  object 
     3   Event.Date              88889 non-null  object 
     4   Location                88837 non-null  object 
     5   Country                 88663 non-null  object 
     6   Latitude                34382 non-null  object 
     7   Longitude               34373 non-null  object 
     8   Airport.Code            50249 non-null  object 
     9   Airport.Name            52790 non-null  object 
     10  Injury.Severity         87889 non-null  object 
     11  Aircraft.damage         85695 non-null  object 
     12  Aircraft.Category       32287 non-null  object 
     13  Registration.Number     87572 non-null  object 
     14  Make                    88826 non-null  object 
     15  Model                   88797 non-null  object 
     16  Amateur.Built           88787 non-null  object 
     17  Number.of.Engines       82805 non-null  float64
     18  Engine.Type             81812 non-null  object 
     19  FAR.Description         32023 non-null  object 
     20  Schedule                12582 non-null  object 
     21  Purpose.of.flight       82697 non-null  object 
     22  Air.carrier             16648 non-null  object 
     23  Total.Fatal.Injuries    77488 non-null  float64
     24  Total.Serious.Injuries  76379 non-null  float64
     25  Total.Minor.Injuries    76956 non-null  float64
     26  Total.Uninjured         82977 non-null  float64
     27  Weather.Condition       84397 non-null  object 
     28  Broad.phase.of.flight   61724 non-null  object 
     29  Report.Status           82508 non-null  object 
     30  Publication.Date        75118 non-null  object 
    dtypes: float64(5), object(26)
    memory usage: 21.0+ MB
    

The AviationData dataset has 31 columns and 88889 rows or observations, which have both float and character data types. Next, a quick peek into the summary statisics of the numeric variables present in the dataset.




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Number.of.Engines</th>
      <th>Total.Fatal.Injuries</th>
      <th>Total.Serious.Injuries</th>
      <th>Total.Minor.Injuries</th>
      <th>Total.Uninjured</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>82805.000000</td>
      <td>77488.000000</td>
      <td>76379.000000</td>
      <td>76956.000000</td>
      <td>82977.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.146585</td>
      <td>0.647855</td>
      <td>0.279881</td>
      <td>0.357061</td>
      <td>5.325440</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.446510</td>
      <td>5.485960</td>
      <td>1.544084</td>
      <td>2.235625</td>
      <td>27.913634</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>8.000000</td>
      <td>349.000000</td>
      <td>161.000000</td>
      <td>380.000000</td>
      <td>699.000000</td>
    </tr>
  </tbody>
</table>
</div>



What about the column names? 




    Index(['Event.Id', 'Investigation.Type', 'Accident.Number', 'Event.Date',
           'Location', 'Country', 'Latitude', 'Longitude', 'Airport.Code',
           'Airport.Name', 'Injury.Severity', 'Aircraft.damage',
           'Aircraft.Category', 'Registration.Number', 'Make', 'Model',
           'Amateur.Built', 'Number.of.Engines', 'Engine.Type', 'FAR.Description',
           'Schedule', 'Purpose.of.flight', 'Air.carrier', 'Total.Fatal.Injuries',
           'Total.Serious.Injuries', 'Total.Minor.Injuries', 'Total.Uninjured',
           'Weather.Condition', 'Broad.phase.of.flight', 'Report.Status',
           'Publication.Date'],
          dtype='object')



Since the column names  have a uniform naming system there are no changes needed. Let's proceed to create a copy. 




    Event.Id                      0
    Investigation.Type            0
    Accident.Number               0
    Event.Date                    0
    Location                     52
    Country                     226
    Latitude                  54507
    Longitude                 54516
    Airport.Code              38640
    Airport.Name              36099
    Injury.Severity            1000
    Aircraft.damage            3194
    Aircraft.Category         56602
    Registration.Number        1317
    Make                         63
    Model                        92
    Amateur.Built               102
    Number.of.Engines          6084
    Engine.Type                7077
    FAR.Description           56866
    Schedule                  76307
    Purpose.of.flight          6192
    Air.carrier               72241
    Total.Fatal.Injuries      11401
    Total.Serious.Injuries    12510
    Total.Minor.Injuries      11933
    Total.Uninjured            5912
    Weather.Condition          4492
    Broad.phase.of.flight     27165
    Report.Status              6381
    Publication.Date          13771
    dtype: int64



With the dataset having 88889 observations we have to proceed to remove columns with more than half of the obersavtions missing. Additionally, any column deemed not statistically significant.

    Columns with more than 50% missing values:
    Index(['Latitude', 'Longitude', 'Aircraft.Category', 'FAR.Description',
           'Schedule', 'Air.carrier'],
          dtype='object')
    




    Event.Id                      0
    Investigation.Type            0
    Accident.Number               0
    Event.Date                    0
    Location                     52
    Country                     226
    Airport.Code              38640
    Airport.Name              36099
    Injury.Severity            1000
    Aircraft.damage            3194
    Registration.Number        1317
    Make                         63
    Model                        92
    Amateur.Built               102
    Number.of.Engines          6084
    Engine.Type                7077
    Purpose.of.flight          6192
    Total.Fatal.Injuries      11401
    Total.Serious.Injuries    12510
    Total.Minor.Injuries      11933
    Total.Uninjured            5912
    Weather.Condition          4492
    Broad.phase.of.flight     27165
    Report.Status              6381
    Publication.Date          13771
    dtype: int64



    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 88889 entries, 0 to 88888
    Data columns (total 25 columns):
     #   Column                  Non-Null Count  Dtype  
    ---  ------                  --------------  -----  
     0   Event.Id                88889 non-null  object 
     1   Investigation.Type      88889 non-null  object 
     2   Accident.Number         88889 non-null  object 
     3   Event.Date              88889 non-null  object 
     4   Location                88837 non-null  object 
     5   Country                 88663 non-null  object 
     6   Airport.Code            50249 non-null  object 
     7   Airport.Name            52790 non-null  object 
     8   Injury.Severity         87889 non-null  object 
     9   Aircraft.damage         85695 non-null  object 
     10  Registration.Number     87572 non-null  object 
     11  Make                    88826 non-null  object 
     12  Model                   88797 non-null  object 
     13  Amateur.Built           88787 non-null  object 
     14  Number.of.Engines       82805 non-null  float64
     15  Engine.Type             81812 non-null  object 
     16  Purpose.of.flight       82697 non-null  object 
     17  Total.Fatal.Injuries    77488 non-null  float64
     18  Total.Serious.Injuries  76379 non-null  float64
     19  Total.Minor.Injuries    76956 non-null  float64
     20  Total.Uninjured         82977 non-null  float64
     21  Weather.Condition       84397 non-null  object 
     22  Broad.phase.of.flight   61724 non-null  object 
     23  Report.Status           82508 non-null  object 
     24  Publication.Date        75118 non-null  object 
    dtypes: float64(5), object(20)
    memory usage: 17.0+ MB
    

    Event.Id — 87951 unique values
    ['20001218X45444' '20001218X45447' '20061025X01555' '20001218X45448'
     '20041105X01764' '20170710X52551' '20001218X45446' '20020909X01562'
     '20020909X01561' '20020909X01560']
    ----------------------------------------
    Investigation.Type — 2 unique values
    ['Accident' 'Incident']
    ----------------------------------------
    Accident.Number — 88863 unique values
    ['SEA87LA080' 'LAX94LA336' 'NYC07LA005' 'LAX96LA321' 'CHI79FA064'
     'NYC79AA106' 'CHI81LA106' 'SEA82DA022' 'NYC82DA015' 'MIA82DA029']
    ----------------------------------------
    Event.Date — 14782 unique values
    ['1948-10-24' '1962-07-19' '1974-08-30' '1977-06-19' '1979-08-02'
     '1979-09-17' '1981-08-01' '1982-01-01' '1982-01-02' '1982-01-03']
    ----------------------------------------
    Location — 27759 unique values
    ['MOOSE CREEK, ID' 'BRIDGEPORT, CA' 'Saltville, VA' 'EUREKA, CA'
     'Canton, OH' 'BOSTON, MA' 'COTTON, MN' 'PULLMAN, WA' 'EAST HANOVER, NJ'
     'JACKSONVILLE, FL']
    ----------------------------------------
    Country — 220 unique values
    ['United States' nan 'GULF OF MEXICO' 'Puerto Rico' 'ATLANTIC OCEAN'
     'HIGH ISLAND' 'Bahamas' 'MISSING' 'Pakistan' 'Angola']
    ----------------------------------------
    Airport.Code — 10376 unique values
    [nan 'N58' 'JAX' 'T72' '5G6' 'YIP' '49G' 'PDK' 'VNY' 'SOP']
    ----------------------------------------
    Airport.Name — 24872 unique values
    [nan 'BLACKBURN AG STRIP' 'HANOVER' 'JACKSONVILLE INTL' 'TUSKEGEE'
     'HEARNE MUNICIPAL' 'FIELD RANCH' 'CHERRY SPRINGS' 'WILLOW RUN'
     'TINKERBELL']
    ----------------------------------------
    Injury.Severity — 110 unique values
    ['Fatal(2)' 'Fatal(4)' 'Fatal(3)' 'Fatal(1)' 'Non-Fatal' 'Incident'
     'Fatal(8)' 'Fatal(78)' 'Fatal(7)' 'Fatal(6)']
    ----------------------------------------
    Aircraft.damage — 5 unique values
    ['Destroyed' 'Substantial' 'Minor' nan 'Unknown']
    ----------------------------------------
    Registration.Number — 79106 unique values
    ['NC6404' 'N5069P' 'N5142R' 'N1168J' 'N15NY' 'CF-TLU' 'N4988E' 'N2482N'
     'N7967Q' 'N3906K']
    ----------------------------------------
    Make — 8238 unique values
    ['Stinson' 'Piper' 'Cessna' 'Rockwell' 'Mcdonnell Douglas'
     'North American' 'Beech' 'Bellanca' 'Navion' 'Enstrom']
    ----------------------------------------
    Model — 12319 unique values
    ['108-3' 'PA24-180' '172M' '112' '501' 'DC9' '180' '140' '401B'
     'NAVION L-17B']
    ----------------------------------------
    Amateur.Built — 3 unique values
    ['No' 'Yes' nan]
    ----------------------------------------
    Number.of.Engines — 8 unique values
    [ 1. nan  2.  0.  3.  4.  8.  6.]
    ----------------------------------------
    Engine.Type — 14 unique values
    ['Reciprocating' nan 'Turbo Fan' 'Turbo Shaft' 'Unknown' 'Turbo Prop'
     'Turbo Jet' 'None' 'Electric' 'Hybrid Rocket']
    ----------------------------------------
    Purpose.of.flight — 27 unique values
    ['Personal' nan 'Business' 'Instructional' 'Unknown' 'Ferry'
     'Executive/corporate' 'Aerial Observation' 'Aerial Application'
     'Public Aircraft']
    ----------------------------------------
    Total.Fatal.Injuries — 126 unique values
    [ 2.  4.  3.  1. nan  0.  8. 78.  7.  6.]
    ----------------------------------------
    Total.Serious.Injuries — 51 unique values
    [ 0. nan  2.  1.  6.  4.  5. 10.  3.  8.]
    ----------------------------------------
    Total.Minor.Injuries — 58 unique values
    [ 0. nan  1.  3.  2.  4. 24.  6.  5. 25.]
    ----------------------------------------
    Total.Uninjured — 380 unique values
    [  0.  nan  44.   2.   1.   3.   6.   4. 149.  12.]
    ----------------------------------------
    Weather.Condition — 5 unique values
    ['UNK' 'IMC' 'VMC' nan 'Unk']
    ----------------------------------------
    Broad.phase.of.flight — 13 unique values
    ['Cruise' 'Unknown' 'Approach' 'Climb' 'Takeoff' 'Landing' 'Taxi'
     'Descent' 'Maneuvering' 'Standing']
    ----------------------------------------
    Report.Status — 17076 unique values
    ['Probable Cause' 'Factual' 'Foreign' 'Preliminary'
     "The departing pilot's inadequate visual lookout."
     "The pilot's failure to maintain directional control.  A contributing factor was the prevailing crosswind."
     "the student pilot's premature flare resulting in the loss of aircraft control."
     "The pilot's inadequate compensation for wind conditions.  A factor in the accident was the wind gust."
     "The line technician's failure to remain clear of the propeller.  A factor was the night lighting conditions."
     nan]
    ----------------------------------------
    Publication.Date — 2925 unique values
    [nan '19-09-1996' '26-02-2007' '12-09-2000' '16-04-1980' '19-09-2017'
     '06-11-2001' '01-01-1982' '02-01-1983' '03-01-1983']
    ----------------------------------------
    

The above steps check the unique values in each of the remaining columns. Given the large size of this dataset, it is safe to assume that columns whose unique values caount is  close to or same as the total observations can be considered as not relevant for any analysis. This is because they do bring much value because they are identifiers. These columns are Accident.Number, and Registration.Number. Additionally, since we are a well known company we have no interests with amateur built aircraft since they pose too much risk. The focus is on acquisition of tested and approved planes, hence no research and development projects

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 88889 entries, 0 to 88888
    Columns: 22 entries, Event.Id to Publication.Date
    dtypes: float64(5), object(17)
    memory usage: 14.9+ MB
    

Now let's deal with the missing values in the object dtype columns by replacing the missing values with "unknown'. This was preferred instead of mode since the missing values are many and cause to much skeweness.  

For the numeric dtypes we can replace the unkowns with mean




    Event.Id                  0
    Investigation.Type        0
    Event.Date                0
    Location                  0
    Country                   0
    Airport.Code              0
    Airport.Name              0
    Injury.Severity           0
    Aircraft.damage           0
    Make                      0
    Model                     0
    Number.of.Engines         0
    Engine.Type               0
    Purpose.of.flight         0
    Total.Fatal.Injuries      0
    Total.Serious.Injuries    0
    Total.Minor.Injuries      0
    Total.Uninjured           0
    Weather.Condition         0
    Broad.phase.of.flight     0
    Report.Status             0
    Publication.Date          0
    dtype: int64



Now, let's check drop and all duplicates




    28



    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 88861 entries, 0 to 88888
    Data columns (total 22 columns):
     #   Column                  Non-Null Count  Dtype  
    ---  ------                  --------------  -----  
     0   Event.Id                88861 non-null  object 
     1   Investigation.Type      88861 non-null  object 
     2   Event.Date              88861 non-null  object 
     3   Location                88861 non-null  object 
     4   Country                 88861 non-null  object 
     5   Airport.Code            88861 non-null  object 
     6   Airport.Name            88861 non-null  object 
     7   Injury.Severity         88861 non-null  object 
     8   Aircraft.damage         88861 non-null  object 
     9   Make                    88861 non-null  object 
     10  Model                   88861 non-null  object 
     11  Number.of.Engines       88861 non-null  float64
     12  Engine.Type             88861 non-null  object 
     13  Purpose.of.flight       88861 non-null  object 
     14  Total.Fatal.Injuries    88861 non-null  float64
     15  Total.Serious.Injuries  88861 non-null  float64
     16  Total.Minor.Injuries    88861 non-null  float64
     17  Total.Uninjured         88861 non-null  float64
     18  Weather.Condition       88861 non-null  object 
     19  Broad.phase.of.flight   88861 non-null  object 
     20  Report.Status           88861 non-null  object 
     21  Publication.Date        88861 non-null  object 
    dtypes: float64(5), object(17)
    memory usage: 15.6+ MB
    




    array(['Fatal', 'Non-Fatal', 'Incident', 'unknown'], dtype=object)



# Exploratort Data Analysis
## Univariate Analysis

    Top 10 Locations:
    ANCHORAGE, AK      434
    MIAMI, FL          200
    ALBUQUERQUE, NM    196
    HOUSTON, TX        192
    CHICAGO, IL        184
    FAIRBANKS, AK      174
    TUCSON, AZ         142
    PHOENIX, AZ        132
    ORLANDO, FL        132
    ENGLEWOOD, CO      131
    
    Top 10 Countries:
    United States     82223
    Brazil              374
    Canada              359
    Mexico              358
    United Kingdom      344
    Australia           300
    France              236
    Unknown             229
    Spain               226
    Bahamas             216
    
    

United States has by far the largest observations in dataset. Given the rarity of accidents in other countries we have to focus the investigation on the United States.
Reason: bias or lack of adequate data for the other countries.Since research is based on quality data, it wise to invest in a market where most, if not all, of the variables are known. 

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 62 entries, 0 to 61
    Data columns (total 2 columns):
     #   Column        Non-Null Count  Dtype 
    ---  ------        --------------  ----- 
     0   US_State      62 non-null     object
     1   Abbreviation  62 non-null     object
    dtypes: object(2)
    memory usage: 1.1+ KB
    

    Top 10 Makes:
    Cessna     21569
    Piper      11661
    CESSNA      4280
    Beech       4167
    PIPER       2507
    Bell        1881
    Boeing      1157
    Grumman     1075
    Mooney      1074
    BEECH        892
    
    Top 10 Models:
    152          2321
    172          1636
    172N         1136
    PA-28-140     910
    150           790
    172M          773
    172P          679
    180           617
    182           589
    PA-18-150     578
    
    

Before proceeding with further exploration, we will have to ensure all values in the "Make" column are uniformly formatted to remove any redudancy in group categoring

    Top 10 Makes:
    Cessna      25849
    Piper       14168
    Beech        5059
    Bell         2284
    Boeing       1480
    Mooney       1293
    Grumman      1141
    Bellanca     1040
    Robinson      917
    Hughes        874
    
    


    
![png](README_files/README_40_0.png)
    


The data reveals that Cessna is by far the most frequently involved aircraft make in reported aviation accidents or incidents, with over 25,000 occurrences, followed by Piper and Beech. These makes are commonly used in general aviation, which may contribute to their higher representation. Notably, Boeing appears fourth, reflecting its presence in commercial aviation despite a lower volume of flights compared to smaller aircraft. In terms of locations, cities like Anchorage, AK and Miami, FL top the list, likely due to their busy regional traffic and challenging flying conditions. Albuquerque, Houston, and Chicago also rank high, suggesting significant aviation activity or concentrated reporting in those areas. The United States overwhelmingly leads in accident reports, which is expected due to the country's vast air traffic volume and comprehensive reporting system. Other countries such as Brazil, Canada, and Mexico follow distantly, with accident counts in the hundreds, emphasizing the U.S.-centric nature of this dataset.

       Event.Year  Accident_Count
    0        1948               1
    1        1962               1
    2        1974               1
    3        1977               1
    4        1979               2
    

From the time series plot below, a huge spike in aviation accident around 1980. The 80's era ushered a boom in air travel after the 1978 Airline Deregulation Act. A rise of commercial and low cost carries, thanks to government deregulization, can be attributed to this spike although later interventions was able to control this crisis. A five year forecast will be added using tableau.


    
![png](README_files/README_44_0.png)
    


### Categorical Columns Disribution


    
![png](README_files/README_46_0.png)
    



    
![png](README_files/README_46_1.png)
    



    
![png](README_files/README_46_2.png)
    



    
![png](README_files/README_46_3.png)
    


1.For the engine type, the reciprocating engine has the highest frequency of incidents while the hybrid pocket has the lowest.  
2. Most accident severity are non fatal, more evidence why air travels is the safest mode of transport.  
3. Should a plane fall, damage is most likely to be substantial. Hence, recovering and fixing these planes is not viable which means  
4. Shockingly, most accident happen in visual meteorological conditions which should be easier for pilots meaning that weather does not pose a huge threat.  
Also, we can infer that the type of aircraft is the key variable.

### Numerical Columns Distribution

    Data shape after removing outliers: (76015, 22)
    

Movin on, from the plot grid below, there are no distribtions in frequency of the various types of injuries. It indicates that it is safe to also invest in any aircraft without considering the number of paasenger. Moreover, the number of engines indicate that airplanes with one to two engines have a higher probability of accident/incident with three and above engines having more the lowest risk.


    
![png](README_files/README_51_0.png)
    



    
![png](README_files/README_51_1.png)
    



    
![png](README_files/README_51_2.png)
    



    
![png](README_files/README_51_3.png)
    



    
![png](README_files/README_51_4.png)
    



    
![png](README_files/README_52_0.png)
    



    
![png](README_files/README_52_1.png)
    



    
![png](README_files/README_52_2.png)
    



    
![png](README_files/README_52_3.png)
    



    
![png](README_files/README_52_4.png)
    



    
![png](README_files/README_53_0.png)
    



    
![png](README_files/README_53_1.png)
    



    
![png](README_files/README_53_2.png)
    



    
![png](README_files/README_53_3.png)
    



    
![png](README_files/README_53_4.png)
    


## Bivariate  Analysis


    
![png](README_files/README_55_0.png)
    


Boeing has the highest fatal injuries while Grumman has the lowest. This is an indicator that grumman, with Cessna as a close second, has the highes survivability. 


    
![png](README_files/README_57_0.png)
    



    
![png](README_files/README_59_0.png)
    


Surprisingly, Boeing shows the highest rate of uninjured meaning fatal injuries could be do to higher case of system malfunctions and not necessarily poor build strength


    
![png](README_files/README_61_0.png)
    


Clear, indication in VMC weather conditions there is a high frequency of accidents most of the airplane makes. However Cessna and Piper seem to be the highest indicating build weakness or endurance during violent weather conditions 


    
![png](README_files/README_63_0.png)
    


The above heat map shows that there are no strong corrrelations relationships between the numeric variables. Most of the correlations coefficients are beow 0.01. However, the most statisticaly signficant obesrvation would be the relationship between the number of engines and the total uninjured is 0.35. Though small we can conclude that higher number of engines increase the total uninjured surviors. Hence we will not analyse the numerical varaibles any further.


    
![png](README_files/README_65_0.png)
    


The above plot further consolidates that higher number of engines reduce casualties. 


    
![png](README_files/README_67_0.png)
    



    
![png](README_files/README_67_1.png)
    



    
![png](README_files/README_67_2.png)
    



    
![png](README_files/README_67_3.png)
    



    
![png](README_files/README_67_4.png)
    


Since we have seen that loss of life and aeroplane damage is bound to be substantial in the clearest of weather and any accident, we should focus on aircraft specifics and accident frequency.  
1.Cessna and piper has the highest accident risk.  
2. The 152 models have the highest accident rate.  
3.Most accidents have no indication at what phase do planes crush but landing and takeoff are the first and second runner-ups respectfully.  
4. Most accidents are non fatal.  
5. Aircrafts used for personal and instructional purposes have the highest accident rate

All these aircraft attriutes should be avoided, bought with precaution or focus on new models with new advancements for optimal flight control ad 


    
![png](README_files/README_70_0.png)
    



    
![png](README_files/README_70_1.png)
    



    
![png](README_files/README_70_2.png)
    



    
![png](README_files/README_70_3.png)
    

