# DWBI_Project

I selected the Baseball Databank as the OLTP data set. I only take the files which can build good relations and have much valuable data. Since all these files has large set of columns and rows, I had to cut them to create certain set of data to use to make rich ETL process and make better hierarchies and dimensions.

Final Reports : 

      [Assignment1.pdf](https://github.com/shanika17/DWBI_Project/files/9141200/Assignment1.pdf)
      
      [Assignment2.pdf](https://github.com/shanika17/DWBI_Project/files/9141202/Assignment2.pdf)


As the preparation of the data sets I come up with 5 tables which are in Text format and CSV format
• Batting – Batting statistics. (CSV file)
• Players – This file contains all the details of players. ( Database Table)
• Salaries – Has the details of the player salaries. (CSV file)
• Teams – Contain all necessary data of the teams. (TEXT file)
• Series – All information about series. (TEXT file)

--Dataware house design

Dimensional Model created in snow flake design 

<img width="636" alt="Screenshot 2022-07-19 at 17 24 43" src="https://user-images.githubusercontent.com/88156395/179744165-7f5b80d7-0fe1-4178-9383-0b575d47fd4f.png">

--ETL Development

   --Extraction--

In this step, extract data from source files and load it for the staging table. And also truncate table to clean the database before loading to avoid duplicating data

<img width="321" alt="Screenshot 2022-07-19 at 17 46 17" src="https://user-images.githubusercontent.com/88156395/179748846-761424ec-a87a-4094-8630-45d0e6828e18.png">

   --Transformation and Loading--

In this step, I extract from the staging tables and load it to the Dim tables 

<img width="318" alt="Screenshot 2022-07-19 at 17 53 35" src="https://user-images.githubusercontent.com/88156395/179749661-e7e27d35-1fbb-42b6-ab8a-7188029e4cdf.png">

--SSAS Cube implementation

Data source defines from where, the cube is extracting data. So, I create the data source as DS_Baseball_DW and data source view as DSV_Baseball_DW. So it will show the linked tables. The snowflake schema is built as a cube. I create my cube as Cube_Baseball. Then I deploy it.

![cubicals](https://user-images.githubusercontent.com/88156395/179750851-32b36365-36e5-4e0e-9df5-7595b9ef8787.png)

--Demonstration of OLAP operations 

Connect an Excel workbook to the Cube using features available in Data tab mode.

I select my hierarchy as birth country, birth state and birth city in my Player dimension.

   Roll-up  : According to Birth country
   
   ![pivot_rolllup](https://user-images.githubusercontent.com/88156395/179752815-6db4d1fb-133c-478f-9e2b-ff2a9d8bff50.png)

   Drill-Down  : According to my hierachy
   
   ![3_drilldown](https://user-images.githubusercontent.com/88156395/179753371-6d4f07a7-720f-4897-b4f0-6a7ac855ca91.png)

   Slice : According to year 1876
   
   ![3_slice](https://user-images.githubusercontent.com/88156395/179753528-019df3d7-6d9d-49ad-ad31-f636320c8eb4.png)

   Dice : Accoding to year 1876 and country USA
   
   ![3_dice](https://user-images.githubusercontent.com/88156395/179753630-00c56984-7c48-4339-a57f-a5daa48c3e28.png)

   Pivot 
   
   ![RollUp](https://user-images.githubusercontent.com/88156395/179753842-ee5901a7-8c48-412f-a5b2-2771a7d4e8e8.png)
