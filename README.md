# Orthogonal Polynomials
> This MATLAB package is aiming to solve different types of orthogonal polynomials in the most efficient way.  

## Table of Contents
* [HermiteCollocationMatrix](#hermitecollocationmatrix)
* [LegendreCollocationMatrix](#legendrecollocationmatrix)
* [LaguerreCollocationMatrix](#laguerrecollocationmatrix)
* [HermiteRoots](#hermiteroots)
* [LegendreRoots](#legendreroots)
* [LaguerreRoots](#laguerreroots)
* [RecursiveTotalOrderIndex](#recursivetotalorderindex)
* [HyperbolicIndex](#hyperbolicindex)
* [MultiplyFunction](#multiplyfunction)
* [TotalOrderMultiDCollocationMatrix](#totalordermultidcollocationmatrix)
* [HyperbolicMultiDCollocationMatrix](#hyperbolicmultidcollocationmatrix)
<!-- * [License](#license) -->


## HermiteCollocationMatrix
The function uses the recurrence relationship of Hermite polynomials(probalists) to create a collocation matrix column by column.  
The general recurrence relationship is  
![WeChat402030cbfc0cb2bf4ce8e0daefe0c953](https://user-images.githubusercontent.com/56415387/125350184-66eff480-e32c-11eb-8e7e-953d3c1bc472.png)  
Some example terms of Hermite polynomials are  
![WechatIMG10351](https://user-images.githubusercontent.com/56415387/125350770-3ceb0200-e32d-11eb-9ee8-c855332726e5.png)  
### Input  
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### x
It is the unknown values in the polynomials listed above. x could be inputted as either a vector or a number.

### Output
#### C
The collocation matrix of Hermite Polynomials

### Example
#### (1) Inputting 1-dimensional sample
If you execute the following MATLAB code  
```
%create object 'new' to store the property of orthogonal polynomials
new=OrthogonalPolynomials(3);
%create Hermite collocation matrix using object 'new' and sample 1
C=HermiteCollocationMatrix(new,1)
```
where 'new' is the object that we create for the othogoanl polynomials. We are inputting 1 as the 1-dimensional sample point. The second line of the code is equivalent to the following code written in an object oriented syntax
```
C=new.HermiteCollocationMatrix(1)
```
You will get the following result as the collocation matrix for the Hermite polynomials  
  
![image](https://user-images.githubusercontent.com/56415387/125353945-32326c00-e331-11eb-8806-6a6285df0f22.png)  
#### (2) Inputting multi-dimensional sample
The function is also able to take multi-dimensional samples as input. In the following snipet of MATLAB code, you first create the multi-dimensional sample 'x' as an array. Then, create an object 'new' for the OrthogonalPolynomials by specifying its order 3. Lastly, you can create the Hermite collocation matrix with object 'new' and sample 'x'.
```
%create the multi-dimensional sample 'x'
x=[1 2 3 4];
%create an object 'new' for the OrthogonalPolynomials by specifying its order 3
new=OrthogonalPolynomials(3);
%create the Hermite collocation matrix with object 'new' and sample 'x'
C=HermiteCollocationMatrix(new,x)
```
The following image shows the results that you should be getting:  
![image](https://user-images.githubusercontent.com/56415387/126424789-06e299fa-76cf-43e6-990c-5cc6c1ef9f80.png)


## LegendreCollocationMatrix
The function uses the recurrence relationship of Legendre polynomials to create a collocation matrix column by column.  
The general recurrence relationship is the following
  
![image](https://user-images.githubusercontent.com/56415387/125355417-044e2700-e333-11eb-97bf-c55114c92684.png)  
  
Some example terms of Legendre polynomials are  
![image](https://user-images.githubusercontent.com/56415387/125355763-67d85480-e333-11eb-9e2c-0f956398ad3a.png)  
### Input  
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### x
It is the unknown values in the polynomials listed above. It could be inputted as either a vector or a number.

### Output
#### C
C is the collocation matrix of Legendre Polynomials

### Example
#### (1) Inputting 1-dimensional sample
If you execute the following MATLAB code  
```
%create object 'new' to store the property of orthogonal polynomials
new=OrthogonalPolynomials(3);
%create Legendre collocation matrix using object 'new' and sample 1
C=LegendreCollocationMatrix(new,1)
```
where 'new' is the object that we create for the othogoanl polynomials. We are inputting 1 as the 1-dimensional sample point. The second line of the code is equivalent to the following code written in an object oriented syntax
```
C=new.LegendreCollocationMatrix(1)
```
You will get the following result as the collocation matrix for Legendre polynomials  
  
![image](https://user-images.githubusercontent.com/56415387/125356261-f5b43f80-e333-11eb-9bc8-fb3246fd9c3a.png)  
#### (2) Inputting multi-dimensional sample
The function is also able to take multi-dimensional samples as its input. In the following snipet of MATLAB code, you first create a multi-dimensional sample 'x' as an array. Then, create an object 'new' for the OrthogonalPolynomials by specifying its order 3. Lastly, you can create the Legendre collocation matrix with object 'new' and sample 'x'.
```
%create the multi-dimensional sample 'x' as an array
x=[1 2 3 4];
%create an object 'new' for the OrthogonalPolynomials by specifying its order 3
new=OrthogonalPolynomials(3);
%create the Legendre collocation matrix with object 'new' and sample 'x'
C=LegendreCollocationMatrix(new,x)
```
The following image shows the results that you should be getting:  
![image](https://user-images.githubusercontent.com/56415387/126425025-6aa60673-6b18-4773-9ba9-35e695a400c5.png)


## LaguerreCollocationMatrix
The function uses the recurrence relationship of Laguerre polynomials to create a collocation matrix column by column.  
The general recurrence relationship is  
  
![image](https://user-images.githubusercontent.com/56415387/125356965-f39eb080-e334-11eb-8b78-cf11e2921f40.png)    
Some example terms of Laguerre polynomials (assume alpha = 0) are  
![image](https://user-images.githubusercontent.com/56415387/125357112-2d6fb700-e335-11eb-9598-fb91932e4a84.png)  
### Input  
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### x
It is the unknown values in the polynomials listed above. It could be inputted as either a vector or a number.
#### alpha
Alpha is the alpha value for Laguerre polynomials which is required in the general formula.

### Output
#### C
The collocation matrix of Laguerre Polynomials

### Example
#### (1) Inputting 1-dimensional sample
If you execute the following MATLAB code  
```
%create object 'new' to store the property of orthogonal polynomials
new=OrthogonalPolynomials(3);
%create Laguerre collocation matrix using object 'new', sample 1 and an alpha value of 0
C=LaguerreCollocationMatrix(new,1,0)
```
where is 'new' is the object that we create for the othogoanl polynomials. We are inputting 1 as the 1-dimensional sample point. The second line of the code is equivalent to the following code written in an object oriented syntax
```
C=new.LaguerreCollocationMatrix(1,0)
```
You will get the following result as the collocation matrix for Laguerre polynomials  
  
![image](https://user-images.githubusercontent.com/56415387/125357654-e8985000-e335-11eb-872e-21999c7c86a9.png)  
#### (2) Inputting multi-dimensional sample
The function is also able to take multi-dimensional samples as input. In the following snipet of MATLAB code, you first create the multi-dimensional sample 'x' as an array. Then, you create an object 'new' for the OrthogonalPolynomials by specifying its order 3. Lastly, you can create the Laguerre collocation matrix with object 'new', sample 'x' and alpha '0'.
```
%create the multi-dimensional sample 'x' as an array
x=[1 2 3 4];
%create an object 'new' for the OrthogonalPolynomials by specifying its order 3
new=OrthogonalPolynomials(3);
%create the Laguerre collocation matrix with object 'new', sample 'x' and alpha '0'
C=LaguerreCollocationMatrix(new,x,0)
```
The following image shows the results that you should be getting:  
![image](https://user-images.githubusercontent.com/56415387/126425787-c154ba4f-abd3-4f69-aaca-265ba00120fc.png)

## HermiteRoots
The function will first compute the T matrix as shown in the following figure. M is the order of the polynomials.  
![image](https://user-images.githubusercontent.com/56415387/125359551-6fe6c300-e338-11eb-88b9-6cfd1ed94a87.png)  
Then, the function will solve the roots of the polynomials by solving for the eigenvalues of T matrix.
### Input
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
### Output
#### roots
roots of the polynomials
### Example
If you execute the following MATLAB code  
```
% create an object 'new' for the orthogonal polynomial with order 3
new=OrthogonalPolynomials(3);
% compute the Hermite root of 'new'
roots=HermiteRoots(new)
```
You will get the following result as the Hermite roots of the polynomials  
  
![image](https://user-images.githubusercontent.com/56415387/125360308-b1c43900-e339-11eb-8a18-c035d72aa791.png)



## LegendreRoots
The function will first compute the T matrix as shown in the following figure. M is the order of the polynomials.  
![image](https://user-images.githubusercontent.com/56415387/125360775-5c3c5c00-e33a-11eb-9ca5-56f65e1f41ad.png)  
Then, the function will solve the roots of the polynomials by solving for the eigenvalues of T matrix.
### Input
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
### Output
#### roots
roots of the polynomials
### Example
If you execute the following MATLAB code  
```
% create an object 'new' for the orthogonal polynomial with order 3
new=OrthogonalPolynomials(3);
% compute the Legendre root of 'new'
roots=LegendreRoots(new)
```
You will get the following result as the Legendre roots of the polynomials  
  
![image](https://user-images.githubusercontent.com/56415387/125361651-9823f100-e33b-11eb-8a01-f9acfb07da6c.png)  

## LaguerreRoots
The function will first compute the T matrix as shown in the following figure. M is the order of the polynomials.  
![image](https://user-images.githubusercontent.com/56415387/125361923-0a94d100-e33c-11eb-97eb-3ebb52f5f643.png)  
Then, the function will solve the roots of the polynomials by solving for the eigenvalues of T matrix.
### Input
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### alpha
Alpha is the alpha value for Laguerre polynomials listed in the T matrix.
### Output
#### roots
roots of the polynomials
### Example
If you execute the following MATLAB code  
```
% create an object 'new' for the orthogonal polynomial with order 3
new=OrthogonalPolynomials(3);
% compute the Laguerre root of 'new' and alpha=0
roots=LaguerreRoots(new,0)
```
You will get the following result as the Laguerre roots of the polynomials  
  
![image](https://user-images.githubusercontent.com/56415387/125362373-c5bd6a00-e33c-11eb-8070-a6a7a01e7a17.png)  

## RecursiveTotalOrderIndex
### Intro
The choice of ordering the terms in the truncated series also impacts the presentation of the theoretical results. In fact, one of the essential differences between polynomials in a single variable and polynomials in several variables is the lack of a natural order in the latter. There are many ways to order the polynomials φα(ξ) and their coefficients according to the contents of the multi-index. One of them is tensor order. We define the ordering by assuming, without loss of generality, that 0≤αi≤M for i=1,···,d and
denote the rank of a multi-index α by |α|,where  
![image](https://user-images.githubusercontent.com/56415387/125364481-8a249f00-e340-11eb-890c-a930b1985ef0.png)  
Let's take an example of d=2 (d is the dimension) and M=2 (and M is the order). We would have the following tensor order index:  
![image](https://user-images.githubusercontent.com/56415387/125364630-d53eb200-e340-11eb-955d-c5368b18044b.png)  
Now, for the total order, we assume that the multi-indices are ordered according to the Lexicographic order. It is defined as, “a multi-index α is said to be of higher order than another multi-index, say β, and denoted by α>β, if the first nonzero entry in the difference is positive”. So, by applying this logic to the tensor order index we will filter it and get our total order index. Total order is less expensive while maintaining the accuracy to discribe the polynomials.  
Let's take an example of d=2 (d is the dimension) and M=2 (and M is the order). We would have the following total order index:  
![image](https://user-images.githubusercontent.com/56415387/125365120-ad038300-e341-11eb-864f-e29d910c0075.png)  

### Functionality
This function will be used to get a matrix that illustrates the index of the total order row by row. It is the same as the total order table above but in a matrix format.
### Input
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### M
The order of the polynomials
#### d
dimension 
### Output
#### H
the matrix describing the index of the total order
### Example
If you execute the following MATLAB code  
```
% create an object 'new' for the orthogonal polynomial with order 2
new=OrthogonalPolynomials(2);
% compute the total order index matrix of 'new' by specifying its dimension and order are both 2
H=RecursiveTotalOrderIndex(new,2,2)
```
You will get the following result which should be the same as the total order table above  
![image](https://user-images.githubusercontent.com/56415387/125365943-28b1ff80-e343-11eb-8226-7b3e975d9387.png)  


## HyperbolicIndex

### Intro
Now, assuming you have known what is the total order index from the previous section. Hyperbolic index is just a less expensive truncation compared to the total order. For total order, the following criterion is used to determine thr order of each one-dimensional polynomial in a multidimensional polynomial basis:  
![image](https://user-images.githubusercontent.com/56415387/125632964-1189ed3b-e6dd-456a-a110-3f1ef2757786.png)(1)  
where ||.||1 represents the L1 norm, and m is the common maximum expansion order for one dimensional polynomials.  
Here are graphical illustrations of the total order index:  
![image](https://user-images.githubusercontent.com/56415387/125633536-9c3d966f-ce4a-4d4f-a21b-876761374426.png)  
For hyperbolic index, the constraint is put on the ![image](https://user-images.githubusercontent.com/56415387/125634728-d4a2d821-21a5-4d2d-ba35-ca8bdc07d522.png)
norm of the indices’ vector d, where u ≤ 1, and the ![image](https://user-images.githubusercontent.com/56415387/125634746-afd3211e-dc54-437c-bac9-35800a0188bc.png) norm  is  casually defined as the u-th root of summation of each member of d to the power of u. Replacing the L1 norm in (1) with ![image](https://user-images.githubusercontent.com/56415387/125634772-5ddfd07f-6d40-4274-89ff-af872a6f946e.png) would result in  
![image](https://user-images.githubusercontent.com/56415387/125634917-e2b76938-9e09-45a1-8619-941024a95664.png)(2)  
In this scheme, the indices are limited between positive axis and a hyperbola which is represented by  
![image](https://user-images.githubusercontent.com/56415387/125635083-a1cbe353-6c64-4395-a6a9-26faca094bfe.png)  
Hence, this scheme is called hyperbolic, and u is called the hyperbolic factor. This technique would significantly reduce number of selected indices while preserving the accuracy in the total order approach.
Here are grahical illustrations of the hyperbolic index:  
![image](https://user-images.githubusercontent.com/56415387/125635393-52b3107b-d20d-4d61-8912-a3fe0fa892b1.png)  
### Functionality
This function will be used to get a matrix that illustrates the hyperbolic index row by row. The function would filter the total order index (H) that you can get from the function in the previous section using the logic in (2). 
### Input
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### H  
The total order index matrix that you can get using RecursiveTotalOrderIndex
#### u
The hyperbolic factor
#### order
The order of the polynomials 
### Output
#### Hyper
The matrix describing the hyperbolic index
### Example
If you execute the following MATLAB code  
```
% create an object 'new' for the orthogonal polynomial with order 3
new=OrthogonalPolynomials(2);
% compute the total order index matrix of 'new' by specifying its
% dimension and order are both 2
H=RecursiveTotalOrderIndex(new,2,2);
% compute the hoperbolic index of 'new' by inputting 'H',u,and order
Hyper=HyperbolicIndex(new,H,0.8,2)
```
You will get the following result  
![image](https://user-images.githubusercontent.com/56415387/125637680-275a9cae-8a42-4faa-b265-793642ec0149.png)  


## MultiplyFunction
This function is used for the construction of multi-dimensional collocation matrix. This function multiplies the matrix values according to selected truncation method. The method is more adaptable than using lots of logical operation to directly do the multiplication. Instead, this method is taking the H(total order) or Hyper(Hyperbolic) matrix to do the multiplication accordingly.
### Input
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### Mat  
Matrix of multiplied polynomials
#### IndexM
The index matrix that contains the truncation indices of tensor order, total order, hyperbolic, or other truncation methods

### Output
#### Row
A vector of multiplied polynomials that would be used to construct multidimensional collocation matrix

## TotalOrderMultiDCollocationMatrix
The function computes the collocation matrix for multi-dimensional matrix for the polynomials with a mix of Hermite, Legendre, Laguerre polynomials. The ordering used is the total order (sum of degrees univariate polynomials e.g. 001 002 .. <= order). The function basically call RecursiveTotalOrderIndex to generate the index matrix for total order. Then it calls different collation matrix computation methods for different kinds of polynomials (defined in input "types") for each dimension in x (column of x), and uses MultiplyFunction to mutiply according to the indices generated.
### Input
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### x  
The sample which is multi-demensional
#### types
A cell array that contains string to describe the input types of each column of x. 'H' stands for Hermite polynomials, 'Leg' stands for Legendre polynomials, and 'Lag' stands for Laguerre polynomials.

### Output
#### multiC
The multi-dimensional collocation matrix

### Example
For example, you have three types of polynomials (Hermite, Legendre, and Laguerre) and your x (the sample) is the following:  
![image](https://user-images.githubusercontent.com/56415387/125643183-1fa376f0-b38b-4257-ab38-dc5d227dcbf1.png)

You could execute the following MATLAB code  
```
% construct the x matrix in a way you like
x = 1:5;
x = x(:);
x=[x x x];
% specify the type of polynomials for each column
types={'H','Leg','Lag'};
% create the orthogonal polynomial object and name it 'new'
new = OrthogonalPolynomials(3);
% call the function to compute the collocation matrix
% with the sample and types
multiC=new.TotalOrderMultiDCollocationMatrix(x,types)
```
You will get the following result as your multi-dimensional collocation matrix 
![image](https://user-images.githubusercontent.com/56415387/125643753-f35f1eaa-7e72-4ab3-9161-2177784e178c.png)

## HyperbolicMultiDCollocationMatrix
The function computes the collocation matrix for multi-dimensional matrix for polynomials with a mix of Hermite, Legendre, Laguerre polynomials. The ordering used is the hyperbolic truncation. The function basically call HyperbolicIndex to generate the hyperbolic index matrix. Then it calls different collation matrix computation methods for different kinds of polynomials (defined in input "types") for each dimension in x (column of x), and uses MultiplyFunction to mutiply according to the indices generated.
### Input
#### obj  
The object OthogonalPolynomials that we have created with order as its property.
#### x  
The sample which is multidemensional
#### types
A cell array that contains string to describe the input types of each column of x. 'H' stands for Hermite polynomials, 'Leg' stands for Legendre polynomials, and 'Lag' stands for Laguerre polynomials.

### Output
#### multiC
The multi-dimensional collocation matrix

### Example
For example, you have three types of polynomials (Hermite, Legendre, and Laguerre) and your x (the sample) is the following:  
![image](https://user-images.githubusercontent.com/56415387/125643183-1fa376f0-b38b-4257-ab38-dc5d227dcbf1.png)

You could execute the following MATLAB code  
```
% construct the x matrix in a way you like
x = 1:5;
x = x(:);
x=[x x x];
% specify the type of polynomials for each column
types={'H','Leg','Lag'};
% create the orthogonal polynomial object and name it 'new'
new = OrthogonalPolynomials(3);
% call the function to compute the collocation matrix 
% with the sample and types
multiC=new.HyperbolicMultiDCollocationMatrix(x,types)
```
You will get the following result as your multi-dimensional collocation matrix  
![image](https://user-images.githubusercontent.com/56415387/125644723-c27a49ad-f760-4c1d-a81d-5f8522c3b702.png)

<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
