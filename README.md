# PowerBI
Dax and Measure use daily bases

## Date Table
'''
Date =
VAR StartDate =
    DATE ( YEAR ( MIN ( 'Transaction'[Order Date] ) ), 1, 1 )
VAR EndDate =
    DATE ( YEAR ( MAX ( 'Transaction'[Actual Delivery] ) ), 12, 31 )
RETURN
    ADDCOLUMNS (
        CALENDAR ( StartDate, EndDate ),
        "Year", YEAR ( [Date] ),
        "MonthNumber", MONTH ( [Date] ),
        "Month", FORMAT ( [Date], "mmmm" ),
        "Quarter", "Q " & FORMAT ( [Date], "Q" ),
        "QuarterNumber", FORMAT ( [Date], "Q" ),
        "Month Year", FORMAT ( [Date], "mmmm yyyy" )
    )
    
'''
