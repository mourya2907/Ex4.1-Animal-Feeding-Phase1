# Ex4.1-Animal-Feeding-Phase1
#AIM :

###To develop a animal feeding game-Phase-1 using unity.

#PLAY CONTROL :
~~~
Step 1
Extract the package and in unity , asserts -> Import packages -> Custom packages and select the package. When we go to Assets folders we can see the course library which we extracted
step 2
If you want, drag a different material from Course Library > Materials onto the Ground object
step 3
Drag 1 Human, 3 Animals, and 1 Food object into the Hierarchy
step 4
Rename the character “Player”, then reposition the animals and food so you can see them
step 5
Adjust the XYZ scale of the food (2,2,2) so you can easily see it from above
step 6
In your Assets folder, create a “Scripts” folder, and a “PlayerController” script inside.Attach the script to the Player by dragging the c# file to the player and open in the inspector and check whether it is attached.
~~~
### MOVING FORWARD :
~~~
step 1
Create a new “MoveForward” script, attach script to the Food Pizza by dragging the c# file to the pizza and open in the inspector and check whether it is attached
step 2
Create a new “Prefabs” folder, drag your food (Pizza) into Prefab folder, and a pop up raises-> choose Original Prefab
step 3
Select the Player in the hierarchy, then drag the pizza from your Prefabs folder onto the new Projectile Prefab box in the inspector
step 4
Rotate all animals on the Y axis by 180 degrees to face down
step 5
Select all three animals in the hierarchy and Add Component > Drag the Move Forward script from the Scripts into inspector
step 6
Edit their speed values and test to see how it looks. Drag all three animals into the Prefabs folder, choosing “Original Prefab”
~~~
### program :
### DEVELOPED BY :Mourya .G
### REG NO : 212224230170

## PLAYER CONTROL :

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerControl : MonoBehaviour
{
    public float horizontalInput;
    public float speed = 10.0f;
    public float xRange = 10.0f;
    public GameObject projectilePrefab;
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if(transform.position.x < -xRange)
        {
            transform.position = new Vector3(-xRange, transform.position.y,transform.position.z);
        }
        if(transform.position.x > xRange)
        {
            transform.position = new Vector3(xRange, transform.position.y, transform.position.z);
        }
        horizontalInput = Input.GetAxis("Horizontal");
        transform.Translate(Vector3.right*horizontalInput*Time.deltaTime*speed);
        
        if(Input.GetKeyDown(KeyCode.Space))
        {
            Instantiate(projectilePrefab, transform.position, projectilePrefab.transform.rotation);
        }
    }
}
```

## MOVING FORWARD :
```

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class MoveForward : MonoBehaviour
{
    public float speed=20.0f;
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        transform.Translate(Vector3.forward*Time.deltaTime*speed);
    }
}

```

### OUTPUT :
![image](https://github.com/user-attachments/assets/1bd3c6c5-3268-45b3-8687-aa1133816422)
### RESULT :
Animal feeding game-Phase-1 using unity is developed successfully.

