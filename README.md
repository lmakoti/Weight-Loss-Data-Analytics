<p align="center"><img src="Fibit Resources\Fitbit_logo.png" alt="Fitbit_logo" style="height:50px"/></p>

<p align="center">
 <a href="#overview">Overview</a> •
 <a href="#Rationale and definition (SDG9c)">Rationale and Definition</a> •
 <a href="#Resource">Resources</a> •
 <a href="#Solution Architecture">Solution Architecture</a> •
 <a href="#networking">Networking</a> •
 <a href="#license">License</a>
</p>




## Overview

> My health has become a key priority in my life, and weight loss is at the top of my to-do list. The reason that prompted this realisation was the benefits I received from doing informal/untracked walks in the last quarter of 2021 and beginning of 2022, most of my walks were aimed at touring parts of London and appreciate this new place I now call home.
>
> I have decided to formalise my tracking and also modify my walking routines to include rucking which is a low intensity interval training workout that involves walking or hiking with a weighted rucksack (bag-pack) for a set distance.



## Rationale and definition

The theme described in the overview inspired me to do an analysis of my personal health and fitness and evaluate the progress 🤞😂 that I have made. The data is tracked from the **15 March 2022** (when I got my [Fitbit Charge 5](https://www.fitbit.com/global/uk/products/trackers/charge5?gclid=CjwKCAjwj42UBhAAEiwACIhADmoVq37g5FDdnkQb_A3GpXnVwAxkAp7_sVM9_h_jyt-eVn1rEH9C0RoC__gQAvD_BwE&gclsrc=aw.ds)) to the **03 August 2022**.



## Resources

The data comes from two primary sources: my Charge 5 and  [Rephno Smart Body Fat Scale](https://uk.renpho.com/products/smart-body-fat-scale-basic?variant=38203353891015)

1. **Fitbit Data**: Daily Distance from Activities

   <p align="center"><img src="Fibit Resources\charge5-black-device-3qtr.png" alt="charge5-black-device-3qtr" style="height:350px" /></p>

2. **Rephno Data**: Daily Weight Measurement (Incl. BMI)

   <p align="center"><img src="https://m.media-amazon.com/images/I/61JlA-7e7aL._AC_SL1500_.jpg" alt="RENPHO Body Fat Scale Bluetooth, Digital Body Weight Bathroom Scales  Weighing Scale Smart BMI Scales, Body Composition Monitors with Smartphone  App, Black : Amazon.co.uk: Health & Personal Care" style="height:350px" /></p>

3. **Basin18 North Face Rucksack**: Weight Carrier

   <p align="center"><img src="Fibit Resources\03_basin18_rucksack.png" alt="basin18_rucksack" style="height:550px" /></p>

## Solution Architecture

1. Link the Rephno scale to the Fitbit app, every measurement recorded in the app gets auto send to Fitbit

   <p align="center"><img src="Fibit Resources\rephno-fitbit.jpeg" alt="rephno-fitbit" style="height:350px" /></p>

2. The data is collected/tracked in the Fitbit app

   <p align="center"><img src="Fibit Resources\fitbit_weight.jpeg" alt="fitbit_weight" style="height:350px" /></p>

3. Export the data from the Fitbit web-based dashboard as a CSV (**NB: **Data can only be exported in batches of 31 days, this is a bit inconvenient but PowerBI handles merging multiple files with relative ease)

   <p align="center"><img src="Fibit Resources\image-20220517121903674.png" alt="image-20220517121903674" style="height:350px" /></p>

4. Export the CSV files into a single working directory which will be used as a `folder data source` in PowerBI

  <p align="center"><img src="Fibit Resources\image-20220517122106574.png" alt="image-20220517122106574" style="height:350px" /></p>

5. The Fitbit data comes in well formatted and easily usable, only a few transformation steps were performed on the data
   - Filter to `Activity` data only i.e. exclude information on `body, foods and sleep` as highlighted in step 3 **NB**: the data can be filtered at export (Step 3)
   - Conversion to explicit data types (Decimal for numerical values)
   - Created a date column to conform to the set system date format `mm-dd-yyyy`



6. Create Report to represent the tracker metrics under focus (Initial Design)
<p align="center"><img src="Fibit Resources\image-20220517122804588.png" alt="image-20220517122106574" style="zoom:25%" /></p>

## License

This license lets others distribute, remix, adapt, and build upon your work, even commercially, as long as they credit you for the original creation. This is the most accommodating of licenses offered. Recommended for maximum dissemination and use of licensed materials. (https://creativecommons.org/licenses/)
