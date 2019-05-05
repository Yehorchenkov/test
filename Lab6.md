```R
```
1. Створити матрицю mat з 5 стовпцями та 10 строками за допомогою
matrix з випадковими даними (функція rnorm(50)).
```R
```
> mat <- matrix(rnorm(50), 10,5)
##was created mat with help of function matrix with random values
> mat
[,1]        [,2]        [,3]         [,4]         [,5]
[1,] -0.281691703 -0.17807799 -0.07196429 -0.518140632  0.508167291
[2,]  0.182379693 -1.56392114 -1.48600356 -0.072883540  0.452065497
[3,] -1.259509930  0.24656849 -1.57519541  2.127973077  0.008847789
[4,]  1.371689826 -0.79932004 -0.50944294 -0.898414709  0.501849677
[5,]  0.898691546  0.94971926  2.33045013 -2.215284801  0.207479918
[6,]  0.366147773  1.41185324  0.93292362 -0.546697563 -0.463356150
[7,]  0.001921326  0.79049850 -0.14580029 -1.987545370 -1.110550973
[8,]  1.831444072  0.08011577  1.46654037 -0.007065457 -0.605395919
[9,] -0.533305515  0.63091964 -0.92325020 -0.590775931 -0.914728525
[10,]  0.389134252  0.92548369 -0.44298234  1.550165507  1.122814922
##showed how works matrix function
```R
```
2. Знайти максимальне значення в кожному стовпці.
```R
```
> apply(mat, 2, max)
[1] 1.831444 1.411853 2.330450 2.127973 1.122815
##with help of apply function was founded max values of all column of matrix mat
##in function value 2 mean column
```R
```
3. Знайти середнє (mean) значення кожного стовпця.
```R
```
apply(mat, 2, mean)
[1]  0.29669013  0.24938394 -0.04247249 -0.31586694 -0.02928065
##with help of apply function was founded mean values of all column of matrix mat
##in function value 2 means column
```R
```
4. Знайти мінімальне значення в кожному рядку.
```R
```
> apply(mat, 1, min)
[1] -0.5181406 -1.5639211 -1.5751954 -0.8984147 -2.2152848 -0.5466976
[7] -1.9875454 -0.6053959 -0.9232502 -0.4429823
##above an example of using columnmin function where 1 means that we use rows of matrix
```R
```
5. Відсортувати кожен стовбець таблиці.
```R
```
apply(mat,2,sort)
[,1]        [,2]        [,3]         [,4]         [,5]
[1,] -1.259509930 -1.56392114 -1.57519541 -2.215284801 -1.110550973
[2,] -0.533305515 -0.79932004 -1.48600356 -1.987545370 -0.914728525
[3,] -0.281691703 -0.17807799 -0.92325020 -0.898414709 -0.605395919
[4,]  0.001921326  0.08011577 -0.50944294 -0.590775931 -0.463356150
[5,]  0.182379693  0.24656849 -0.44298234 -0.546697563  0.008847789
[6,]  0.366147773  0.63091964 -0.14580029 -0.518140632  0.207479918
[7,]  0.389134252  0.79049850 -0.07196429 -0.072883540  0.452065497
[8,]  0.898691546  0.92548369  0.93292362 -0.007065457  0.501849677
[9,]  1.371689826  0.94971926  1.46654037  1.550165507  0.508167291
[10,]  1.831444072  1.41185324  2.33045013  2.127973077  1.122814922
##function apply helped to sort values in each column of matrix mat
```R
```
6. Знайти кількість значень < 0 для кожного стовпця. Використати свою
функцію.
```R
```
> apply(mat,2,function(x) sum(x<0))
[1] 3 3 7 8 4
##with help of function apply was founded numbers of values that less than zero
```R
```
7. Вивести вектор з булевими значеннями TRUE та FALSE. TRUE, якщо в
стовпці є елементи >2, FALSE – якщо немає.
```R
```
> apply(mat,2,function(x) sum(x>2))
[1] 0 0 1 1 0
##was showed that function apply return values that more than 2
> apply(mat,2,function(x) sum(x>2)>0)
[1] FALSE FALSE  TRUE  TRUE FALSE
##return logical values where TRUE-when column has values more than 2 and FALSE- when column doesn't consist values that more than 2
```R
```
8. Створить список list1 <- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2)). Для цього списку знайдіть sum за допомогою lapply.
```R
```
> list1 <- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2))
##was created list1 with help of some cinditions of different observations
> list1
$observationA
[1] 1 2 3 4 5 7 6 5 4 3

$observationB
[,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6
##print observations
> lapply(list1, mean)
$observationA
[1] 4

$observationB
[1] 3.5

> lapply(list1, sum)
$observationA
[1] 40

$observationB
[1] 21
##with help of function lapply was found sum of A and B observations
```R
```
9. Для кожного елементу списку list1 знайдіть максимальне та мінімальне
значення (range) за допомогою lapply та sapply.
```R
```
> lapply(list1, min)
$observationA
[1] 1
$observationB
[1] 1
##used lapply function
> sapply(list1, min)
observationA observationB 
1            1 
##used sapply function
##we can see that lapply and sapply functions have the same result
> lapply(list1, max)
$observationA
[1] 7
$observationB
[1] 6
##was used lapply function
> sapply(list1, max)
observationA observationB 
7            6 
##was used sapply function
##each of this functions have the same result
```R
```
10.Для вбудованого набору даних InsectSprays знайти середнє count для
кожного spray.
```R
```
> g <- split(InsectSprays$count, InsectSprays$spray)
##split the "count" values into six groups based on types of sprays
> g
$A
 [1] 10  7 20 14 14 12 10 23 17 20 14 13

$B
 [1] 11 17 21 11 16 14 17 17 19 21  7 13

$C
 [1] 0 1 7 2 3 1 2 1 3 0 1 4

$D
 [1]  3  5 12  6  4  3  5  5  5  5  2  4

$E
 [1] 3 5 3 5 3 6 1 1 3 2 6 4

$F
 [1] 11  9 15 22 15 16 13 10 26 26 24 13

> sapply(g, mean)
        A         B         C         D         E         F 
14.500000 15.333333  2.083333  4.916667  3.500000 16.666667 
> lapply(g, mean)
$A
[1] 14.5

$B
[1] 15.33333

$C
[1] 2.083333

$D
[1] 4.916667

$E
[1] 3.5

$F
[1] 16.66667
##calculated mean value of every type of spray with help of two functions:sapply and apply that have the same result
```R
```
