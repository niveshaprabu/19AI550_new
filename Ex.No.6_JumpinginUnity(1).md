# Experiment 6: Implementing Jumping Behavior in Unity 
### DATE:   
### REGISTER NUMBER : 212222040108
### AIM: 
To implement a jumping behavior for a player-controlled character in Unity using Rigidbody physics and user input, where pressing the spacebar while in the air causes the player to move down. 
### Algorithm:
```
1. **Create a New Unity Project**  
   - Open **Unity Hub** → Click **New Project**  
   - Select **3D Template** → Name the project **JumpingBehavior** → Click **Create**  

2. **Set Up the Scene**  
   - **Create Ground:**  
     - Go to **GameObject → 3D Object → Plane**  
     - Rename it `"Ground"`  
     - Scale it to **(10,1,10)** (or as needed)  
     - Set **Position** to `(0, 0, 0)`  

3. **Create the Player Object**  
   - **Create a Capsule to Represent the Player:**  
     - Go to **GameObject → 3D Object → Capsule**  
     - Rename it `"Player"`  
     - Scale it to **(1,2,1)** (default is fine)  
     - Set **Position** to `(0, 1, 0)`  

4. **Add Rigidbody to the Player**  
   - Select **Player**  
   - Go to **Inspector → Add Component → Rigidbody**  
   - Set the **Constraints**:  
     - Freeze **Rotation X**, **Rotation Z** (to prevent falling over)  

5. **Create the Jumping Script**  
   - Go to **Assets → Right Click → Create → C# Script**  
   - Rename it `"Jump.cs"`  
   - Open the script and add the following code:  

6. **Attach the Script to the Player**  
   - Select **Player**  
   - Drag & Drop **Jump.cs** onto it  

7. **Assign the Ground Tag**  
   - Select **Ground**  
   - In **Inspector**, go to **Tag → Add Tag... → Click "+" → Type "Ground" → Save**  
   - Select **Ground** again and assign the `"Ground"` tag  

8. **Run the Program**  
   - Press **Play**  
   - Press **Spacebar** to make the player jump, and if pressed while in the air, the player will fall down  
```  
### Program:
```
using UnityEngine;

   public class Jump : MonoBehaviour
   {
       public float jumpForce = 5f;
       private bool isGrounded;
       private Rigidbody rb;

       void Start()
       {
           rb = GetComponent<Rigidbody>();
       }

       void Update()
       {
           if (isGrounded && Input.GetKeyDown(KeyCode.Space))
           {
               rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
               isGrounded = false;
           }
       }

       private void OnCollisionEnter(Collision collision)
       {
           if (collision.gameObject.CompareTag("Ground"))
           {
               isGrounded = true;
           }
       }
   }
```

### Output:

## Initially player in air:
![Screenshot 2025-04-21 112850](https://github.com/user-attachments/assets/002250ad-13a1-4514-bb5b-3143cee9aff2)


## After player jumped:
![Screenshot 2025-04-21 112928](https://github.com/user-attachments/assets/6c168f07-ddd3-48f0-aaf5-b2e7bb6fa33e)
![Screenshot 2025-04-21 112947](https://github.com/user-attachments/assets/243fbe45-5922-4e5f-a15c-8dbeb237a8bf)









### Result:
Thus the simple seek behavior was implemented successfully.
