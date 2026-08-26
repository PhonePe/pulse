# PhonePe Pulse - Data

The Indian digital payments story has truly captured the world’s imagination. From the largest towns to the remotest villages, there is a payments revolution being driven by the penetration of mobile phones, mobile internet and state-of-art payments infrastructure built as Public Goods championed by the central bank and the government. PhonePe started in 2016 and has been a strong beneficiary of the API driven digitisation of payments in India. When we started, we were constantly looking for definitive data sources on digital payments in India without much success. As a way of giving back to the data and developer community, we decided to open the anonymised aggregate data sets that demystify the what, why and how of digital payments in India. Licensed under the [CDLA-Permissive-2.0 open data license](https://github.com/PhonePe/pulse/blob/main/LICENSE), the PhonePe Pulse Dataset API is a first of its kind open data initiative in the payments space.

## Announcements

### About This Data Release

The datasets within this repository have been refreshed to accommodate the below changes resulting in
a simpler data structure.

### What Has Changed?

- **Polished Metric Definitions:** Every metric now features a single, fully documented definition
  that outlines exactly what is included and excluded. If any further clarifications are required,
  please feel free to reach out to pulse@phonepe.com.

- **Refreshed and Restated Data:** To ensure consistency across the full time series in accordance
  with updated definitions, earlier periods from JFM 2018 have also been restated. All the metrics
  core to the Pulse ecosystem have been updated till AMJ 2026.

- **Simpler Transaction Category Structure:** The previous split (P2P, RCBP, FS, Merchant, and
  Others) was difficult to interpret - particularly within the &quot;FS (Financial Services)&quot; and &quot;Others&quot;
  buckets. We have streamlined this into three mutually exclusive categories:
  - **P2P:** Person-to-person money transfers.
  - **Utilities:** Recharges and bill payments.
  - **Business:** Payments to merchants (this consolidates the activity previously spread across
    FS, Merchant, and Others).  
    _Note:_ These three categories sum up to the total transactions.

- **New Addition:** Merchant Data: For the first time, PhonePe Pulse is introducing merchant data
  cut to showcase the acceptance side of digital payments. This release includes &quot;Registered
  Merchants&quot;, which represents the life-till-date count of unique merchants onboarded on the
  platform, published at both the state and district levels. This allows users to analyze the
  geographic spread and density of India&#39;s digital payment infrastructure. As with all Pulse data,
  these datasets are fully aggregated and anonymised.

### Important Note on Earlier Data

Figures for past quarters in this current release will **not exactly** match the numbers published earlier for
those same periods. This is a deliberate outcome of moving to this new approach. Hence, minor
differences will be present due to edge cases.  
**Practical Implication:** Figures from this release should not be compared against previously published
figures, and the two datasets should not be joined into a single series. Any growth read across that data
boundary will reflect a change in methodology rather than a change in underlying user activity.

### Data Coverage:

This repository contains data spanning from Q1 2018 (January - March) through Q2 2026 (April - June).

### ~~Upcoming Release:~~ Released:

Expanded district-level data. ~~Please watch this space for updates.~~

<!-- TOC -->

## Table of Contents

- [PhonePe Pulse - Data](#phonepe-pulse---data)
  - [Announcements](#announcements)
  - [Table of Contents](#table-of-contents)
  - [Goal](#goal)
  - [Guide](#guide)
  - [Documentation](#documentation)
    - [Folder Structure](#folder-structure)
    - [JSON Structure / Syntax](#json-structure--syntax)
      - [Aggregated](#1-aggregated)
        - [<u>data/aggregated/transaction/country/india/2018/1.json</u>](#11-dataaggregatedtransactioncountryindia20181json)
        - [<u>data/aggregated/user/country/india/2021/1.json</u>](#12-dataaggregatedusercountryindia20211json)
        - [<u>data/aggregated/merchant/country/india/2021/1.json</u>](#13-dataaggregatedmerchantcountryindia20211json)
      - [Map](#2-map)
        - [<u>data/map/transaction/hover/country/india/2021/1.json</u>](#21-datamaptransactionhovercountryindia20211json)
        - [<u>data/map/user/hover/country/india/2021/1.json</u>](#22-datamapuserhovercountryindia20211json)
        - [<u>data/map/merchant/hover/country/india/2021/1.json</u>](#23-datamapmerchanthovercountryindia20211json)
      - [Top](#3-top)
        - [<u>data/top/transaction/country/india/2021/1.json</u>](#31-datatoptransactioncountryindia20211json)
        - [<u>data/top/user/country/india/2021/1.json</u>](#32-datatopusercountryindia20211json)
        - [<u>data/top/merchant/country/india/2021/1.json</u>](#33-datatopmerchantcountryindia20211json)
  - [FAQs](#faqs)
  - [LICENSE](#license)

<!-- /TOC -->

## Goal

Our goal is to share this data with everyone (license below), so that you can build your own understanding, insights and visualization on how digital payments have evolved over the years in India.

## Guide

This [data](https://github.com/PhonePe/pulse/tree/main/data) has been structured to provide details of following three sections with data cuts on **Transactions**, **Users** and **Merchants** of PhonePe Pulse - Explore tab.

1. **Aggregated** - Aggregated values of various payment categories as shown under <u>Categories</u> section
1. **Map** - Total values at the State and District levels.
1. **Top** - Totals of top States / Districts

All the data provided in these folders is of JSON format. For more details on the structure/syntax you can refer to the [JSON Structure / Syntax](https://github.com/PhonePe/pulse#json-structure--syntax) section of the documentation.

## Documentation

### Folder Structure

Head to the [data](https://github.com/PhonePe/pulse/tree/main/data) folder to the find below shown structure. Overall, above mentioned sections data can be found at top level folder structure.

Under each of these sections there are folders for **Transactions**, **Users** and **Merchants** respectively.

Data for **Transactions**, **Users** and **Merchants** is grouped under country level within **India** folder which further grouped the data into each year (_for country level data_) and there is one folder with name **state** which groups data for all the available states of India respectively.

Similar to country level data, state level data too grouped into each year. All of these year folders(_both at country and state level_) have a maximum of four files with names starting from 1 to 4. These numbers represent each quarter in the selected year.

<ins>Example</ins>: `2021 > 1.json` represents data for quarter 1 (_Jan, Feb and Mar 2021_)

For details on syntax of each of these files, refer to [JSON Structure / Syntax](https://github.com/PhonePe/pulse#json-structure--syntax).

```
data
|___ aggregated
    |___ transaction
        |___ country
            |___ india
                |___ 2018
                |    1.json
                |    2.json
                |    3.json
                |    4.json

                |___ 2019
                |    ...
                |___ 2019
                |___ state
                    |___ andaman-&-nicobar-islands
                        |___2018
                        |   1.json
                        |   2.json
                        |   3.json
                        |   4.json

                    |___ andhra-pradesh
                    |    ...
                    |    ...
```

### JSON Structure / Syntax

#### 1. Aggregated

##### 1.1 <u>data/aggregated/transaction/country/india/2018/1.json</u>

Transaction data broken down by type of payment at country level.

For complete details on syntax find the comments in below code

**NOTE:** Similar syntax is followed for state level too. Ex: <u>data/aggregated/transaction/country/india/state/delhi/2018/1.json</u>

```javascript
{
    "success": true, //Ignore. For internal use only
    "code": "SUCCESS", //Ignore. For internal use only
    "data": {
        "transactionData": [
            {
                "name": "Retail", //Type of payment category
                "paymentInstruments": [
                    {
                        "type": "TOTAL",
                        "count": 72550406, //Total number of transactions for the above payment category
                        "amount": 1.4472713558652578E10 //Total value
                    }
                ]
            },

            ...,

            ...,

        ]
    },
    "responseTimestamp": 1630346628866 //Ignore. For internal use only.
}
```

##### 1.2 <u>data/aggregated/user/country/india/2021/1.json</u>

Users data broken down by devices at country level.

For complete details on syntax find the comments in below code

**NOTE:** Similar syntax is followed for state level too. Ex: <u>data/aggregated/user/country/india/state/delhi/2021/1.json</u>

```javascript
{
    "success": true, //Ignore. For internal use only.
    "code": "SUCCESS", //Ignore. For internal use only.
    "data": {
        "aggregated": {
            "registeredCount": 284985430, //Total number of registered users for the selected quarter.
        },
    },
    "responseTimestamp": 1630346630074 //Ignore. For internal use only.
}
```

##### 1.3 <u>data/aggregated/merchant/country/india/2021/1.json</u>

Merchant data at country level.

For complete details on syntax find the comments in below code

**NOTE:** Similar syntax is followed for state level too. Ex: <u>data/aggregated/merchant/country/india/state/delhi/2021/1.json</u>

```javascript
{
    "success": true, //Ignore. For internal use only.
    "code": "SUCCESS", //Ignore. For internal use only.
    "data": {
        "aggregated": {
            "registeredCount": 284985430, //Total number of registered users for the selected quarter.
        },
    },
    "responseTimestamp": 1630346630074 //Ignore. For internal use only.
}
```

#### 2. Map

##### 2.1 <u>data/map/transaction/hover/country/india/2021/1.json</u>

Total number of transactions and total value of all transactions at the state level.

For complete details on syntax find the comments in below code

```javascript
{
    "success": true, //Ignore. For internal use only.
    "code": "SUCCESS", //Ignore. For internal use only.
    "data": {
        "hoverDataList": [ //Internally, this being used to show state level data whenever a user hovers on a particular state.
            {
                "name": "puducherry", //State
                "metric": [
                    {
                        "type": "TOTAL",
                        "count": 3309432, //Total number of transactions done within the selected year-quarter for the current state.
                        "amount": 5.899309571743641E9 //Total transaction value within the selected year-quarter for the current state.
                    }
                ]
            },

            ...,

            ...,

            {
                "name": "tamil nadu",
                "metric": [
                    {
                        "type": "TOTAL",
                        "count": 136556674,
                        "amount": 2.4866814387365314E11
                    }
                ]
            }
        ]
    },
    "responseTimestamp": 1630346628834 //Ignore. For internal use only.
}
```

##### 2.2 <u>data/map/user/hover/country/india/2021/1.json</u>

Total number of registered users at the state level.

For complete details on syntax find the comments in below code

```javascript
{
    "success": true, //Ignore. For internal use only.
    "code": "SUCCESS", //Ignore. For internal use only.
    "data": {
        "hoverData": { //Internally, this being used to show state level data whenever a user hovers on a particular state.
            "puducherry": {
                "registeredCount": 346279, //Total number of registered users for the selected state
            },

            ...,

            ...,

            "tamil nadu": {
                "registeredCount": 16632608,
                "appOpens": 348801714
            }
        }
    },
    "responseTimestamp": 1630346628866 //Ignore. For internal use only.
}
```

##### 2.3 <u>data/map/merchant/hover/country/india/2021/1.json</u>

Total number of registered merchants at the state level.

For complete details on syntax find the comments in below code

```javascript
{
    "success": true, //Ignore. For internal use only.
    "code": "SUCCESS", //Ignore. For internal use only.
    "data": {
        "hoverData": { //Internally, this being used to show state level data whenever a user hovers on a particular state.
            "puducherry": {
                "registeredCount": 346279, //Total number of registered merchants for the selected state
            },

            ...,

            ...,

            "tamil nadu": {
                "registeredCount": 16632608,
                "appOpens": 348801714
            }
        }
    },
    "responseTimestamp": 1630346628866 //Ignore. For internal use only.
}
```

#### 3. Top

##### 3.1 <u>data/top/transaction/country/india/2021/1.json</u>

Top 10 states / districts where the most number of the transactions happened for a selected year-quarter combination.

For complete details on syntax find the comments in below code

**NOTE:** Similar syntax is followed for state level too. The only exception is, it won't have data for states. Ex: <u>data/top/transaction/country/india/state/delhi/2021/1.json</u>

```javascript
{
    "success": true, //Ignore. For internal use only.
    "code": "SUCCESS", //Ignore. For internal use only.
    "data": {
        "states": [ //List of states where most number of transactions happened along with total value for a selected year-quarter combination.
            {
                "entityName": "karnataka", // State name
                "metric": {
                    "type": "TOTAL",
                    "count": 523797492, //Total number of transactions
                    "amount": 7.549953574123948E11 //Total value of all transactions
                }
            },

            ...,
        ],
        "districts": [ //List of districts where most number of transactions happened along with total value for a selected year-quarter combination.
            {
                "entityName": "bengaluru urban", //District name
                "metric": {
                    "type": "TOTAL",
                    "count": 348712787, //Total number of transactions
                    "amount": 4.324013412317671E11 //Total value of all transactions
                }
            },

            ...,
        ]
    },
    "responseTimestamp": 1630346629360 //Ignore. For internal use only.
}
```

##### 3.2 <u>data/top/user/country/india/2021/1.json</u>

Top 10 states / districts where most number of users registered from, for a selected year-quarter combination.

For complete details on syntax find the comments in below code

**NOTE:** Similar syntax is followed for state level too. The only exception is, it won't have data for states. Ex: <u>data/top/user/country/india/state/delhi/2021/1.json</u>

```javascript
{
    "success": true, //Ignore. For internal use only.
    "code": "SUCCESS", //Ignore. For internal use only.
    "data": {
        "states": [ //List of states where the most number of users registered from, for a selected year-quarter combination.
            {
                "name": "maharashtra", //State name
                "registeredUsers": 37077537 //Number of registered users
            },

            ...,
        ],
        "districts": [ //List of districts where the most number of users registered from, for a selected year-quarter combination.
            {
                "name": "bengaluru urban", //State name
                "registeredUsers": 9955387 //Number of registered users
            },

            ...,
        ]
    },
    "responseTimestamp": 1630346630074 //Ignore. For internal use only.
}
```

##### 3.3 <u>data/top/merchant/country/india/2021/1.json</u>

Top 10 states / districts where most number of merchants registered from, for a selected year-quarter combination.

For complete details on syntax find the comments in below code

**NOTE:** Similar syntax is followed for state level too. The only exception is, it won't have data for states. Ex: <u>data/top/merchant/country/india/state/delhi/2021/1.json</u>

```javascript
{
    "success": true, //Ignore. For internal use only.
    "code": "SUCCESS", //Ignore. For internal use only.
    "data": {
        "states": [ //List of states where the most number of merchants registered from, for a selected year-quarter combination.
            {
                "name": "maharashtra", //State name
                "registeredUsers": 37077537 //Number of registered merchants
            },

            ...,
        ],
        "districts": [ //List of districts where the most number of merchants registered from, for a selected year-quarter combination.
            {
                "name": "bengaluru urban", //State name
                "registeredUsers": 9955387 //Number of registered merchants
            },

            ...,
        ]
    },
    "responseTimestamp": 1630346630074 //Ignore. For internal use only.
}
```

## FAQs

1. `How frequently data gets updated?`
   <br/><u>A:</u> The frequency is once in three months.
2. `How to report a bug or raise a query?`
   <br/><u>A:</u> Use GitHub issues to [raise a query](https://github.com/PhonePe/pulse/issues/new).

## LICENSE

[Community Data License Agreement – Permissive – Version 2.0](https://github.com/PhonePe/pulse/blob/main/LICENSE)
