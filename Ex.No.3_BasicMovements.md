# Ex.No: 3  Basic movements in Unity 
### DATE:5.03.2025                                                                            
### REGISTER NUMBER : 212222040108
### AIM: 
 To learn the basic movements translation,scaling and rotation of game objects through code.
### Procedure:
1. Setup the Scene
2. Open Unity and create a 3D Scene.
3. Add three objects:Cube → Rename to Object1 (for movement),Sphere → Rename to Object2 (for rotation).Capsule → Rename to Object3 (for scaling).
4. Add the Script,Create a C# Script → Name it TransformOperations.cs.
5. Write the code for translation,scaling and rotation,save and close the script
6. Save the script
7. Select any empty GameObject (or create one: GameObject → Create Empty).
8. Attach the TransformOperations script to it.
9. In the Inspector, assign Object1 → Drag the Cube,Object2 → Drag the Sphere.Object3 → Drag the Capsule.
10. Run the Scene Press Play ▶️ in Unity
11. Stop the program.
### Program 
```
using UnityEngine;
public class TransformOperations : MonoBehaviour
{
    public Transform object1; // Object for translation
    public Transform object2; // Object for rotation
    public Transform object3; // Object for scaling

    public float moveSpeed = 2f;  // Speed of translation
    public float rotateSpeed = 50f; // Speed of rotation
    public float scaleSpeed = 0.5f; // Speed of scaling

    void Update()
    {
        // Translate (Move) object1 along the X-axis- Time.deltaTime to make movement smooth across all frame rates
        if (object1 != null)
        {
            object1.position += Vector3.right * moveSpeed * Time.deltaTime;
        }

        // Rotate object2 around the Y-axis
        if (object2 != null)
        {
            object2.Rotate(Vector3.up * rotateSpeed * Time.deltaTime);
        }

        // Scale object3 up and down
        if (object3 != null)
        {
            float scaleChange = Mathf.PingPong(Time.time * scaleSpeed, 1f) + 0.5f; // generates a value that moves back and forth between 0 and length
            object3.localScale = new Vector3(scaleChange, scaleChange, scaleChange);
        }
    }
}
```
### Output:
![Screenshot 2025-03-05 155259](https://github.com/user-attachments/assets/ca3513fc-b57b-4a49-a3d3-e24c0330cc0d)
![Screenshot 2025-03-05 155504](https://github.com/user-attachments/assets/ddab2996-a0f6-48ed-8d07-4c73eaf90149)

### Result:
Thus the basic movement is learned through scripting


