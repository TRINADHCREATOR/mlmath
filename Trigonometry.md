# Trigonometry and Vectors

## What Is Trigonometry?

Say you're standing at one corner of a room and you want to describe exactly where a lamp is on the other side, without walking over and measuring it directly. You could say "it's 5 meters away, at this angle from where I'm facing." That single idea, using an angle and a distance to pin down a location, is the whole point of trigonometry.

**Trigonometry** is the branch of math that deals with angles and the relationships between the sides of a triangle. In AI, trigonometry helps calculate distances and directions, especially when dealing with vectors and positions.

## Right-Angle Triangles

Picture a ladder leaning against a wall. The wall is straight up, the ground is flat, and the ladder is the slanted part connecting them. That's a right-angle triangle, and every part of it has a name depending on which angle you're looking from.

The foundation of trigonometry is the **right-angle triangle**. A right-angle triangle has:

1. One **right angle** (90°).
2. Two smaller angles.
3. Three sides:
   - **Hypotenuse**: The longest side (opposite the 90° angle). In the ladder example, this is the ladder itself.
   - **Opposite**: The side opposite the angle you're focusing on.
   - **Adjacent**: The side next to the angle you're focusing on (but not the hypotenuse).

```txt
        |\
        | \
Opposite|  \ Hypotenuse
        |   \
        |____\
        Adjacent
```

## The Three Basic Trigonometric Ratios

Once you've labeled the three sides, trigonometry gives you a way to relate any two of them using an angle. These relationships don't change no matter how big or small the triangle is, only the angle matters. That's what makes them useful: give the ratio an angle, and it gives you back a fixed number you can build calculations on.

Trigonometry is all about the **ratios** of the sides of a triangle. These are the main ones you need:

1. **Sine (sin)**:

   ```txt
   sin(θ) = Opposite / Hypotenuse
   ```

2. **Cosine (cos)**:

   ```txt
   cos(θ) = Adjacent / Hypotenuse
   ```

3. **Tangent (tan)**:

   ```txt
   tan(θ) = Opposite / Adjacent
   ```

## Worked Example: Self-Driving Car and an Obstacle

Let's revisit the car-obstacle example:

- The car is at position (0, 0).
- The obstacle is 5 meters away at a 45° angle.
- We want to calculate the vector components [x, y] (horizontal and vertical distances).

### Step 1: Write Down What We Know

- Distance (r) = 5 (hypotenuse).
- Angle (θ) = 45°.
- We need:
  - x = r · cos(θ) (adjacent side).
  - y = r · sin(θ) (opposite side).

### Step 2: Apply the Formulas

From trigonometry:

- cos(45°) = sin(45°) = √2/2 ≈ 0.707.

Calculate:

```txt
x = 5 · cos(45°) = 5 · 0.707 = 3.535
y = 5 · sin(45°) = 5 · 0.707 = 3.535
```

**Result:** the vector is `[3.5, 3.5]`.

## What Is a Vector?

Now think about that same lamp-in-the-room problem again. An angle and a distance describe where something is, but what if you want to describe *movement*, like an arrow pointing from you toward the lamp? That arrow has two properties: how long it is, and which way it's pointing. That's exactly what a vector captures.

A **vector** is a mathematical object that represents both:

- **Magnitude**: How "big" or "strong" something is.
- **Direction**: Which way it's pointing.

It's like an arrow: the length of the arrow is the magnitude, and the way it's pointing is the direction.

A vector is typically written as a list of numbers:

```txt
v = [vx, vy]
```

where:

- vx: the horizontal component (x-axis).
- vy: the vertical component (y-axis).

In 3D, it extends to:

```txt
v = [vx, vy, vz]
```

where vz is the depth or height component.

## Magnitude of a Vector

If a vector is an arrow, its magnitude is just its length, and you can measure that length the same way you'd measure the diagonal side of a right-angle triangle: with the Pythagorean theorem. The vector's horizontal and vertical components form the two shorter sides, and the arrow itself is the hypotenuse.

The **magnitude** (or length) of a vector is calculated using the Pythagorean theorem:

```txt
‖v‖ = √(vx² + vy²)
```

**Example:** if v = [3, 4], then:

```txt
‖v‖ = √(3² + 4²) = √(9 + 16) = 5
```

**AI Use Case:** magnitude tells us the strength or size of a vector. For example, the magnitude of a vector can represent the **distance** between two data points.

## Direction of a Vector

Length alone doesn't tell you which way the arrow is pointing, two vectors can be the same length but point in completely different directions. To find the direction, think about how far the arrow "rises" compared to how far it "runs," the exact same rise-over-run idea from the ladder-against-the-wall picture earlier. That ratio is a tangent, and running it backward with the inverse tangent hands you the actual angle.

In the case of a vector, the components vx and vy correspond to:

- vx: the **adjacent side** (horizontal distance along the x-axis).
- vy: the **opposite side** (vertical distance along the y-axis).

So the tangent ratio for a vector v = [vx, vy] is:

```txt
tan(θ) = Opposite / Adjacent = vy / vx
```

This means the angle θ depends on how much the vector "rises" (vy) compared to how much it "runs" (vx).

To actually find θ, we need to undo the tangent. We use the **inverse tangent function** (tan⁻¹), also called **arctan**:

```txt
θ = tan⁻¹(vy / vx)
```

**Example:** let's calculate the direction of the vector v = [3, 4]:

```txt
tan(θ) = vy / vx = 4 / 3

θ = tan⁻¹(4/3) = tan⁻¹(1.333) ≈ 53.13°
```

### AI Use Case: Self-Driving Car

Imagine a self-driving car needs to move in a certain direction. The vector v = [3, 4] represents its movement:

- 3 m forward along the x-axis.
- 4 m upward along the y-axis.

The car calculates:

- Magnitude: ‖v‖ = √(3² + 4²) = 5 m.
- Direction: θ = 53.13°, so the car knows to move northeast.

The angle (θ) tells us the **direction of the vector** relative to the x-axis, which is exactly how systems like robots and self-driving cars decide where to move based on a vector.

## Vector Operations: Addition

Two arrows can be combined into one by simply adding up how far they each go left-right and up-down. That's all vector addition is: add the x's together, add the y's together.

To add two vectors, add their corresponding components:

```txt
u + v = [ux + vx, uy + vy]
```

**Example:**

```txt
u = [1, 2], v = [3, 4]
u + v = [1 + 3, 2 + 4] = [4, 6]
```

**AI Use Case:** vector addition is used in **physics simulations** or combining multiple input signals in machine learning.

## Summary

- **Trigonometry** relates the angles and sides of a right-angle triangle using sin, cos, and tan.
- The three sides of a right-angle triangle are the **hypotenuse**, **opposite**, and **adjacent**.
- A **vector** represents both **magnitude** (length) and **direction** (which way it points).
- **Magnitude** is found with the Pythagorean theorem: ‖v‖ = √(vx² + vy²).
- **Direction** is found with the inverse tangent: θ = tan⁻¹(vy / vx).
- **Vector addition** combines two vectors by adding their matching components.
- In AI, these tools let systems like robots and self-driving cars calculate distances and figure out which way to move.
