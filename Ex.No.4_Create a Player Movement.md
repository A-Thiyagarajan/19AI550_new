# Ex.No: 4  Create a player Movement Script in unity 
### DATE:                                                                            
### REGISTER NUMBER : 212222240110
### AIM: 
To write a program to create a player movement in unity.
### Algorithm:
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project,Name the project (e.g., PlayerMovement).
2. Create the Moving Object
   In the Hierarchy, right-click → 3D Object → Capsule (or Sphere).
   Rename it to Player 
4. Adding the Player Movement Behavior Script
   Create the Script-In the Project Window, go to the Assets folder.
   Right-click → Create → C# Script.
5. Write a script for player behavior and save it
6. Attach the Script
   Select player in the Hierarchy - Drag & Drop the playerBehavior script onto the Inspector Panel.
7. Run the game 
8. Stop the program
    
### Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Player_movement : MonoBehaviour
{
    public float speed = 5.0f;

void Update()
{
    float xdir = Input.GetAxis("Horizontal") * speed * Time.deltaTime;
    float zdir = Input.GetAxis("Vertical") * speed * Time.deltaTime;

    transform.Translate(xdir, 0, zdir);
}
}

```
### Output:

![41](https://github.com/user-attachments/assets/eaa695c2-16eb-4fbf-a4be-0a7fac41be1b)

![42](https://github.com/user-attachments/assets/fd4fcb60-2da3-416e-946c-c43d366d42ae)

![43](https://github.com/user-attachments/assets/98453693-1187-40c0-ad84-a604332389fb)


![44](https://github.com/user-attachments/assets/b13eabc2-5dd7-49d2-9a1e-f1501a9c54ac)




### Result:
Thus the simple movement behavior was implemented successfully.
