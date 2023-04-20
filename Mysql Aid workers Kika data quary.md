## Data Analysis Quaries:

- Retrieve the Number of incidents by country:
- Retrieve the locations of the incidents:
- Retrieve the actors of the incident:
- Retrieve the weapons used:
- Retrieve the organization mostly involved:
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by organisation:
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:



***

## Solutions
- Retrieve the Number of incidents by country:
```sql
SELECT Country, COUNT(Country) FROM aid_workers_kika  GROUP BY Country;

```
![q1](https://user-images.githubusercontent.com/114537955/233423200-b95f7fd4-9bc4-4fd0-afeb-2fddd7bfdce2.png)

***
- Retrieve the locations of the incidents: 
```sql
SELECT Location, COUNT(Location) FROM aid_workers_kika  GROUP BY Location;

```
![q2](https://user-images.githubusercontent.com/114537955/233424151-3e67f103-8d1e-4335-b98b-a00652e526cc.png)

***
- Retrieve the actors of the incident:
```sql
SELECT Actor, COUNT(Actor) FROM aid_workers_kika  GROUP BY Actor;

```
![q3](https://user-images.githubusercontent.com/114537955/233425468-554ca8e1-b8c1-4fa1-9f3c-9a6cbd5da211.png)

***
- Retrieve the weapons used:
```sql
SELECT Weapon, COUNT(Weapon) FROM aid_workers_kika  GROUP BY Weapon;

```
![q4](https://user-images.githubusercontent.com/114537955/233426469-255505d8-2be3-4aea-89cd-57779d66f6b3.png)

***
- Retrieve the organization mostly involved:
```sql
SELECT Organisation, COUNT(Organisation) FROM aid_workers_kika  GROUP BY Organisation;

```
![q5](https://user-images.githubusercontent.com/114537955/233427173-adf043aa-2be6-4d48-b49b-1c8db7802071.png)

***
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
```sql
SELECT Country, SUM(Killed) as Total_Killed, SUM(Injured) as Total_Injured, SUM(Kidnapped) as Total_Kidnapped, SUM(Arrested) as Total_Arrested,
SUM(Killed_in_Captivity) as Total_Killed_in_Captivity FROM aid_workers_kika GROUP BY Country ORDER BY Total_Killed DESC, Total_Injured DESC, Total_Kidnapped DESC,
Total_Arrested DESC, Total_Killed_in_Captivity DESC;

```
![q6](https://user-images.githubusercontent.com/114537955/233427807-d256ecd8-2a94-48fa-ae57-976b28568672.png)

***
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by organisation:
```sql
SELECT Organisation, SUM(Killed) as Total_Killed, SUM(Injured) as Total_Injured, SUM(Kidnapped) as Total_Kidnapped, SUM(Arrested) as Total_Arrested,
SUM(Killed_in_Captivity) as Total_Killed_in_Captivity FROM aid_workers_kika GROUP BY Organisation ORDER BY Total_Killed DESC, Total_Injured DESC, Total_Kidnapped DESC,
Total_Arrested DESC, Total_Killed_in_Captivity DESC;

```
![q7](https://user-images.githubusercontent.com/114537955/233428342-7c18a902-c08a-47d6-b6e5-e5bf141a0b0a.png)

***
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
```sql
SELECT Weapon, SUM(Killed) as Total_Killed, SUM(Injured) as Total_Injured, SUM(Kidnapped) as Total_Kidnapped, SUM(Arrested) as Total_Arrested,
SUM(Killed_in_Captivity) as Total_Killed_in_Captivity FROM aid_workers_kika GROUP BY Weapon ORDER BY Total_Killed DESC, Total_Injured DESC, Total_Kidnapped DESC,
Total_Arrested DESC, Total_Killed_in_Captivity DESC;

```
![q8](https://user-images.githubusercontent.com/114537955/233428916-0b1d9254-23cc-4fd8-8830-e50cf50c67f1.png)

***
- Retrieve the number of aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
```sql
SELECT year, SUM(Killed) as Total_Killed, SUM(Injured) as Total_Injured, SUM(Kidnapped) as Total_Kidnapped, SUM(Arrested) as Total_Arrested,
SUM(Killed_in_Captivity) as Total_Killed_in_Captivity FROM aid_workers_kika GROUP BY year ORDER BY Total_Killed DESC, Total_Injured DESC, Total_Kidnapped DESC,
Total_Arrested DESC, Total_Killed_in_Captivity DESC;

```
![q9](https://user-images.githubusercontent.com/114537955/233429403-7cb3fb70-a768-4294-adbd-7b60529edaf0.png)

***
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
```sql
SELECT Country, SUM(Int_l_Killed) as Total_Int_l_Killed, SUM(Int_l_Injured) as Total_Int_l_Injured, SUM(Int_l_Kidnapped) as Total_Int_l_Kidnapped,
SUM(Int_l_Arrested) as Total_Int_l_Arrested, SUM(Int_l_Killed_Captive) as Total_Int_l_Killed_Captive FROM aid_workers_kika GROUP BY Country
ORDER BY Total_Int_l_Killed DESC, Total_Int_l_Injured DESC, Total_Int_l_Kidnapped DESC, Total_Int_l_Arrested DESC, Total_Int_l_Killed_Captive DESC;

```
![q10](https://user-images.githubusercontent.com/114537955/233430124-89fb000a-6f21-4e07-bb59-0345010037c8.png)

***
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
```sql
SELECT Country, SUM(Int_l_Killed) as Total_Int_l_Killed, SUM(Int_l_Injured) as Total_Int_l_Injured, SUM(Int_l_Kidnapped) as Total_Int_l_Kidnapped,
SUM(Int_l_Arrested) as Total_Int_l_Arrested, SUM(Int_l_Killed_Captive) as Total_Int_l_Killed_Captive FROM aid_workers_kika GROUP BY Country
ORDER BY Total_Int_l_Killed DESC, Total_Int_l_Injured DESC, Total_Int_l_Kidnapped DESC, Total_Int_l_Arrested DESC, Total_Int_l_Killed_Captive DESC;

```
![q11](https://user-images.githubusercontent.com/114537955/233430413-19ea1d23-173a-4b78-942e-308ee757c0e8.png)

***
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
```sql
SELECT Organisation, SUM(Int_l_Killed) as Total_Int_l_Killed, SUM(Int_l_Injured) as Total_Int_l_Injured, SUM(Int_l_Kidnapped) as Total_Int_l_Kidnapped,
SUM(Int_l_Arrested) as Total_Int_l_Arrested, SUM(Int_l_Killed_Captive) as Total_Int_l_Killed_Captive FROM aid_workers_kika GROUP BY Organisation
ORDER BY Total_Int_l_Killed DESC, Total_Int_l_Injured DESC, Total_Int_l_Kidnapped DESC, Total_Int_l_Arrested DESC, Total_Int_l_Killed_Captive DESC;

```
![q12](https://user-images.githubusercontent.com/114537955/233430843-3653af2f-237d-4249-9d9d-309701ea9bc8.png)

***
- Retrieve the number of Int'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
```sql
SELECT Weapon, SUM(Int_l_Killed) as Total_Int_l_Killed, SUM(Int_l_Injured) as Total_Int_l_Injured, SUM(Int_l_Kidnapped) as Total_Int_l_Kidnapped,
SUM(Int_l_Arrested) as Total_Int_l_Arrested, SUM(Int_l_Killed_Captive) as Total_Int_l_Killed_Captive FROM aid_workers_kika GROUP BY Weapon
ORDER BY Total_Int_l_Killed DESC, Total_Int_l_Injured DESC, Total_Int_l_Kidnapped DESC, Total_Int_l_Arrested DESC, Total_Int_l_Killed_Captive DESC;

```
![q13](https://user-images.githubusercontent.com/114537955/233431287-91fda4a6-5fdb-4f41-8603-acd0134ee7c6.png)

***
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
```sql
SELECT Country, SUM(Nat_l_Killed) as Total_Nat_l_Killed, SUM(Nat_l_Injured) as Total_Nat_l_Injured, SUM(Nat_l_Kidnapped) as Total_Nat_l_Kidnapped,
SUM(Nat_l_Arrested) as Total_Nat_l_Arrested, SUM(Nat_l_Killed_Captive) as Total_Nat_l_Killed_Captive FROM aid_workers_kika GROUP BY Country
ORDER BY Total_Nat_l_Killed DESC, Total_Nat_l_Injured DESC, Total_Nat_l_Kidnapped DESC, Total_Nat_l_Arrested DESC, Total_Nat_l_Killed_Captive DESC;

```
![q14](https://user-images.githubusercontent.com/114537955/233432141-5103f209-c375-4740-b358-a73dfb5461eb.png)

***
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
```sql
SELECT Organisation, SUM(Nat_l_Killed) as Total_Nat_l_Killed, SUM(Nat_l_Injured) as Total_Nat_l_Injured, SUM(Nat_l_Kidnapped) as Total_Nat_l_Kidnapped,
SUM(Nat_l_Arrested) as Total_Nat_l_Arrested, SUM(Nat_l_Killed_Captive) as Total_Nat_l_Killed_Captive FROM aid_workers_kika GROUP BY Organisation
ORDER BY Total_Nat_l_Killed DESC, Total_Nat_l_Injured DESC, Total_Nat_l_Kidnapped DESC, Total_Nat_l_Arrested DESC, Total_Nat_l_Killed_Captive DESC;

```
![q15](https://user-images.githubusercontent.com/114537955/233432751-b1ea2278-dcc2-423b-86dd-fe2007768132.png)

***
- Retrieve the number of Nat'l aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
```sql
SELECT Weapon, SUM(Nat_l_Killed) as Total_Nat_l_Killed, SUM(Nat_l_Injured) as Total_Nat_l_Injured, SUM(Nat_l_Kidnapped) as Total_Nat_l_Kidnapped,
SUM(Nat_l_Arrested) as Total_Nat_l_Arrested, SUM(Nat_l_Killed_Captive) as Total_Nat_l_Killed_Captive FROM aid_workers_kika GROUP BY Weapon
ORDER BY Total_Nat_l_Killed DESC, Total_Nat_l_Injured DESC, Total_Nat_l_Kidnapped DESC, Total_Nat_l_Arrested DESC, Total_Nat_l_Killed_Captive DESC;

```
![q16](https://user-images.githubusercontent.com/114537955/233433169-b0f37fcd-c33d-4bba-a6cc-960249fa1fd9.png)

***
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
```sql
SELECT Country, SUM(Female_Killed) as Total_Female_Killed, SUM(Nat_l_Injured) as Total_Female_Injured, SUM(Female_Kidnapped) as Total_Female_Kidnapped,
SUM(Female_Arrested) as Total_Female_Arrested, SUM(Female_Killed_Captive) as Total_Female_Killed_Captive FROM aid_workers_kika GROUP BY Country
ORDER BY Total_Female_Killed DESC, Total_Female_Injured DESC, Total_Female_Kidnapped DESC, Total_Female_Arrested DESC, Total_Female_Killed_Captive DESC;

```
![q17](https://user-images.githubusercontent.com/114537955/233433808-ae13ad54-9f18-40d7-8c1c-a799a4fda548.png)

***
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
```sql
SELECT Organisation, SUM(Female_Killed) as Total_Female_Killed, SUM(Nat_l_Injured) as Total_Female_Injured, SUM(Female_Kidnapped) as Total_Female_Kidnapped,
SUM(Female_Arrested) as Total_Female_Arrested, SUM(Female_Killed_Captive) as Total_Female_Killed_Captive FROM aid_workers_kika GROUP BY Organisation
ORDER BY Total_Female_Killed DESC, Total_Female_Injured DESC, Total_Female_Kidnapped DESC, Total_Female_Arrested DESC, Total_Female_Killed_Captive DESC;

```
![q18](https://user-images.githubusercontent.com/114537955/233434733-a2403c12-e8ac-43f0-a8c7-b9fa85c70af1.png)

***
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
```sql
SELECT Weapon, SUM(Female_Killed) as Total_Female_Killed, SUM(Nat_l_Injured) as Total_Female_Injured, SUM(Female_Kidnapped) as Total_Female_Kidnapped,
SUM(Female_Arrested) as Total_Female_Arrested, SUM(Female_Killed_Captive) as Total_Female_Killed_Captive FROM aid_workers_kika GROUP BY Weapon
ORDER BY Total_Female_Killed DESC, Total_Female_Injured DESC, Total_Female_Kidnapped DESC, Total_Female_Arrested DESC, Total_Female_Killed_Captive DESC;
```
![q19](https://user-images.githubusercontent.com/114537955/233435239-b8ae1a8f-c99f-4f48-a138-0153fda5c640.png)

***
- Retrieve the number of female aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
```sql
SELECT year, SUM(Female_Killed) as Total_Female_Killed, SUM(Nat_l_Injured) as Total_Female_Injured, SUM(Female_Kidnapped) as Total_Female_Kidnapped,
SUM(Female_Arrested) as Total_Female_Arrested, SUM(Female_Killed_Captive) as Total_Female_Killed_Captive FROM aid_workers_kika GROUP BY year
ORDER BY Total_Female_Killed DESC, Total_Female_Injured DESC, Total_Female_Kidnapped DESC, Total_Female_Arrested DESC, Total_Female_Killed_Captive DESC;
```
![q20](https://user-images.githubusercontent.com/114537955/233435751-048d981a-5a1f-4968-bff9-73f13f816851.png)

***
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by country:
```sql
SELECT Country, SUM(Male_Killed) as Total_Male_Killed, SUM(Male_Injured) as Total_Male_Injured, SUM(Male_Kidnapped) as Total_Male_Kidnapped,
SUM(Male_Arrested) as Total_Male_Arrested, SUM(Male_Killed_Captive) as Total_Male_Killed_Captive FROM aid_workers_kika GROUP BY Country
ORDER BY Total_Male_Killed DESC, Total_Male_Injured DESC, Total_Male_Kidnapped DESC, Total_Male_Arrested DESC, Total_Male_Killed_Captive DESC;
```
![q21](https://user-images.githubusercontent.com/114537955/233436328-d5e5601b-3559-4927-9fd0-79830e550be5.png)

***
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by organization:
```sql
SELECT Organisation, SUM(Male_Killed) as Total_Male_Killed, SUM(Male_Injured) as Total_Male_Injured, SUM(Male_Kidnapped) as Total_Male_Kidnapped,
SUM(Male_Arrested) as Total_Male_Arrested, SUM(Male_Killed_Captive) as Total_Male_Killed_Captive FROM aid_workers_kika GROUP BY Organisation
ORDER BY Total_Male_Killed DESC, Total_Male_Injured DESC, Total_Male_Kidnapped DESC, Total_Male_Arrested DESC, Total_Male_Killed_Captive DESC;
```
![q22](https://user-images.githubusercontent.com/114537955/233437741-88eee7c3-9ef1-49ae-bb47-c68aa3af6390.png)

***
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by weapon:
```sql
SELECT Weapon, SUM(Male_Killed) as Total_Male_Killed, SUM(Male_Injured) as Total_Male_Injured, SUM(Male_Kidnapped) as Total_Male_Kidnapped,
SUM(Male_Arrested) as Total_Male_Arrested, SUM(Male_Killed_Captive) as Total_Male_Killed_Captive FROM aid_workers_kika GROUP BY Weapon
ORDER BY Total_Male_Killed DESC, Total_Male_Injured DESC, Total_Male_Kidnapped DESC, Total_Male_Arrested DESC, Total_Male_Killed_Captive DESC;
```
![q23](https://user-images.githubusercontent.com/114537955/233439038-99cf5a05-f93a-4579-9983-d3eeaf5923db.png)

***
- Retrieve the number of male aid workers killed, injured, Kidnapped, arrested or killed in captivity by year:
```sql
SELECT year, SUM(Male_Killed) as Total_Male_Killed, SUM(Male_Injured) as Total_Male_Injured, SUM(Male_Kidnapped) as Total_Male_Kidnapped,
SUM(Male_Arrested) as Total_Male_Arrested, SUM(Male_Killed_Captive) as Total_Male_Killed_Captive FROM aid_workers_kika GROUP BY year
ORDER BY Total_Male_Killed DESC, Total_Male_Injured DESC, Total_Male_Kidnapped DESC, Total_Male_Arrested DESC, Total_Male_Killed_Captive DESC;
```
![q24](https://user-images.githubusercontent.com/114537955/233439568-69cc37ae-92c0-4e8e-9932-9d5d81325aa8.png)

***

