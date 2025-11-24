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







examination, has the potential to do better'), (Shiva', 90, 70, 73, 89, 87, 82, 'He has improved a lot since his last

of scope in improving his marks in physics'), "Shail', 80, 65, 87, 91, 93, 83, 'He hns the potential to do better, and has a lot

has the potential to do better')"") ("Priya', 39, 45, 52, 56, 54, 49, 'Needs to work harder to gain good marks, she

connection.commit()

#displaying table

def display_items(cursor):

query = ""SELECT * FROM CLASS12"'

cursor.execute(query)

results = cursor.fetchall()

print("List of Students: ")

print("ID ", "Name"," Math", " Phy"," CS"," Chem"," Eng", "Percentage", "Remarks", sep=" ")

for each in results:

print(each[0], each[1], each[2], each[3], each[4], each[5], each[6], each[7], each[8], sep=" ")

#displaying records for parent

def display_name(cursor):

query = ""'SELECT Admn_no, name FROM CLASS12"

cursor.execute(query)

results = cursor.fetchall)

print("List of Students: ")

print("ID", "Name", sep=" ")

for each in results:

print(each[0], each[1], sep=" ")





teacher login function

def teacher_login(connection, cursor):

print(

print("-Welcome! You are logged in as Teacher!-")

print(

print("Here are the list of choices:")

print("Choice 1: Add a student report",

"Choice 2: Remove a report",

"Choice 3: Update marks",

"Choice 4: See the report of all the students",

"Choice 5: Exit",

sep="\n")

choice = int(input("Enter your choice: "))

print(

time.sleep(0.5)

if choice= 1:

print("What would you like to add?")

name = input("Enter name: ")

Math_marks = int(input("Enter math marks: "))

Phy marks = int(input("Enter physics marks: "))

Computer_marks = int(input("Enter computer marks: "))

Chem marks = int(input('Enter Chemistry marks: '))

Eng marks = int(input('Enter English marks: '))

Percentage =

(Math_marks+Phy_marks+Computer_marks+Chem_marks+Eng_marks)//5
