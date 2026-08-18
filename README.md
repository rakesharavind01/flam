# FLAM Assignment - Java Solution

## Supplied resource
`UVCE_BTech_Flam_Resource.csv`

The CSV contains 1500 points with columns `x,y`.

## Model

x = t*cos(theta) - exp(M*|t|)*sin(0.3t)*sin(theta) + X

y = 42 + t*sin(theta) + exp(M*|t|)*sin(0.3t)*cos(theta)

Java uses radians internally for trigonometric functions.

## Parameter ranges

- theta: 0 < theta < 50 degrees
- M: -0.05 < M < 0.05
- X: 0 < X < 100
- t: 6 < t < 60

## Result for this CSV

- theta = 30 degrees
- M = 0.03
- X = 55

The supplied resource is generated from these clean parameter values.

## How to run

From the project folder:

```bash
javac src/Main.java
java -cp src Main UVCE_BTech_Flam_Resource.csv
```

Or:

```bash
cd src
javac Main.java
java Main ../UVCE_BTech_Flam_Resource.csv
```

## Desmos expression

Use a Desmos variable `a` for theta (degrees):

```text
(t*cos(a/180*3.141592653589793)-exp(M*t)*sin(0.3*t)*sin(a/180*3.141592653589793)+X,42+t*sin(a/180*3.141592653589793)+exp(M*t)*sin(0.3*t)*cos(a/180*3.141592653589793))
```

Set:

- a = 30, range 0 to 50
- M = 0.03, range -0.05 to 0.05
- X = 55, range 0 to 100
- t = 6 to 60

## Notes

Because the assignment uses |t| and the required t interval is positive (6 < t < 60), `|t| = t` on the allowed interval. Therefore the Java/Desmos expression can use `exp(M*t)` for this dataset.

