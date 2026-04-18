## Procedural Mesh Collection

This repository contains Blender Python scripts for generating organic, parametric geometry. These tools use a combination of **BMesh** for mesh generation and **Armature-driven deformations** to allow for real-time animation of complex botanical and organic forms.
<img width="588" height="513" alt="image" src="https://github.com/user-attachments/assets/3254e4d4-91eb-44e0-a203-a0d69951490e" />
<img width="393" height="153" alt="image" src="https://github.com/user-attachments/assets/aaeb6f8a-73c4-420c-9dc0-83450ba31a1a" />
<img width="528" height="456" alt="image" src="https://github.com/user-attachments/assets/587386b6-5272-45f7-8f87-d4aa4e0609e2" />


https://github.com/user-attachments/assets/2f1f4786-20be-45de-b442-2f7b21bf694b

<img width="692" height="455" alt="image" src="https://github.com/user-attachments/assets/12f16181-5907-4958-bf4f-30bbc5d01612" />


-----

## Physalis (Chinese Lantern) Generator

The core script in this collection generates a procedural Physalis lantern. It is designed to be highly adjustable through custom properties on the armature. Including these visual references allows for easy discrimination between this lantern script and future variants like "zombie pods" or succulent shapes.

### Mesh Visualization

### Custom Control Interface

The script automatically generates custom sliders on the **Physalis\_Arm** object to control the mesh deformation:

| Property | Function |
| :--- | :--- |
| **Fold\_Slider** | Controls the rotation of the bone chains to open or close the lantern structure. |
| **Arch\_Depth** | Adjusts the curvature and "bulge" of individual petals. |
| **Width\_Adjust** | Scales the width of the petals while maintaining the central spine position. |

-----

## Technical Features

### Automated Bone Weighting

The script calculates the proximity of generated vertices to the petal's central "spine." It assigns vertex weights to a chain of bones (the number of which is defined by the `resolution` variable), allowing for smooth, curved folding without manual weight painting.

### Procedural Geometry Math

The mesh utilizes a sine-wave distribution for petal width:

$$w\_max = (base\_width / 2) \times \sin(\pi \times s / resolution)$$

The arching effect for the petals is calculated using a parabolic falloff from the spine:

$$z\_v = (1.0 - (t\_f^2)) \times arch\_max \times \sin(\pi \times r / height)$$

-----

## Usage Instructions

1.  Paste the script into the Blender **Text Editor**.
2.  Press **Run Script**.
3.  Select the **Physalis\_Arm** in the 3D Viewport.
4.  Navigate to the **Custom Properties** panel in the **Object Data Properties** tab to adjust the sliders as shown in the UI reference images above.

-----

## Future Variants

Additional scripts in this repository follow similar logic for:

  * **Zombie/Organic Pods**: Utilizing the same armature-fold logic but with randomized "growth" noise and thicker solidification.
  * **Succulent/Petal Generators**: Variations on the petal math to create tighter, spiraling leaf patterns.
