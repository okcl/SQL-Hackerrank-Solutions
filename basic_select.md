
---

### **[Weather Observation Station 5](https://www.hackerrank.com/challenges/weather-observation-station-5)**

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

*Sample Input*

Let's say that CITY only has four entries: DEF, ABC, PQRS and WXY

*Sample Output*

ABC 3 

PQRS 4

*Explanation*

When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with the respective lengths 3,3,4,3,3,4, and 33. The longest-named city is obviously PQRS, but there are 33 options for shortest-named city; we choose ABC, because it comes first alphabetically.

#### **Solution**
```sql
SELECT city, LENGTH(city)
FROM station
ORDER BY LENGTH(city) DESC,
city ASC
LIMIT 1;

SELECT city, LENGTH(city)
FROM station
ORDER BY LENGTH(city) ASC,
city ASC
LIMIT 1;
```

---

### **[Weather Observation Station 6](https://www.hackerrank.com/challenges/weather-observation-station-6)**

Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

#### **Solution**
```sql
SELECT DISTINCT city
FROM station
WHERE LEFT(city, 1) IN ('a','e','i','o','u');
```

---

### **[Weather Observation Station 7](https://www.hackerrank.com/challenges/weather-observation-station-7)**

Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

#### **Solution**
```sql
SELECT DISTINCT city
FROM station
WHERE RIGHT(city, 1) IN ('a','e','i','o','u');
```

---
### **[Weather Observation Station 8](https://www.hackerrank.com/challenges/weather-observation-station-8)**

Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

#### **Solution**
```sql
SELECT DISTINCT city
FROM station
WHERE LEFT(city, 1 ) IN ('a','e','i','o','u')
AND RIGHT(city, 1) IN ('a','e','i','o','u');
```

---

### **[Weather Observation Station 9](https://www.hackerrank.com/challenges/weather-observation-station-9)**

Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

#### **Solution**
```sql
SELECT DISTINCT city
FROM station
WHERE NOT LEFT(city,1) IN ('a','e','u','i','o');
```

---

### **[Weather Observation Station 10](https://www.hackerrank.com/challenges/weather-observation-station-10)**

Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

#### **Solution**
```sql
SELECT DISTINCT city
FROM station
WHERE NOT RIGHT(city,1) IN ('a','e','u','i','o');
```

---

### **[Weather Observation Station 11](https://www.hackerrank.com/challenges/weather-observation-station-11)**

Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

#### **Solution**
```sql
SELECT DISTINCT city
FROM station
WHERE NOT LEFT(city,1) IN ('a','e','i','o','u')
OR NOT RIGHT(city,1) IN ('a','e','i','o','u');
```

---

### **[Weather Observation Station 12](https://www.hackerrank.com/challenges/weather-observation-station-12)**

Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

#### **Solution**
```sql
SELECT DISTINCT city
FROM station
WHERE NOT LEFT(city,1) IN ('a','e','i','o','u')
AND NOT RIGHT(city,1) IN ('a','e','i','o','u');
```

---

### **[Weather Observation Station 12](https://www.hackerrank.com/challenges/more-than-75-marks)**

Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Input Format

The STUDENTS table is described as follows:

|  Colomn | Type |
|---|---|
| ID  | Integer |
| NAME | String   |
| Marks  | Integer  |

The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

Sample Input

|  ID | Name | Marks|
|----|-----------|--|
| 1 | Ashley |81|
| 2 | Samantha |75|
| 3 | Julia  |76|
| 4 | Belvet |84|


Sample Output

Ashley
Julia
Belvet
Explanation

Only Ashley, Julia, and Belvet have Marks > 75 . If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.

#### **Solution**
```sql
SELECT DISTINCT city
FROM station
WHERE NOT LEFT(city,1) IN ('a','e','i','o','u')
AND NOT RIGHT(city,1) IN ('a','e','i','o','u');