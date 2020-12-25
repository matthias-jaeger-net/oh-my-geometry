# oh-my-geometry
Cheatsheet for frequently used procedural 2D geometry in p5

Get the angle between two vectors
```javascript
// The dot product divided by the magnitude product is the cosine of the angle
// https://onlinemschool.com/math/library/vector/angl/
function getAngle(v1, v2) {
  const dotProduct = v2.dot(v1);
  const magProduct = v1.mag() * v2.mag();
  return acos(dotProduct / magProduct);
}
```

Get the midpoint of a line segment, the complicated way
```javascript
function midpoint(x1, y1, x2, y2) {
  let v1 = createVector(x1, y1);
  let v2 = createVector(x2, y2);
  let direction = v2.sub(v1);
  let magnitude = direction.mag();
  direction.normalize();
  direction.mult(magnitude * 0.5);
  const x = x1 + direction.x;
  const y = y1 + direction.y;
  return createVector(x, y);
}
```
Get a point on a line segement and pass the length of the offset
```javascript
function segpoint(x1, y1, x2, y2, len) {
  let v1 = createVector(x1, y1);
  let v2 = createVector(x2, y2);
  let direction = v2.sub(v1);
  let magnitude = direction.mag();
  direction.normalize();
  direction.mult(len);
  const x = x1 + direction.x;
  const y = y1 + direction.y;
  return createVector(x, y);
}
```
