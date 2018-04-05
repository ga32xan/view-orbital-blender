# view-orbital-blender
Calculates (gaussian) and shows (JMol/blender) molecular orbitals

So this is how it works:

-in gaussian

1. Build your structure in gaussview (or import from hyperchem etc.)
2. calculate orbital information with whatever functional u want to
3. "Edit => MOs" and choose what surfaces you want to show  
3a. "Visualize => Isovalue (0.02) and Cube Grid (Fine) regulate the detail level of the created mesh  

4. "Results => Surfaces/contours"  
4a. There should be already created surfaces for the orbital u'v chosen.  
4b. Click on "Cube Actions => Save Cube" (up right)  
4c. filename.cub file is generated and saved  
5. save ur structure as mol file

-in JMol

1. open structure .mol file
2. open a console (File=> Console)

3a. create positive parity isosurface mesh with 
``` isosurface "0.04" "filename.cub"  ```
3b. click inside the workspace and do "File=> Export=> X3D Model"  
3c. Save as "...-positive.x3d"

4a. create negative parity isosurface mesh with "isosurface -0.04 "filename.cub"  
4b. click inside the workspace and do "File=> Export=> X3D Model"  
4c. Save as "...-negative.x3d"  

-in blender
1. import "...-positive.x3d" and "...-negative.x3d"
