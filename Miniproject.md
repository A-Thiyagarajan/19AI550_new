# Ex.No: 10  Implementation of 2D/3D game - Escape from the Falling Object Game
### DATE:                                                                            
### REGISTER NUMBER : 212222240110
### AIM: 
To develop a Escape from the Falling Object Game in Unity 
### Algorithm:
```
1. Create a new Unity project.
2. Add a Player GameObject to the scene.
3. Add a FallingObject GameObject to the scene.
4. Attach the PlayerController script to the Player GameObject.
5. Attach the FallingObject script to the FallingObject GameObject.
6. Set the Player GameObject's tag and add a Collider2D (if needed).
7. Set the Ground GameObject with tag "Ground" and add a Collider2D with IsTrigger enabled.
8. In the PlayerController script, read horizontal input and move the player each frame (in Update).
9. In the FallingObject script, move the object downwards each frame and check for collision with the ground using OnTriggerEnter2D.
10. If the falling object collides with the ground, destroy the player object.
```
### Program:
#### FallingObject.cs
```
using UnityEngine;

public class FallingObject : MonoBehaviour
{
    public float fallSpeed = 1f;

    void Update()
    {
        transform.position += new Vector3(0, -fallSpeed * Time.deltaTime, 0);
    }

    void OnTriggerEnter2D(Collider2D other)
    {
        if (other.gameObject.CompareTag("Ground"))
        {
            Destroy(gameObject); // Destroy the object when it hits the ground
        }
    }
}

```
#### PlayerController.cs
```

using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 5f;

    void Update()
    {
        float move = Input.GetAxis("Horizontal"); // Get left/right key input
        transform.position += new Vector3(move * speed * Time.deltaTime, 0, 0);
    }
}

```

### Output:
![WhatsApp Image 2025-05-20 at 21 15 36_54544c74](https://github.com/user-attachments/assets/f0ae77b1-f643-41ef-a604-3b00b31f9b10)

![WhatsApp Image 2025-05-20 at 21 16 29_6ff37835](https://github.com/user-attachments/assets/6213cc1e-28f4-49bf-a996-a848118888ce)

![WhatsApp Image 2025-05-20 at 21 17 22_b6834eb3](https://github.com/user-attachments/assets/1495f1f2-34bd-4138-9d7a-fbe287956aea)



### Result:
Thus the game Escape from the Falling Object Game was developed using Unity.
