# oh-my-geometry
Cheatsheet for frequently used procedural 2D geometry in p5

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
