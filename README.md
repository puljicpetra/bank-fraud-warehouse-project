# 🏦 Bank Fraud Warehouse Project

## 🌐 Language / Jezik

- [Hrvatski](#hrvatski)
- [English](#english)

---

# Hrvatski

## Projekt skladišta podataka za analizu bankovnih prijevara

Ovaj repozitorij sadrži projekt iz kolegija **Skladišta i rudarenje podataka**.

Projekt se temelji na skupu podataka **Bank Transaction Fraud Detection** i obuhvaća eksplorativnu analizu podataka, izradu relacijskog modela, izradu dimenzijskog modela, ETL proces, punjenje skladišta podataka te OLAP analizu i vizualizaciju u Power BI alatu.

Cilj projekta je pripremiti, organizirati i transformirati podatke o bankovnim transakcijama u strukturu skladišta podataka kako bi se nad njima mogla provesti analiza prijevara i drugih poslovno korisnih pokazatelja.

---

## 📌 Opis projekta

Projekt je izrađen kroz pet checkpointova.

### Checkpoint 1: Eksplorativna analiza podataka

U prvom dijelu projekta provedena je osnovna analiza izvornog CSV skupa podataka pomoću Pythona i pandas biblioteke.

Analiza uključuje:

- učitavanje CSV datoteke u DataFrame
- pregled prvih redaka podataka
- provjeru veličine skupa podataka
- ispis naziva stupaca
- provjeru nedostajućih vrijednosti
- pregled jedinstvenih vrijednosti
- ispis tipova podataka
- analizu frekvencija vrijednosti po stupcima

Na temelju analize zaključeno je da je skup podataka dovoljno velik, da sadrži raznolike podatke, vremensku dimenziju te kvantitativne i kvalitativne podatke.

---

### Checkpoint 2: Dizajn i implementacija relacijskog modela

U drugom dijelu projekta izrađen je relacijski model baze podataka.

Ovaj dio uključuje:

- definiranje entiteta
- definiranje atributa
- definiranje veza između entiteta
- određivanje kardinalnosti veza
- izradu ER dijagrama kao konceptualnog modela
- izradu EER dijagrama kao logičkog modela
- implementaciju modela u MySQL-u
- učitavanje podataka u relacijsku bazu podataka

Relacijska baza korištena je kao jedan od izvora podataka u kasnijem ETL procesu.

---

### Checkpoint 3: Kreiranje dimenzijskog modela

U trećem dijelu projekta izrađen je dimenzijski model podataka.

Dimenzijski model temelji se na **star shemi**, u kojoj se u središtu nalazi tablica činjenica, a oko nje dimenzijske tablice.

Središnja tablica činjenica je:

- `fact_bank_transaction`

Glavne dimenzijske tablice su:

- `dim_customer`
- `dim_account`
- `dim_merchant`
- `dim_device`
- `dim_transaction_type`
- `dim_transaction_location`
- `dim_currency`
- `dim_date`

Glavne mjere u tablici činjenica su:

- iznos transakcije
- stanje računa
- oznaka prijevare
- broj transakcija

U modelu su definirane i hijerarhije, kao što su hijerarhija lokacije i hijerarhija trgovca. Uključene su i napredne izvedbe dimenzijskog modela, poput sporo mijenjajućih dimenzija i degenerirane dimenzije.

---

### Checkpoint 4: ETL proces i punjenje skladišta podataka

U četvrtom dijelu projekta proveden je ETL proces.

ETL proces uključuje tri glavne faze:

- **Extract** – dohvaćanje podataka iz izvora
- **Transform** – čišćenje, usklađivanje i priprema podataka
- **Load** – učitavanje podataka u skladište podataka

Podaci su učitani iz dva izvora:

- MySQL relacijske baze podataka
- CSV datoteke

U projektu je korištena podjela podataka na dva izvora:

- 80% podataka učitano je u MySQL bazu
- 20% podataka ostalo je u CSV datoteci
- oba izvora su zatim integrirana u završno skladište podataka

Nakon punjenja skladišta provedene su provjere ispravnosti učitanih podataka, uključujući provjeru broja redaka, provjeru povezanosti tablice činjenica s dimenzijama i usporedbu podataka između izvora i skladišta.

---

### Checkpoint 5: OLAP analiza i vizualizacija

U petom dijelu projekta korišten je **Power BI** kao OLAP alat.

U Power BI-ju izrađen je podatkovni model povezan s dimenzijskim skladištem podataka. Zatim su kreirani dashboardi, grafovi, tablice i KPI kartice za analizu bankovnih transakcija i prijevara.

Analiza uključuje:

- ukupan iznos transakcija
- prosječan iznos transakcije
- ukupan broj transakcija
- broj prijevarnih transakcija
- stopu prijevara
- analizu prema tipu transakcije
- analizu prema tipu uređaja
- analizu prema kategoriji trgovca
- analizu prema lokaciji
- analizu kroz hijerarhije

Provedene su i OLAP operacije kao što su:

- slice
- dice
- drill-down
- roll-up
- pivot

---

## 📊 Skup podataka

Korišten je skup podataka **Bank Transaction Fraud Detection**.

Skup podataka sadrži podatke o bankovnim transakcijama i omogućuje analizu prijevarnih i neprijevarnih transakcija.

Skup podataka sadrži:

- 200 000 redaka
- 24 stupca
- kvantitativne podatke
- kvalitativne podatke
- datumsku i vremensku dimenziju
- oznaku je li transakcija prijevarna

---

## 🛠️ Korištene tehnologije

U projektu su korištene sljedeće tehnologije:

- Python
- Jupyter Notebook
- pandas
- SQLAlchemy
- MySQL
- Power BI
- GitHub

---

## ⭐ Glavne funkcionalnosti projekta

Projekt uključuje:

- eksplorativnu analizu podataka
- dizajn relacijskog modela
- implementaciju relacijske baze podataka
- dizajn dimenzijskog modela
- izradu star sheme
- definiranje tablice činjenica i dimenzijskih tablica
- provedbu ETL procesa iz dva izvora
- punjenje skladišta podataka
- provjeru ispravnosti učitanih podataka
- izradu Power BI dashboarda
- provedbu OLAP analize
- vizualizaciju rezultata

---

## 📝 Napomena

Izvorni skup podataka i podaci za spajanje na bazu nisu uključeni u ovaj repozitorij.

Postavke za spajanje na bazu potrebno je lokalno prilagoditi prije pokretanja notebook datoteka.

---

# English

## Bank Fraud Warehouse Project

This repository contains a university project for the course **Warehouses and Data Mining**.

The project is based on the **Bank Transaction Fraud Detection** dataset and includes exploratory data analysis, relational database modeling, dimensional data warehouse modeling, ETL processing, data warehouse loading, and OLAP analysis with Power BI.

The goal of the project is to prepare, organize, and transform bank transaction data into a data warehouse structure in order to analyze fraudulent transactions and other useful business indicators.

---

## 📌 Project Description

The project is divided into five checkpoints.

### Checkpoint 1: Exploratory Data Analysis

The first part of the project includes basic analysis of the original CSV dataset using Python and the pandas library.

The analysis includes:

- loading the CSV file into a DataFrame
- displaying the first rows of the dataset
- checking the dataset size
- displaying column names
- checking missing values
- displaying unique values
- checking data types
- analyzing value frequencies by column

Based on the analysis, the dataset was found to be large enough, diverse, and suitable for further processing. It contains a time dimension as well as quantitative and qualitative data.

---

### Checkpoint 2: Relational Model Design and Implementation

The second part of the project focuses on designing and implementing a relational database model.

This part includes:

- defining entities
- defining attributes
- defining relationships between entities
- determining relationship cardinalities
- creating an ER diagram as a conceptual model
- creating an EER diagram as a logical model
- implementing the model in MySQL
- loading data into the relational database

The relational database was later used as one of the data sources in the ETL process.

---

### Checkpoint 3: Dimensional Model Design

The third part of the project focuses on creating a dimensional data model.

The dimensional model is based on a **star schema**, where the fact table is placed in the center and dimension tables are connected to it.

The central fact table is:

- `fact_bank_transaction`

The main dimension tables are:

- `dim_customer`
- `dim_account`
- `dim_merchant`
- `dim_device`
- `dim_transaction_type`
- `dim_transaction_location`
- `dim_currency`
- `dim_date`

The main measures in the fact table are:

- transaction amount
- account balance
- fraud indicator
- transaction count

The model also includes hierarchies, such as location hierarchy and merchant hierarchy. Advanced dimensional modeling concepts were also included, such as slowly changing dimensions and a degenerate dimension.

---

### Checkpoint 4: ETL Process and Data Warehouse Loading

The fourth part of the project focuses on the ETL process.

The ETL process consists of three main phases:

- **Extract** – extracting data from sources
- **Transform** – cleaning, aligning, and preparing data
- **Load** – loading data into the data warehouse

Data was loaded from two sources:

- MySQL relational database
- CSV file

The project uses an 80/20 data source split:

- 80% of the data was loaded into MySQL
- 20% of the data remained in a CSV file
- both sources were later integrated into the final data warehouse

After loading the data warehouse, validation checks were performed. These included checking row counts, verifying that the fact table successfully connects to all dimensions, and comparing data between the sources and the warehouse.

---

### Checkpoint 5: OLAP Analysis and Visualization

The fifth part of the project uses **Power BI** as the OLAP tool.

A data model connected to the dimensional data warehouse was created in Power BI. Dashboards, charts, tables, and KPI cards were then created to analyze bank transactions and fraud.

The analysis includes:

- total transaction amount
- average transaction amount
- total number of transactions
- number of fraudulent transactions
- fraud rate
- analysis by transaction type
- analysis by device type
- analysis by merchant category
- analysis by location
- analysis through hierarchies

The following OLAP operations were also performed:

- slice
- dice
- drill-down
- roll-up
- pivot

---

## 📊 Dataset

The dataset used in this project is **Bank Transaction Fraud Detection**.

The dataset contains bank transaction data and enables the analysis of fraudulent and non-fraudulent transactions.

The dataset contains:

- 200,000 rows
- 24 columns
- quantitative data
- qualitative data
- date and time dimension
- fraud indicator column

---

## 🛠️ Technologies Used

The following technologies were used in the project:

- Python
- Jupyter Notebook
- pandas
- SQLAlchemy
- MySQL
- Power BI
- GitHub

---

## ⭐ Main Project Features

The project includes:

- exploratory data analysis
- relational model design
- relational database implementation
- dimensional model design
- star schema creation
- fact and dimension table definition
- ETL process from two sources
- data warehouse loading
- data validation
- Power BI dashboard creation
- OLAP analysis
- result visualization

---

## 📝 Note

The original dataset and database connection credentials are not included in this repository.

Database connection settings must be configured locally before running the notebook files.
