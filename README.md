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














print("Percentage of ",name,' is ',Percentage)

Remarks = input("Enter remarks: ")

try:

query = "INSERT INTO CLASS12 (name, Math_marks, Phy_marks, Computer_marks, Chem_marks, Eng_marks, Percentage, Teacher_Remarks)

data = (name, Math_marks, Phy_marks, Computer_marks, Chem_marks, Eng_marks, Percentage, Remarks)

cursor.execute(query, data)

connection.commit()

print("The report has been added to the list!")

except Exception as e:

print("Error occurred:", e)

time.sleep(1)

teacher_login(connection, cursor)

elif choice 2:

display_items(cursor)

print("Which report would you like to remove?")

id = int(input("Enter admission id:"))

try:

query = f"DELETE FROM CLASS12 WHERE Admn_no={id}""

cursor execute(query)

connection.commit)

print("The report has been removed











print("Invalid item!", e)

time.sleep(1)

teacher_login(connection, cursor)

elif choice 3:

display_items(cursor)

print("Which student's marks would you like to update?") id = int(input("Enter admission ID:"))

print("Which category would you like to update?")

print("1. Maths")

print("2. Physics")

print("3. Computer")

print("4. Chemistry")

print("5. English")

print("6. Percentage")

print("7. Remarks")

subject_choice = int(input("Enter the category number (1-7):"))

subject = ""

if subject_choice == 1:

subject = "Math_marks"

elif subject_choice == 2:

subject = "Phy_marks"

elif subject_choice == 3:

subject = "Computer_marks"

elif subject_choice == 4:

subject = "Chem_marks"





elif subject_choice == 5:

subject = "Eng_marks"

elif subject_choice== 6:

subject = "Percentage"

elif subject_choice== 7:

subject = "Teacher_Remarks"

else:

print("Invalid choice!")

time.sleep(1)

teacher_login(connection, cursor)

return

if subject choice == 7:

record = input("Enter the updated record:")

query = f"UPDATE CLASS12 SET {subject} = %s WHERE Admn_no = {id}" data = (record,)

else:

record = int(input("Enter the updated record:"))

query = f"UPDATE CLASS12 SET {subject} = {record} WHERE Admn_no =

try:

cursor.execute(query, data)

connection.commit()

print("The record has been updated!")

except Exception as e:

print("Invalid Admission ID or error updating record!", e)














time.sleep(1)

teacher_login(connection, cursor)

elif choice= 4:

display_items(cursor)

time.sleep(1.5)

teacher_login(connection, cursor)

elif choice = 5:

main()

else:

print("Invalid Choice!")

time.sleep(1)

teacher_login(connection, cursor)

#parent login function

--")

def parent_login(connection, cursor):

print("-----------Welcome, You are logged in as a Parent!-

print("Here is the list of choices:")

print("Choice 1: Check Your child's report", "Choice 2: Exit", sep="\n")

choice = int(input("Enter your choice:"))

if choice 1:

name = input("Enter your name:")

print(f"Greetings From Green Fields School, {name}")

time.sleep(0.5)

display_name(cursor)












print(

while True:

id = int(input("Enter your child's ID NO:"))

try:

query = f""SELECT * FROM CLASS12 WHERE Admn_no={id}"

cursor.execute(query)

result = cursor.fetchone()

if result:

print("ID:", result[0])

print("Name:", result[1])

print("Math:", result[2])

print("Physics:", result[3])

print("Computer:", result[4])

print("Chemistry:", result[5])

print("English:", result[6])

print("Percentage:", result[7])

print("Remarks:", result[8])

if result[7]>=33:

print("Congratulations! Your child has passed this academic year!")

else:

else:

print("Sorry! Your child has failed this academic year")

print("No record found for this ID.")

i = input("Want to check another result? Answer Y for Yes and N for No: ")

if i.upper() = 'N':

break

except Exception as e:









print("Invalid Entry!")

print(e)

break

print("Thank you! Have a sweet day!")

time.sleep(1)

parent_login(connection, cursor)

elif choice = 2:

main()

else:

print("Invalid Choice!")

time.sleep(1)

parent_login(connection, cursor)

#user interface

def main():

inloop = 1

while inloop:

printo

print("

--")

-")

print("--------------------Welcome to GREEN FIELDS SCHOOL-

print("-

print("How do you want to Enter?")

print("Choice 1: Teacher Login", "Choice 2: Parent Login", "Choice 3: Exit",

sep="\n")

choice = input("Enter your choice:")

if choice == '1



password = input("Enter the password: ")

if password == "gfs123":

teacher_login(connection, cursor)

else:

print("Incorrect Password!")

time.sleep(1)

elif choice == '2':

parent_login(connection, cursor)

elif choice == '3':

exit(

else:

print("Invalid Choice!")

main(






