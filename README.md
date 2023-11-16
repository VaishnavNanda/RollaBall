# RollaBall

## Aim:
To Roll a Ball using C# program in unity .

## Algorithm:

1. File -> Scene -> Select the scene -> Save as-> New folder(Scenes)-> File name (MiniGame)

2. Heirarchy -> 3D Object-> Plane
3.[ Right side-> Inspector-> Change the name of plane (Name: Ground)
Transform -> Reset
Edit -> FrameSelected ]

4. Scale the ground by giving the scaling value as x=4 y=1 z=4

5. Heirarchy -> 3D Object-> Sphere
[ Right side-> Inspector-> Change the name of plane (Name: Player)
Transform -> Reset
Edit -> FrameSelected 
Transform -> Position -> y=0.5]

6. Hierarchy -> DirectionalLight
[ Inspector -> Change the color to white (255,255,255)]

7. Create a folder in project and name as Materials
[Material folder -> Create -> Material (Name: Background)
Inspector ->Surface Inputs ->BaseMAp (Choose the color)
Metallic map-> 0
Smoothness -> 0.25
Drag the Background to the plane and release the mouse

Material folder -> Create -> Material (Name: Sphere)
Inspector ->Surface Inputs ->BaseMAp (Choose the color)
Metallic map-> 0
Smoothness -> 0.75
Drag the Sphere material to the ball and release the mouse

 7. Hierarchy -> Player-> Inspector ->Add component-> Rigidbody

8. Create a new script -> Create a folder in project (Name: Scripts)
Hierarchy -> Player -> Inspector-> AddComponent-> NewScripts-> PlayerController( Click create and Add)
Copy the PlayerController and drag to Script folder
Double click the PlayerController file and type the coding

## Program:
```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Program : MonoBehaviour
{
    public float Xforce = 5.0f;
    public float Zforce = 5.0f;
    public float Yforce = 300f;

    // Start is called before the first frame update
    void Start()
    {

    }
    // Update is called once per frame
    void Update()
    {
        float x = 0.0f;
        float y = 0.0f;
        float z = 0.0f;
        if (Input.GetKey(KeyCode.A))
        {
            x = x - Xforce;
        }
        if (Input.GetKey(KeyCode.D))
        {
            x = x + Xforce;
        }
        if (Input.GetKey(KeyCode.W))
        {
            z = z + Zforce;
        }
        if (Input.GetKey(KeyCode.S))
        {
            z = z - Zforce;
        }
        if (Input.GetKeyDown(KeyCode.Space))
        {
            y = Yforce;
        }
        GetComponent<Rigidbody>().AddForce(x, y, z);

    }
}
```
## Output:

![Screenshot 2023-10-16 205346](https://github.com/Dharshan011/RollaBall/assets/113497491/12e89daf-0cbf-40ba-ab0c-d2f74d52458a)

## Result:
Thus, The 3D application for Roll the Ball in unity is developed successfully.
