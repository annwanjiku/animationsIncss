## CSS Transformations
CSS transformations allow elements to be modified in a two-dimensional (2D) or three-dimensional (3D) space. The `transform` property is used to apply these changes. Transformations include translation, rotation, scaling, skewing, and matrix transformations.

## 1. Translation (`translate`)
The `translate` function moves an element from its original position along the X, Y, or Z axes.

- `translateX(px or %)`: Moves the element horizontally.
- `translateY(px or %)`: Moves the element vertically.
- `translate(x, y)`: Moves the element in both directions.

### Example:
```css
.box {
    transform: translate(50px, 20px);
}
```
This moves the element 50 pixels to the right and 20 pixels down.

## 2. Rotation (`rotate`)
The `rotate` function rotates an element around a fixed point (default is the center).

- `rotate(angle)`: Rotates the element in 2D space (positive values rotate clockwise).
- `rotateX(angle)`: Rotates around the X-axis.
- `rotateY(angle)`: Rotates around the Y-axis.
- `rotateZ(angle)`: Same as `rotate(angle)` but explicitly for 3D.

### Example:
```css
.box {
    transform: rotate(45deg);
}
```
This rotates the element 45 degrees clockwise.

## 3. Scaling (`scale`)
The `scale` function resizes an element by stretching or shrinking it.

- `scaleX(value)`: Scales the width.
- `scaleY(value)`: Scales the height.
- `scale(valueX, valueY)`: Scales both width and height.

### Example:
```css
.box {
    transform: scale(1.5, 1.2);
}
```
This increases the width by 1.5 times and the height by 1.2 times.

## 4. Skewing (`skew`)
The `skew` function distorts an element along the X and/or Y axis.

- `skewX(angle)`: Skews only the X-axis.
- `skewY(angle)`: Skews only the Y-axis.
- `skew(angleX, angleY)`: Skews both axes.

### Example:
```css
.box {
    transform: skew(20deg, 10deg);
}
```
This skews the element 20 degrees along the X-axis (horizontally) and 10 degrees along the Y-axis (vertically).


## 5. 3D Transformations
For 3D transformations, use `perspective` to create depth.

### Example:
```css
.box {
    transform: rotateY(60deg);
    perspective: 500px;
}
```
This tilts the element along the Y-axis, making it appear to rotate in 3D.

## 6. Combining Transformations
Multiple transformations can be combined.

### Example:
```css
.box {
    transform: translate(50px, 30px) rotate(45deg) scale(1.2);
}
```
This Moves the element (50px right, 30px down) ,Rotates it (45 degrees) and Scales it (1.2 times its original size).

## Final Example 
```css
.box {
    width: 100px;
    height: 100px;
    background-color: lightblue;
    transform: rotate(30deg) skewX(20deg) scale(1.5);
    transition: transform 0.5s ease-in-out;
}

.box:hover {
    transform: translate(20px, 20px) rotate(-30deg);
}
```
The element is initially rotated, skewed, and scaled.  
On hover, it moves along the x and y axis and rotates in the anticlockwise direction.

---

## CSS Transitions and Animations
CSS provides various time-related properties that control how elements transition between states or animate over time. Below is a discussion of key time-related factors, including delays, durations, directions, and timing functions.

## 1. Transition Delay (`transition-delay`)
- Specifies the waiting time before a transition starts.
- Measured in seconds (`s`) or milliseconds (`ms`).
- Can be positive (delays start) or negative (starts midway).

### Example:
```css
.box {
    transition: background-color 1s ease-in-out;
    transition-delay: 0.5s;
}

.box:hover {
    background-color: red;
}
```
Here, the color change starts 0.5 seconds after hovering.

## 2. Transition Duration (`transition-duration`)
- Determines how long a transition takes to complete.
- Defined in seconds (`s`) or milliseconds (`ms`).

### Example:
```css
.box {
    transition: transform 2s;
}

.box:hover {
    transform: scale(1.5);
}
```
This scales the element over 2 seconds when hovered.

## 3. Animation Delay (`animation-delay`)
- Works like `transition-delay` but for CSS animations.
- Defines the time before an animation starts.

### Example:
```css
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

.box {
    animation: fadeIn 3s;
    animation-delay: 1s;
}
```
This fades in after a 1-second delay.

## 4. Animation Duration (`animation-duration`)
- Controls how long an animation takes from start to end.
- Without it, the animation happens instantly.

### Example:
```css
@keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
}

.box {
    animation: bounce 1.5s;
}
```
This makes the element bounce over 1.5 seconds.

## 5. Animation Direction (`animation-direction`)
- Defines the playback direction of an animation:
  - `normal` → Default (plays forward).
  - `reverse` → Plays backward.
  - `alternate` → Forwards, then backwards.
  - `alternate-reverse` → Backwards, then forwards.

### Example:
```css
@keyframes slide {
    from { transform: translateX(0); }
    to { transform: translateX(100px); }
}

.box {
    animation: slide 2s alternate infinite;
}
```
The element moves right, then back left repeatedly.

## 6. Animation Timing Function (`animation-timing-function`)
- Controls speed variation of an animation or transition.
- Common values:
  - `ease` → Starts slow, speeds up, then slows down (default).
  - `ease-in` → Starts slow then speeds up.
  - `ease-out` → Starts fast then slows down.
  - `ease-in-out` → Starts and ends slow.
  - `linear` → Constant speed.

### Example:
```css
.box {
    transition: transform 2s ease-in-out;
}
```
The transformation gradually accelerates and decelerates.

## 7. Animation Iteration Count (`animation-iteration-count`)
- Specifies how many times an animation repeats.
- Can be a number or `infinite`.

### Example:
```css
.box {
    animation: bounce 2s infinite;
}
```
This makes the bounce repeat forever.

## 8. Animation Fill Mode (`animation-fill-mode`)
- Defines how an animation behaves before and after execution:
  - `none` → Default (no effect before/after animation).
  - `forwards` → Keeps final state after animation ends.
  - `backwards` → Applies starting styles before animation starts.
  - `both` → Combines forwards and backwards.

### Example:
```css
.box {
    animation: fadeIn 3s forwards;
}
```
This keeps the element fully visible after fading in.

## Summary Table
| Property | Effect |
|----------|--------|
| `transition-delay` | Delays transition by a specified time. |
| `transition-duration` | Defines how long a transition takes. |
| `animation-delay` | Delays animation start. |
| `animation-duration` | Sets animation length. |
| `animation-direction` | Controls playback direction. |
| `animation-timing-function` | Adjusts speed variations. |
| `animation-iteration-count` | Defines repeat count. |
| `animation-fill-mode` | Controls state before/after animation. |

## Final Example
```css
@keyframes colorChange {
    0% { background-color: blue; }
    100% { background-color: red; }
}

.box {
    width: 100px;
    height: 100px;
    animation: colorChange 2s ease-in-out infinite;
    animation-delay: 1s;
    animation-direction: alternate;
}
```
This changes color from blue to red,each complete cycle of the animation takes 2 seconds,animation starts slowly and ends slowly repeating infinitely,animation waits 1 second before starting,reversing each time.

[**Examples**](https://annwanjiku.github.io/animations_in_css/)
