# Ex.No: 7  Implementation of Simple Pathfinding with Obstacles
### DATE:                                                                            
### REGISTER NUMBER : 212222240110
### AIM: 
To write a program to pathfinding using AI navigation 
### Algorithm:
```
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project,Name the project (e.g., Pathfinding).
2. Set Up the Scene by Create the Ground (Plane or Terrain)
  Go to: GameObject → 3D Object → Plane and Rename: "Ground"  Scale it: (10, 1, 10) (or adjust as needed)
3. Add Obstacles (Cubes or Walls)
  Go to: GameObject → 3D Object → Cube  Scale it: (3, 3, 1) (for a wall-like structure)
  Position it: Place it anywhere to block AI movement Rename it: "Obstacle"  Duplicate: Ctrl + D to create multiple obstacles ,tag the obstacke with same name.
4.Bake the NavMesh
Go to: Window → AI → Navigation , Select Ground: Click on your Ground object ,
In Navigation Window: Check ✅ "Navigation Static"  or Add component Navigation surface and Bake
5.Create the AI Character and Attach navMesh Agent
Go to: GameObject → 3D Object → Capsule ,  Rename: "AICharacter" , Scale: (1, 2, 1)
Go to: Inspector → Add Component → NavMeshAgent Adjust Settings: Speed: 3.5 Stopping Distance: 1  Obstacle Avoidance: High
6.Create the Script "AIPathFinder" (Go to: Assets → Right Click → Create → C# Script and  Rename it: "AIPathfinder"
7.Attach the Script"AIPathFinder" code by Drag & Drop the AIPathfinder.cs onto the AICharacter 
8.Assign the Target:Create a Target: GameObject → 3D Object → Sphere, Rename it: "Target",
 In AICharacter Inspector → AIPathfinder → Drag the Target Sphere into the "target" field.
9.Add NavMeshObstacle
Select an Obstacle (Cube)
Go to: Inspector → Add Component → NavMeshObstacle and Check: ✅ "Carve"
10.Move the Obstacle with Code ( attach it with Obstacle) 
11. Run the program
```  
### Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.AI;
using static UnityEngine.GraphicsBuffer;

public class AIPathfinder : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target; // Assign the target in the Inspector
    private NavMeshAgent agent;
    void Start()
    {
        agent = GetComponent<NavMeshAgent>(); // Get the NavMeshAgent
    }

    // Update is called once per frame
    void Update()
    {
        agent.SetDestination(target.position);
    }
}
#Moving Obstacle
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Moving : MonoBehaviour
{
    // Start is called before the first frame update
    public float moveDistance = 3f;
    public float moveSpeed = 2f;
    private Vector3 startPos;
void Start()
    {
    startPos = transform.position;
    }

    // Update is called once per frame
    void Update()
    {
       float movement=Random.Range(-moveDistance / 14, moveDistance / 14);
        transform.position = startPos + new Vector3(movement, 0, 0);
    }
}
```
For smooth movement(optional)  -> use  
float movement = Mathf.PingPong(Time.time * moveSpeed, moveDistance) - moveDistance / 2;
transform.position = startPos + new Vector3(movement, 0, 0);
### Output:
![Screenshot 2025-04-09 151152](https://github.com/user-attachments/assets/491ee3e3-f9c2-4b7e-8cad-b1571770ca43)

![Screenshot 2025-04-09 151251](https://github.com/user-attachments/assets/f7a7657f-bb75-4656-af9f-149d5cf5c71b)

![Screenshot 2025-04-09 151352](https://github.com/user-attachments/assets/059990c2-fd9e-450c-aa1d-f9c1512ca625) 

### Result:
Thus the simple path finding  behavior was implemented using AI navigation successfully.
