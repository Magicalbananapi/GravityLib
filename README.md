![GravityLib Banner](https://user-images.githubusercontent.com/56317194/121430473-c0d05980-c93d-11eb-8f18-4b33ecc59bed.png)

- Created for fabric 1.17 (Might backport later)
- Work in progress

---

## Overview

Adds 6 directional gravity to entities with variable strength.

Directions defaults to Down and includes: Up, Down, North, East, South, and West.

Strength defaults to 1 and acts differently depending if the value is positive, negative, or zero.

Generally, strength values closer to zero are weaker and those further from zero are stronger, while a strength of zero prevents movement.

Negative gravity values act as antigravity and repel entities while keeping their direction intact, and thus an entitiy with an upwards gravity of -1 strength would look like Dinnerbone does.

Also attempts to fix [MC-119369](https://bugs.mojang.com/browse/MC-119369) by making the behavior of falling boats consistent.

---

## Future Plans:
- Special gravity effects for swimming and riptide such that swimming in zero gravity unlocks the pitch rotation of the camera.
- Gravity Fields to apply gravity.

---

## Extra Information:

### Command Syntax:
/gravity \<add, divide, get, multiply, reset, rotate, set, subtract> \<target> ...

/gravity \<add, divide, get, multiply, reset, rotate, set, subtract> \<target> [\<type>] ...

*suggestions will be organized in alphabetical order in game, and I have no idea how to change this

\
/gravity get \<target> [\<attribute>]

/gravity get \<target> [\<type>] [\<attribute>]

\
/gravity reset \<target> [\<attribute>]

/gravity reset \<target> [\<type>] [\<attribute>]

\
/gravity rotate \<target> \<rotation> [\<time>]

/gravity rotate \<target> \<type> <rotation> [\<time>]

\
/gravity set \<target> \<direction> [\<strength>] [\<time>]

/gravity set \<target> \<attribute> (\<direction>|\<strength>|\<time>)

/gravity set \<target> \<type> \<direction> [\<strength>] [\<time>]

/gravity set \<target> \<type> \<attribute> (\<direction>|\<strength>|\<time>)

### Command Arguments:
  
\<target> = (entity \<target>|block \<targetPos>)

\<type> = (base, target, motion, drops, projectiles, special)

\<attribute> = (direction, strength, time)

\<rotation> = (forward, backwards, left, right)

\<direction> = (UP, DOWN, NORTH, EAST, SOUTH, WEST, NONE)

---
### Gravity Types:
base - all other types combined

target - the gravity used for rendering, hitbox rotation, camera rotation, eye height, aim, etc.

motion - the gravity used for movement of the entity/block

drops - the gravity of items dropped by the entity/block

projectiles - the gravity of projectiles shot by the entity/block

special - the gravity of other entities in special cases where an entity/block's gravity is tied to another's
(entities with the same gravity as the nearest player or the opposite gravity of a random player for example)

---
### Special Cases:
/gravity reset \<target> time - refreshes the remaining time of the currently applied gravity back to it's maximum

In general, block entities will only be affected by direction, as such strength and time will not be an option if a coordinate is chosen as the target.
