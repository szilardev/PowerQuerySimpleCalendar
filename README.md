# PowerQuerySimpleCalendar

Generate a simple calendar table in Power Query (M language)

## Description

This project provides a simple Power Query (M language) script to generate a calendar table. The generated calendar table can be extremely useful in data modeling projects within Power BI, Excel, or other applications where a date dimension is required. The basic solution is easily customizable, allowing you to add additional columns such as Year, Month, Day, Quarter, Week Number, and more.

## Features

- **Simple Calendar Generation:** Create a continuous list of dates based on a defined start and end date.
- **Automatic Column Expansion:** The script automatically adds basic date attributes (Year, Month, Day) to the table.
- **Customizability:** Easily modify the code to include additional columns or adjust the date range to suit your project’s needs.

## Installation and Usage

### 1. Insert the Code

1. Open the Power Query Editor in Excel or Power BI.
2. Create a new query and click on **Advanced Editor**.
3. Copy the M-code from the [_dimSimpleCalendar](./_dimSimpleCalendar) file and paste it into the new query.

### 2. Customize the Calendar

You can adjust the start and end dates in the code to generate a calendar for your desired date range. For example:

```m
let
    // Parameters
    Begin = try BeginDate otherwise #date(Date.Year(DateTime.LocalNow())-5,1,1),  // BeginDate parameter or #date(ThisYear-5,month,day) or you can switch the BeginDate to #date(year, month, day) 
    LangCode = "en-US",                                                           // US english en-US, british english en-GB, hungarian hu-HU, german de-DE
    FirstDayOfWeek = Day.Monday,                                                  // Day.Monday, Day.Sunday
    
    // Generate Data from here 
    ToDate = #date(Date.Year(DateTime.LocalNow())+1,12,31),                        //The closing date is December 31st of the following year by default. 
    [...]
```

### 3. Run the Query
After inserting and customizing the code:

- Click Done in the Advanced Editor.
- Refresh the query to display the generated calendar table.

### Reporting Issues and Contributions
If you encounter any issues or have suggestions for improvements, please open an issue or submit a pull request on this GitHub repository. Contributions are always welcome!

### License
This project is available under the MIT License. (Ensure you create the LICENSE file in the root of your repository if it isn’t already present.)


