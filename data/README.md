# Data Directory

## Valencia Airbnb Dataset

This project uses public Airbnb listing data for Valencia, Spain from [Inside Airbnb](http://insideairbnb.com/).

### Data Acquisition

The notebook automatically downloads the dataset when run. The data is sourced from:
- **Source**: Inside Airbnb (http://insideairbnb.com/)
- **Location**: Valencia, Spain
- **Date**: September 2024
- **URL**: http://data.insideairbnb.com/spain/valencia/valencia/2024-09-18/data/listings.csv.gz

### Dataset Description

The dataset contains detailed information about Airbnb listings in Valencia, including:

- **Property Characteristics**: Type, size, number of bedrooms, beds, bathrooms
- **Location**: Latitude, longitude, neighborhood
- **Amenities**: List of amenities provided
- **Pricing**: Nightly price, cleaning fees, security deposit
- **Availability**: Calendar availability, minimum/maximum nights
- **Reviews**: Number of reviews, review scores across multiple categories
- **Host Information**: Response time, acceptance rate, superhost status

### Data Files

After running the notebook, the following files will be present:

```
data/
├── valencia_listings.csv.gz    # Main listings dataset (auto-downloaded)
└── README.md                   # This file
```

### Data Privacy

This dataset is publicly available and aggregated. It does not contain personally identifiable information about hosts or guests. All data is used in compliance with Inside Airbnb's data usage policies.

### License

The data is made available under a [Creative Commons CC0 1.0 Universal License](https://creativecommons.org/publicdomain/zero/1.0/).

For more information about the data, visit [Inside Airbnb - Valencia](http://insideairbnb.com/valencia/).
