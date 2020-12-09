# TP-commit-et-rollback-

import pyodbc
conn = pyodbc.connect('Driver={SQL Server};'
                      'Server=.;'
                      'Database=WideWorldImportersDW;'
                      'Trusted_Connection=yes;')

cursor = conn.cursor()
cursor.execute("select * from Dimension.City where [City Key] = 50085")    
#conn.rollback()
cursor.execute("UPDATE Dimension.City SET City='Paris' where [City Key] = 50085")
for row in cursor:
    print(row)
