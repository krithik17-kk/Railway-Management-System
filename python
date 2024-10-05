import mysql.connector as a

passwd=str(input("DATABASE PASSWORD: "))

con = a.connect(host="localhost",

user="root", passwd = passwd)

#SELECT DATA BASE IF EXIST

c = con.cursor()

c.execute("show databases")

dl = c.fetchall()

dl2 =[]

for i in dl:

    dl2.append(i[0])

if 'myrailway' in dl2:

    sql = "use myrailway"

    c.execute(sql)

else:
  sql1 = "create database myrailway"
c.execute(sql1)
sql2 = "use myrailway"
c.execute(sql2)
sql3="""create table Train (Name varchar(50), Cost integer, Distance integer,Date varchar(20))"""
c.execute(sql3)
sql4="""create table Customer (Name varchar(20), Train varchar(25), Payment integer,Date varchar(20),Phone varchar(20))"""
c.execute(sql4)
c.execute(sql4)

sql5="""create table Bills (Detail varchar(20), Cost integer, Date varchar(20))"""

c.execute(sql5)

sql6 = "create table Worker (Name varchar(100), Work varchar(20), Salary varchar(20))"""

c.execute(sql6)

con.commit()

#SYSTEM PASSWORD LOGIN

def signin():

  print("\n")

  print(">>>>>>>>> Welcome, My Railway System [MRS] <<<<<^^^^^……………………")

  print("\n")

  p = input("System Password: ")

  if p == "mrs111":

     options()

  else:

     signin()

#PROJECT WORKING OPTIONS

def options():

   print("""
1.Add Train

2.Book Train

3.Add Bill

4.Add Worker

6.Display Train

7.Display Payments

8.Display Bills
""")


choice = input("Select Option: ")

while True:

 if (choice == '1'):

  AddTrain()

 elif (choice=='2'):

  BookTrain()

 elif (choice=='3'):

  AddBill()

 elif (choice=='4'):

  AddWorker()

 elif (choice=='5'):

  dTrain()

 elif (choice=='6'):
     dPayments()

 elif (choice=='7'):

  dBills()

 elif (choice=='8'):

  dWorker()

 else:
    print("Enter Again...............")
    options()

#function to add new Trains data into Train table

def AddTrain():

   n = input("Train Name: ")

   c = input("Cost: ")

   b = input("Distance: ")

   d = input("Date: ")

   data = (n,c,b,d)

   sql = 'insert into Train values(%s, %s, %s, %s)'
   
   c = con.cursor()

   c.execute(sql,data)

   con.commit()

   print("Data Inserted Successfully")

   options()

#function to Display data from Train table

def dTrain():

  sql = 'select*from Train'

  c = con.cursor()

  c.execute(sql)

  d = c.fetchall()

  for i in d:

       print(" Name:"[0])

       print(" Cost: "[1])

       print(" Distance: ",i[2])

       print(" Date: ",[3])

       print(".......................")

options()
#function to add selling data into Customer table

def BookTrain():

    n = input("Customer Name:")

    s = input("Train: ")

    py = int(input("Payment: "))

    d = input("Date: ")

    p = input("Phone: ")

    data = (n,s,py,d,p)

    sql = 'insert into Customer values(%s, %s, %s, %s, %s)'

    c = con.cursor()

    c.execute(sql,data)

    con.commit()

    print("Data Inserted Successfully")

    options()
#function to Display selling data from Customer table

def dPayments():

   sd = input("Date: ")

   sql = 'select from Customer'

   c = con.cursor()

   c.execute(sql)

   d = c.fetchall()

   for i in d:

     if i[3] == sd:

       print(" Name: "[0])

       print(" Train: "[1])

       print(" Payment: ",i[2])

       print(" Date: ",[3])

       print(" Phone:"[4])

       print("..................")

options()
#function to add new bills

def AddBill():

    dt = input("Detail: ")

    c= input("Cost: ")

    d = input("Date: ")

    data = (dt,c,d)

    sql = 'insert into Bills values(%s, %s, %s)'

    c = con.cursor()

    c.execute(sql,data)

    con.commit()

    print("Data Inserted Successfully")

    options()
#function to display all previous bills

def dBills():

    sql = 'select from Bills'

    c = con.cursor()

    c.execute(sql)

    d = c.fetchall()

    for i in d:

         print("Detail: ",i[0])

         print(" Cost: ",[1])

         print("Date: ",i[2])

         print(".............................")

options()
#function to add new worker

def AddWorker():

    n = input("Name: ")

    w = input("Work: ")

    s = input("Salary: ")

    data = (n,w,s)

    sql = 'insert into Worker values(%s, %s, %s)'

    c = con.cursor()

    c.execute(sql,data)

    con.commit()

    print("Data Inserted Successfully")
  
    options()
#function to display all workers

def dWorker():

   sql = 'select * from Worker'
  
   c = con.cursor()

   c.execute(sql)

   d = c.fetchall()

   for i in d:
 
       print(" Name: "[0])

       print(" Work: ",i[1])

       print(" Salary: "[2])

       print("...................")

   options()

signin()
    
