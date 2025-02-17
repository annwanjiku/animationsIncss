## CSS Transformations
CSS transformations allow elements to be modified in a two-dimensional (2D) or three-dimensional (3D) space. The `transform` property is used to apply these changes. Transformations include **translation, rotation, scaling, skewing, and matrix transformations**.

### 1. Two-Dimensional (2D) Transformations
2D transformations operate on the X and Y axes.

- **Translate:** Moves an element without rotating or resizing it.
- **Rotate:** Rotates an element around a fixed point.
- **Scale:** Increases or decreases the size of an element.
- **Skew:** Tilts an element along the X or Y axis.
- **Matrix:** A more complex transformation that combines multiple transformations.

### 2. Three-Dimensional (3D) Transformations
3D transformations add depth by incorporating the Z axis.

- **translate3d(x, y, z):** Moves an element in 3D space.
- **rotateX(deg), rotateY(deg), rotateZ(deg):** Rotates an element along different axes.
- **scale3d(x, y, z):** Resizes an element along all three axes.
- **perspective(n):** Defines depth perception for 3D elements.

### 3. Translation (`translate`)
Moves an element from its original position along the X, Y, or Z axes.

```css
.box {
    transform: translate(50px, 20px);
}
```
This moves the element **50px to the right** and **20px down**.

### 4. Rotation (`rotate`)
Rotates an element around a fixed point.

```css
.box {
    transform: rotate(45deg);
}
```
This rotates the element **45 degrees clockwise**.

### 5. Scaling (`scale`)
Resizes an element by stretching or shrinking it.

```css
.box {
    transform: scale(1.5, 1.2);
}
```
This scales the width by **1.5 times** and the height by **1.2 times**.

### 6. Skewing (`skew`)
Distorts an element along the X and/or Y axis.

```css
.box {
    transform: skew(20deg, 10deg);
}
```
This skews the element **20 degrees along the X-axis** and **10 degrees along the Y-axis**.

### 7. Combining Transformations
Multiple transformations can be applied at once.

```css
.box {
    transform: translate(50px, 30px) rotate(45deg) scale(1.2);
}
```

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
This **changes color from blue to red**, **waits 1 second before starting**, and **repeats infinitely, reversing each time**.
