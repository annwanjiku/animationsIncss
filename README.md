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
CSS provides various time-related properties that control how elements transition between states or animate over time.

### 1. Transition Delay (`transition-delay`)
Delays the start of a transition.

```css
.box {
    transition: background-color 1s ease-in-out;
    transition-delay: 0.5s;
}
```

### 2. Transition Duration (`transition-duration`)
Defines how long a transition takes.

```css
.box {
    transition: transform 2s;
}
```

### 3. Animation Delay (`animation-delay`)
Delays the start of an animation.

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

### 4. Animation Duration (`animation-duration`)
Controls how long an animation takes.

```css
@keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
}

.box {
    animation: bounce 1.5s;
}
```

### 5. Animation Direction (`animation-direction`)
Defines the playback direction of an animation.

```css
.box {
    animation: slide 2s alternate infinite;
}
```

### 6. Animation Timing Function (`animation-timing-function`)
Controls speed variation of an animation.

```css
.box {
    transition: transform 2s ease-in-out;
}
```

### 7. Animation Iteration Count (`animation-iteration-count`)
Specifies how many times an animation repeats.

```css
.box {
    animation: bounce 2s infinite;
}
```

### 8. Animation Fill Mode (`animation-fill-mode`)
Defines how an animation behaves before and after execution.

```css
.box {
    animation: fadeIn 3s forwards;
}
```

---

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

---

### Final Example
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
