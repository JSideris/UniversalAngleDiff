# Universal 2D Angle Subtraction

Use these to subtract angles in degrees (to use radians, just change the 360° to 2π). There are two methods, both will work for any angles, even ones not bound between 0 and 360. 

The absolute method will return the absolute unsigned different between the angles between 0° and 180° (180° is the farstest apart angles can be).

The Relative (signed) method will return a value between -180° and 180° where the magnitude of the value is absolute difference and the sign indicates whether the shortest angle from b to a is positive or negative. For instance, if a is 15 and b is 25, the result will be -10.

To subtract 3D angles using this method, find the 2D values for the angles on their common plane.

Please contact me if you have any suggestions on improvements.

## Implementations

### Python

**Absolute**
```python
def absAngleSub(a, b):
	d = a - b
	if d < 0: d = -d
	d = d % 360
	if d < 180: return d
	else return 360 - d
```
**Relative (Signed)**
```python
def relAngleSub(a, b):
	if a < 0: 
		a = -(-a % 360)
		if a <= -180: a = 360 + a
	else: 
		a = a % 360
		if a > 180: a = -360 + a
	if b < 0: 
		b = -(-b % 360)
		if b <= -180: b = 360 + b
	else: 
		b = b % 360
		if b > 180: b = -360 + b
	return a - b
```

### JavaScript

**Absolute**
```JavaScript
function absAngleSub(a, b){
	var d = a - b;
	if(d < 0) d = -d;
	d = d % 360;
	if(d < 180) return d;
	else return 360 - d;
}
```
**Relative (Signed)**
```JavaScript
function relAngleSub(a, b){
	if (a < 0){
		a = -(-a % 360);
		if(a <= -180) a = 360 + a;
	}
	else {
		a = a % 360;
		if(a > 180) a = -360 + a;
	}
	if(b < 0){
		b = -(-b % 360);
		if(b <= -180) b = 360 + b;
	}
	else{
		b = b % 360;
		if(b > 180) b = -360 + b;
	}
	return a - b;
}
```
### C\#

**Absolute**
```C#
public double AbsAngleSub(double a, double b){
	var d = a - b;
	if(d < 0d) d = -d;
	d = d % 360d;
	if(d < 180d) return d;
	else return 360d - d;
}
```
**Relative (Signed)**
```C#
public double RelAngleSub(double a, double b){
	if (a < 0d){
		a = -(-a % 360d);
		if(a <= -180d) a = 360d + a;
	}
	else {
		a = a % 360d;
		if(a > 180d) a = -360d + a;
	}
	if(b < 0d){
		b = -(-b % 360d);
		if(b <= -180d) b = 360d + b;
	}
	else{
		b = b % 360d;
		if(b > 180d) b = -360d + b;
	}
	return a - b;
}
```
