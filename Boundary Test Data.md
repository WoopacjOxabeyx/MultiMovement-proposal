Logic point A: Player Position

| Boundary Input | Test Data | Expected Outcome |
| :---- | :---- | :---- |
| Falling towards floor | Player position: (0, 10, 0\) | Player should hit floor and lose all vertical momentum |
| Inside of the ground | Player position: (0, \-2, 0\) | Player should gradually be pushed back upwards |
| Outside of the map | Player position: (0, \-25, 0\) | Player should be killed instantly |

I should watch out for the instakill barrier being too close to the map

Logic point B: Weapons

| Boundary Input | Test Data | Expected Outcome |
| :---- | :---- | :---- |
| Switching to a weapon while still switching to a different one | While in the equip animation, switch to another weapon | The new weapon switch should overwrite the current weapon switch |
| Switching the weapon while firing | Pressing fire and switch on the same frame | The bullet should still fire and then switch the weapon |
| Melee hit goes slightly off hitbox | Melee hit barely misses enemy | The melee swing should still count as a hit |

The melee hit going slightly off hitbox is the most important boundary because of how hard it is to land a melee strike

Logic point C: Enemies

| Boundary Input | Test Data | Expected Outcome |
| :---- | :---- | :---- |
| Negative enemies | Enemy count \= \-1 | Change the enemy count back to 0 |
| Too much enemies | Game tries to add another enemy when RAM usage is too high to handle another | Free up space (despawn dead bodies, decals, etc.) , and when the space is allocated, spawn the enemy |
| 0 enemies | Player kills the last enemy in room | Open the door that lets the player move on to the next room |

Having too much enemies is going to be the riskiest boundary because if it is too lenient, then the game will crash and if it is too strict, the game quality will not be good