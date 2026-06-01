# Airbnb Data Cleaning & EDA Project
<img width="500" alt="image" src="https://github.com/user-attachments/assets/4a48bfc3-417c-48bb-988e-a5f00faa6a18" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/34685a05-8447-47d7-84c4-c5e7951cb341" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/6334f0f3-3cc3-4aee-bde5-28099b86450a" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/a63381b4-8c2c-4c0b-b4b1-d5f43f0c02e7" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/afb71974-7a22-4453-8ff3-ecb9de182aef" />

# Here's what this project is about
I took a messy Airbnb dataset from Kaggle with 74,111 listings across 6 US cities and tried to clean it up and find some interesting patterns in the data.

The Dataset
Where I got it: [Kaggle — Airbnb Data](https://www.kaggle.com/datasets/sankalp102/air-bnb)
Size: 74,111 listings and 29 columns
Cities: San Francisco, NYC, LA, Boston, Washington DC, Chicago

# Airbnb Data Cleaning & EDA Project

![Python](https://img.shields.io/badge/Python-3.x-blue) 
![Pandas](https://img.shields.io/badge/Pandas-EDA-green) 
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Dataset](https://img.shields.io/badge/Dataset-74%2C111%20listings-lightgrey)

---

# What I used

| Tool | What I used it for |
|------|---------|
| Python | Main language |
| Pandas | Cleaning and analyzing the data |
| NumPy | Math stuff (reversing the log price) |
| Matplotlib | Making the charts |
| Jupyter Notebook | Writing and running everything |

---

# How I cleaned the data

Honestly the data was messier than I expected. Here's what I had to fix:

| Problem I found | What I did about it |
|-------|-------------|
| `id` and `thumbnail_url` columns | Dropped them — totally useless for analysis |
| 1 listing with $0 price | Removed it — clearly an error |
| Missing bathrooms, bedrooms, beds | Filled them with the median value |
| 188 rows with missing host info | Dropped them — only 0.25% of the data so no big deal |
| Prices were in log format | Converted to real dollars using `np.exp()` |

I started with 74,111 rows and ended with 74,110 — barely lost anything!

---

# What I found

# 1. Apartments are basically everywhere
Two thirds of all listings 66% are apartments. I kind of expected this but not by that much. Houses are second at 22% and everything else is pretty rare.

### 2. Want a whole place? It'll cost you
| Room Type | Average Price per Night |
|-----------|--------------|
| Entire home/apt | $218.75 |
| Private room | $88.49 |
| Shared room | $63.71 |

Renting an entire home costs almost 2.5x more than a private room. Makes sense but the gap is bigger than I thought!

### 3. SF is more expensive than NYC — I did not expect this
| City | Average per Night |
|------|--------------------|
| San Francisco | $227.37 |
| Washington DC | $217.93 |
| Boston | $165.63 |
| Los Angeles | $155.39 |
| New York City | $143.03 |
| Chicago | $132.48 |

I honestly thought NYC would be #1 but San Francisco beats it by $84/night. Chicago is the most affordable by far

# 4. More bedrooms = way more expensive (obvious but the numbers are wild)
- Studio: $144/night
- 2 bedrooms: $234/night
- 4 bedrooms: $499/night
- 7 bedrooms: $871/night

A 7-bedroom listing costs 6x more than a studio. The trend is super consistent too — every bedroom you add bumps the price up significantly

# 5. Super strict cancellation = luxury listing
The super strict listings average $929/night which makes sense, those are probably fancy properties that can afford to be picky. Among the normal policies (strict, moderate, flexible) the price difference is actually pretty small which surprised me

# 6. Being a verified host barely matters for price
Unverified hosts: $163/night vs Verified hosts: $159/night. I thought verified hosts would charge more but it's basically the same

# Charts

I made a chart for each finding using Matplotlib.

# What I learned doing this project

- Always make a copy of your dataframe before cleaning (`df.copy()`) learned this the hard way!
- Use median instead of mean when filling missing values because outliers mess up the average
- `log_price` is a thing — prices get log-transformed to handle huge ranges, and `np.exp()` reverses it
- `groupby()` is incredibly useful for finding patterns across categories
- Real data is messy and that's totally normal

Dataset from Kaggle. Feedback welcome 🙂*


