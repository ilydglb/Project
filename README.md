# OOPProject

*You should check the main method inside Main class to understand the code better.*

We set the Student class as abstract because we wanted to specify student types as grad or undergrad. 
There are undergrad students and grad students of two types inheriting Student class, master students and doctoral students (so GradStudent is abstract too).
Student class has attributes that was given in project's general information and has two lists storing societies the student is in and attendance info as extra.
We store grades of courses in Student class in a hashmap and calculate GPA.
We don't add courses inside Student class because courses can be of two types, grad and undergrad. So we add them inside UnderGradStudent and GradStudent classes. (an under grad student cannot have a grad course and same for reverse)
We have two abstract methods inside Student class and a method that calculates whether a student fails because lack of attendance or not.

We set the Course class as abstract because we wanted to specify course types as grad or undergrad.
Inside Course class we have attributes that was given in project's general information and two other attributes that we use in some methods.
There is an array of student ids (not a list because only students store the courses objects they are taking but courses don't store students objects -this information was given in project directives).
We also have course notes and necessary conditions about adding a note here.

Lecturer class has lists of classes UndergradCourse and GradCourse since a lecturer can give both.
And for regular lecturers, isHeadOfDepartment variable is set to false by default. 
There are two constructors, one is for creating the head of department, setting  isHeadOfDepartment to true.
And if this variable is true this lecturer can give a graduate certificate which is inside the Lecturer class.

## Extra attributes and methods:

Course class:

    -total_course_hour_in_aweek: int
    -topics: ArrayList
    +
    +

Student class:

    -societies: ArrayList
    -courseattendance: HashMap
    +FailOfAttendance()
    +

Lecturer class:

    -isHeadOfDepartment: boolean
    -title: String
    -yearOfService: int
    -monthly_salary: int
    +Calculatemonthly_salary()
    +

Staff class:

    -monthly_salary:int
    -yearOfService: int
    -annualDayOff: int
    +CalculateSalary()
    +DecreaseDayOff()

Secretay class (BONUS):

    +DropUndGradCourse()
    +DropGradCourse()
    


## Some exceptions you should check:

Course class:

- Inside setstdId() method we used try-catch to catch an ArrayIndexOutOfBoundsException in case of we exceed maximum array index number(which is 100) because we used an array to store students' ids. 

Lecturer class:

- Inside giveGraduationCertificate() method we used try-catch to catch a NullPointerException in case the student or student's courses are null.

GradStudent and UndergradStudent class:

- While adding courses with addUndgradCourse() or addGradCourse() methods  we used try-catch to catch a NullPointerException to check whether the student takes a non-existent course.
- Also in the same methods, we checked whether the array bounds will be exceeded if we add the student's id into the course.
- And we also checked whether the student's courses already contains the course to be added inside the same methods.

Society class:

- Inside addMember() method we check whether the member list contains the student to be added already, and if not we add the student.
- Inside removeMember() method we check whether the student is already a member and if so we remove the object from the member ArrayList.
- Inside these both methods above we used try-catch to catch a NullPointerException in case of attempting to delete or add a non-existent student.

Secretary class:

- Inside appointLecToCourse() we used try-catch to catch a NullPointerException in case of attempting to appoint a non-existent lecturer or course.
- Inside the same method we check if courses of the lecturer is less than 9 and we also check whether the lecturer already gives this course.
- Inside removeLecFromCourse(), we again use NullPointerException to prevent from doing anyting if lecturer or course is null.
- Inside DropUndgradCourse() and DropGradCourse() methods we check necessary conditions inside try and catch NullPointerException if there are any (student or course might be non-existent).

*Note: We didn't feel the need to put an exception about "a student who takes the course does not have a grade" (which was in the general info of project) because we used a hashmap to store grades and courses.
So they are key value pairs and in a hashmap there can't be any values without keys and keys without values (in this case a grade).*

## Extra class:

Society class is for societies in the department. 
It has a UndergradStudent leader, a Lecturer supervisor and members who are undergraduate students created with an ArrayList. 
Members can be added and removed with some conditions.












