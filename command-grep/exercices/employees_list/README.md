# Liste d'emplyés 

`employees.csv`

```sql
Employee ID,First Name,Last Name,Department,Title,Salary
101,John,Doe,IT,Network Administrator,60000
102,Jane,Smith,Marketing,Sales Manager,80000
103,David,Brown,IT,Software Engineer,75000
104,Maria,Garcia,HR,Human Resources Manager,90000
105,Emily,Jones,IT,Web Developer,55000
106,James,Wilson,Finance,Financial Analyst,65000
107,Michael,Davis,Marketing,Marketing Specialist,45000
108,Samantha,Rodriguez,IT,Systems Administrator,70000
109,Kevin,Miller,IT,Database Administrator,80000
110,Andrea,Martinez,Finance,Accountant,55000
111,Jose,Hernandez,HR,Recruiter,50000
112,Ashley,Lopez,Marketing,Marketing Coordinator,40000
113,Kimberly,Jackson,Finance,Financial Planner,75000
114,Carlos,Perez,IT,Software Developer,85000
115,Sarah,Moore,HR,Employee Relations Manager,95000
116,Daniel,Taylor,Marketing,Sales Representative,50000
117,Karen,Anderson,IT,Project Manager,90000
118,Brian,Thomas,Finance,Financial Advisor,70000
119,Michelle,Jackson,HR,Compensation Analyst,65000
120,Amanda,White,Marketing,Marketing Director,100000
121,Matthew,Harris,IT,Help Desk Technician,40000
122,Laura,Martin,Finance,Senior Financial Analyst,85000
123,Joshua,Thompson,IT,Information Security Analyst,90000
124,Melissa,Lee,HR,Training Coordinator,55000
125,Angel,Gonzalez,Marketing,Marketing Manager,85000
126,Elizabeth,Clark,IT,Software Tester,60000
127,Richard,Robinson,IT,Technical Writer,65000
128,Stephanie,Walker,Finance,Payroll Specialist,50000
129,Nathan,Perkins,Marketing,Product Manager,95000
130,Cynthia,Young,IT,Network Engineer,80000
```

Dans le fichier des employés ci-dessus, utilisez la commande `grep` pour obtenir diverses informations:

* Trouvez toutes les lignes comportant le prénom "John"
* Trouvez toutes les lignes contenant le département "IT"
* Cherchez toutes les lignes contenant le mot "Manager" dans le champs "Title" et les afficher dans le terminal
* Cherchez toutes les lignes dont le salaire est de "75000" et afficher le résultat dans le terminal
* Cherchez toutes les lignes dont le nom de famille est "Smith" et dont le titre est "Sales", les afficher dans le terminal
* Cherchez toutes les lignes qui contiennent soit le département "IT", soit le département "Marketing"
* Trouvez toutes les lignes possédant le département "Financial" et le titre d'analyste.
* Trouvez toutes les lignes dont le salaire est de 50000, 55000 ou 60000
* Trouvez toutes les lignes dont le nom de famille est soit "Garcia", soit "Wilson" et dont le salaire est plus grand que 65000