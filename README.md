# ECE-2112-PA-3
Jhan Gabriel V. Caragay | 2ECE-D

This programming assignment uses **Python Data Analysis** (Pandas) and consists of three problems that demonstrate different techniques for loading, indexing, and extracting data from a CSV dataset.

We first import the Python Data Analysis library ```Pandas```:

```python
import pandas as pd
```
> We rename it as pd to make it shorter and more efficient.

This should be done first because the remaining code in all three problems relies on functions and operations provided by the ```Pandas``` library.

We first load the **CSV file** into a **DataFrame** named ```cars```:

```python
cars = pd.read_csv('cars.csv')
```
> This will then be used in the entirety of the programming assignment.

Calling the ```DataFrame``` will show the following data:

| Model | mpg | cyl | disp | hp | drat | wt | qsec | vs | am | gear | carb |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Mazda RX4 | 21.0 | 6 | 160.0 | 110 | 3.90 | 2.620 | 16.46 | 0 | 1 | 4 | 4 |
| Mazda RX4 Wag | 21.0 | 6 | 160.0 | 110 | 3.90 | 2.875 | 17.02 | 0 | 1 | 4 | 4 |
| Datsun 710 | 22.8 | 4 | 108.0 | 93 | 3.85 | 2.320 | 18.61 | 1 | 1 | 4 | 1 |
| Hornet 4 Drive | 21.4 | 6 | 258.0 | 110 | 3.08 | 3.215 | 19.44 | 1 | 0 | 3 | 1 |
| Hornet Sportabout | 18.7 | 8 | 360.0 | 175 | 3.15 | 3.440 | 17.02 | 0 | 0 | 3 | 2 |
| Valiant | 18.1 | 6 | 225.0 | 105 | 2.76 | 3.460 | 20.22 | 1 | 0 | 3 | 1 |
| Duster 360 | 14.3 | 8 | 360.0 | 245 | 3.21 | 3.570 | 15.84 | 0 | 0 | 3 | 4 |
| Merc 240D | 24.4 | 4 | 146.7 | 62 | 3.69 | 3.190 | 20.00 | 1 | 0 | 4 | 2 |
| Merc 230 | 22.8 | 4 | 140.8 | 95 | 3.92 | 3.150 | 22.90 | 1 | 0 | 4 | 2 |
| Merc 280 | 19.2 | 6 | 167.6 | 123 | 3.92 | 3.440 | 18.30 | 1 | 0 | 4 | 4 |
| Merc 280C | 17.8 | 6 | 167.6 | 123 | 3.92 | 3.440 | 18.90 | 1 | 0 | 4 | 4 |
| Merc 450SE | 16.4 | 8 | 275.8 | 180 | 3.07 | 4.070 | 17.40 | 0 | 0 | 3 | 3 |
| Merc 450SL | 17.3 | 8 | 275.8 | 180 | 3.07 | 3.730 | 17.60 | 0 | 0 | 3 | 3 |
| Merc 450SLC | 15.2 | 8 | 275.8 | 180 | 3.07 | 3.780 | 18.00 | 0 | 0 | 3 | 3 |
| Cadillac Fleetwood | 10.4 | 8 | 472.0 | 205 | 2.93 | 5.250 | 17.98 | 0 | 0 | 3 | 4 |
| Lincoln Continental | 10.4 | 8 | 460.0 | 215 | 3.00 | 5.424 | 17.82 | 0 | 0 | 3 | 4 |
| Chrysler Imperial | 14.7 | 8 | 440.0 | 230 | 3.23 | 5.345 | 17.42 | 0 | 0 | 3 | 4 |
| Fiat 128 | 32.4 | 4 | 78.7 | 66 | 4.08 | 2.200 | 19.47 | 1 | 1 | 4 | 1 |
| Honda Civic | 30.4 | 4 | 75.7 | 52 | 4.93 | 1.615 | 18.52 | 1 | 1 | 4 | 2 |
| Toyota Corolla | 33.9 | 4 | 71.1 | 65 | 4.22 | 1.835 | 19.90 | 1 | 1 | 4 | 1 |
| Toyota Corona | 21.5 | 4 | 120.1 | 97 | 3.70 | 2.465 | 20.01 | 1 | 0 | 3 | 1 |
| Dodge Challenger | 15.5 | 8 | 318.0 | 150 | 2.76 | 3.520 | 16.87 | 0 | 0 | 3 | 2 |
| AMC Javelin | 15.2 | 8 | 304.0 | 150 | 3.15 | 3.435 | 17.30 | 0 | 0 | 3 | 2 |
| Camaro Z28 | 13.3 | 8 | 350.0 | 245 | 3.73 | 3.840 | 15.41 | 0 | 0 | 3 | 4 |
| Pontiac Firebird | 19.2 | 8 | 400.0 | 175 | 3.08 | 3.845 | 17.05 | 0 | 0 | 3 | 2 |
| Fiat X1-9 | 27.3 | 4 | 79.0 | 66 | 4.08 | 1.935 | 18.90 | 1 | 1 | 4 | 1 |
| Porsche 914-2 | 26.0 | 4 | 120.3 | 91 | 4.43 | 2.140 | 16.70 | 0 | 1 | 5 | 2 |
| Lotus Europa | 30.4 | 4 | 95.1 | 113 | 3.77 | 1.513 | 16.90 | 1 | 1 | 5 | 2 |
| Ford Pantera L | 15.8 | 8 | 351.0 | 264 | 4.22 | 3.170 | 14.50 | 0 | 1 | 5 | 4 |
| Ferrari Dino | 19.7 | 6 | 145.0 | 175 | 3.62 | 2.770 | 15.50 | 0 | 1 | 5 | 6 |
| Maserati Bora | 15.0 | 8 | 301.0 | 335 | 3.54 | 3.570 | 14.60 | 0 | 1 | 5 | 8 |
| Volvo 142E | 21.4 | 4 | 121.0 | 109 | 4.11 | 2.780 | 18.60 | 1 | 1 | 4 | 2 |

> Again, this will then be used in the entirety of the programming assignment.

# A. POSITIONAL AND LABEL-BASED SLICING

### **OBJECTIVE**

The first problem requires displaying the **shape** and **complete column names** of the `cars` DataFrame, then using **positional slicing** with `iloc`
to extract rows 6 through 10 of the dataset. From those selected rows, the required columns **Model, mpg, cyl, hp, and gear** are selected using their
**column labels**, in the specified order.

### **DISCUSSION**

The shape of the ```cars``` **DataFrame** was obtained using the code:
```python
cars.shape
```
The code outputs:
```python
(32, 12)
```
> The cars DataFrame contains 32 rows and 12 columns.

We then get the complete list of column names of cars using the code:

```python
cars.columns
```
The code outputs:
```python
['Model',
 'mpg',
 'cyl',
 'disp',
 'hp',
 'drat',
 'wt',
 'qsec',
 'vs',
 'am',
 'gear',
 'carb']
```
> This prints out the names of all 12 columns.

Next, using positional slicing, we create ```cars_6_to_10``` containing rows 6 through 10 of the dataset using the code:

```python
cars_6_to_10 = cars.iloc[5:10] 
```

The code outputs:

| Model | mpg | cyl | disp | hp | drat | wt | qsec | vs | am | gear | carb |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Valiant | 18.1 | 6 | 225.0 | 105 | 2.76 | 3.46 | 20.22 | 1 | 0 | 3 | 1 |
| Duster 360 | 14.3 | 8 | 360.0 | 245 | 3.21 | 3.57 | 15.84 | 0 | 0 | 3 | 4 |
| Merc 240D | 24.4 | 4 | 146.7 | 62 | 3.69 | 3.19 | 20.00 | 1 | 0 | 4 | 2 |
| Merc 230 | 22.8 | 4 | 140.8 | 95 | 3.92 | 3.15 | 22.90 | 1 | 0 | 4 | 2 |
| Merc 280 | 19.2 | 6 | 167.6 | 123 | 3.92 | 3.44 | 18.30 | 1 | 0 | 4 | 4 |

> This selects rows at positions **5** through **9**, which correspond to rows **6** through **10** in the dataset as Python indexing starts at ```0```.

### **OVERALL STRUCTURE**




# B. MODEL LOOKUP

### **OBJECTIVE**

The second problem requires using Boolean indexing on the ```Model``` **column** to locate specific car models without relying on their row numbers.
The complete row for **Toyota Corolla** is stored in ```toyota```, while **Model**, **mpg**, **hp**, and **wt** for **Pontiac Firebird** are selected and stored in ```pontiac```.

### **DISCUSSION**

### **OVERALL STRUCTURE**




# C. MULTI-MODEL SUBSETTING

### **OBJECTIVE**

The third problem requires creating a new DataFrame named ```selected_cars``` by filtering the Model column for three specific car models: **Datsun 710**, **Lotus Europa**, and **Ferrari Dino**. 
Only the columns **Model**, **mpg**, **cyl**, **hp**, and **gear** are retained. The resulting ```DataFrame``` is displayed along with its shape.

### **DISCUSSION**

### **OVERALL STRUCTURE**




## **HISTORY**

**September 6, 2026** - Finalized the README.md file.

**September 5, 2026** - Submitted the required .ipynb and .npy files.

**September 5, 2026** - Started the Readme file.
