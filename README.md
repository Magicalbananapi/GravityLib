![GravityLib Banner](https://user-images.githubusercontent.com/56317194/121430473-c0d05980-c93d-11eb-8f18-4b33ecc59bed.png)

- Created for fabric 1.17 (Might backport later)
- Work in progress

---

Adds 6 directional gravity to entities with variable strength.

Directions defaults to Down and includes: Up, Down, North, East, South, and West.

Strength defaults to 1 and acts differently depending if the value is positive, negative, or zero.

Generally, strength values closer to zero are weaker and those further from zero are stronger, while a strength of zero prevents movement.

Negative gravity values act as antigravity and repel entities while keeping their direction intact, and thus an entitiy with an upwards gravity of -1 strength would look like Dinnerbone does.

Also attempts to fix [MC-119369](https://bugs.mojang.com/browse/MC-119369) by making the behavior of falling boats consistent.

---

Future Plans:
- Special gravity effects for swimming and riptide such that swimming in zero gravity unlocks the pitch rotation of the camera.
- Gravity Fields to apply gravity.
