# itsme
cursor.execute('CREATE TABLE IF NOT EXISTS CLASS12(Admn_no INTEGER PRIMARY KEY AUTO INCREMENT,name varchar(30),Math_marks INTEGER,Phy_marks INTEGER, Computer_marks INTEGER,Chem_marks INTEGER,Eng_marks INTEGER, Percentage Integer, Teacher_Remarks varchar(600))')

#creating table for records

query = ""SELECT * FROM CLASS12"

cursor.execute(query)

results = cursor.fetchall)

if results= []:

cursor.execute(""INSERT INTO CLASS12 (name,Math_marks,Phy_marks,Computer_marks,Chem_marks,Eng_marks, Percentag Teacher Remarks)

VALUES

('Aasha', 90, 96, 99, 97, 96, 96, 'One of the best students of my class, sincer and trustworthy, can improve in Maths'),

('Madhu', 90, 95, 94, 93, 94, 93, 'Has the potential to be 1st in class'),

