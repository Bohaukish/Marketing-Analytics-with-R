https://www.udemy.com/course/marketing-analytics-with-r-2020/learn/lecture/20628480#overview

https://rstudio.cloud/projects


Analytics: tuning raw data into insight for making better decisions.

Business Analytics: stastical analtsis and predictive modeling to improve business planning.

Need for Analytics: Cost reduction, better marketing and product analysis, organizational analytics, better and faster decision making.

![](https://tva1.sinaimg.cn/large/008eGmZEly1gmn0iv2wpyj31az0u0b29.jpg)

一个流程

![](https://tva1.sinaimg.cn/large/008eGmZEly1gmn0o4nqz5j31840ps1kx.jpg)

环境： R Studio Cloud 用的github账号登入

## Importing and Exporting Data

### Importing

```
# read csv
f = read.csv(filename, header = T)  
# if true first line will be read as labels

# read URL/txt file in table format
f = read.table(URLLinkStr, header = TRUE, sep = "," stringAsFactors = FALSE)
view(f) # show

# read excel file
read.xlsx(filename, sheetIndex = 1)

# read google sheet
# importing file from web and install packages
library(gsheet)

g_data = as.data.frame(gsheet2tbl(URLStr))
```

### Exporting

```
# save in csv format
write.csv(filetobewritten, filename)
```

## Operatosrs

Assignment赋值 Operators: h <- 24 ,也可以 24 -> h

Arithmetic: exp是^, mod取余:%%, integer division取整除法: %/%

Logical: 跟python差不多 & 按位与， && 短路与 只返回vector第一项返回结果
```
x <- c(1,2,3,4,5,6,7,8,9)

x>2 & x<5 #FALSE FALSE TRUE TRUE FALSE FALSE FALSE FALSE FALSE

# 找出这个数组大于2小于5的部分
x[x>2 & x<5]

```
Telational: <= 之类的跟python一样

## Data Types and Data Structure

### 数据类型

![](https://tva1.sinaimg.cn/large/008eGmZEly1gmnsjkxsllj315c0icwgx.jpg)

### 数据结构

![](https://tva1.sinaimg.cn/large/008eGmZEly1gmo26agwekj30qy0de0u6.jpg)

#### Vector
```
# vector
x = c(1,2,3) 或 x = 1:3
length(x)  # 3
x = c(x, 4) # add an element 
```

#### Matrix



```
# matrix: 二维的
# matrix filled row wise with giving names to rows and columns
m1 = matrix(1:6, nrow = 3, byrow = TRUE, dimnames = list(c("d", "e", "f"), c("a","b")))

    a b
 c  1 2
 d  3 4
 f  5 6

# Other ways to construct matrix
m2 <- 1:6
dim(m2) = c(3, 2) # row <- 3, column <- 2

    1  4
    2  5
    3  6

# adding row to a matrix
newrow = c(7, 8)
m3 = rbind(m1, newrow)

    1 2
    3 4
    5 6
    7 8
```

#### Lists
It can contains different data type, numbers, strings, vectors and matrix.

```
v1 = c(1, 2)
v2 = month.abb[4:5] ## 月份缩写
combinedV = c(v1, v2) # all elements converted to character by default
list = list(v1, v2) # each vector stays in their original types


[[1]]
[1] 1 2

[[2]]
[1] "Apr" "May"
```

#### Arrays

Sorts data in more than 2 dimensions

dim(2, 3, 4): 4个矩阵，每个都有2 rows 3 columns

```
v1 <- c(5, 9, 3)
v2 <- c(10, 11, 12, 13, 14, 15)
column.names <- c("COL1", "COL2", "COL3")
row.names <- c("ROW1", "ROW2", "ROW3")
matrix.names <- c("Matrix1", "Matrix2")

# Take these vectors as input to the array

result <- array(c(v1, v2, dim = c(3, 3, 2), dimnames = list(row.names, column.names, matrix.names)))

. . Matrix 1
        COL1 COL2 COL3
ROW1     5    10   13
ROW2     9    11   14
ROW3     3    12   15

另一个matrix2跟1是一样的
```
#### Data Frame

跟python的差不多

```
rollno = 1:10
name = paste('S', 1:10, sep = '') # S1 S2 S3...S10
age = round(rnorm(10. mean=25, sd=2), 1)  
# round用于保留一位小树，rnorm产生一系列的随机数,随机数个数,均值和标准差都可以设定
gender = sample(c('M', 'F'), size = 10, replace = T) # sample就是用来随机产生M和F的
df = data.frame(rollno, name, age, gender)
```
明天从Section5开始刷


