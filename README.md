# view-orbital-blender
Calculates (gaussian) and shows (JMol/blender) molecular orbitals

So this is how it works:

-in gaussian

1. Build your structure in gaussview (or import from hyperchem etc.)
2. calculate orbital information with whatever functional u want to
2a. Wait ... This may take ~2days on a 4core i5 4690)
3. "Edit => MOs" and choose what surfaces you want to show  
3a. "Visualize => Isovalue (0.04) and Cube Grid (Coarse) regulate the detail level of the created mesh  
3b. Wait .... This may take some time (10min) ... There is a console window popping up that should close first

4. GOTO "Results => Surfaces/contours"  
4a. There should be already created surfaces for the orbital u'v chosen.  
4b. Click on "Cube Actions => Save Cube" (up right)  
4c. filename.cub file is generated and saved  
5. save ur structure as mol file

-in JMol

1. open structure .mol file
2. open a console (File=> Console)

3a. create positive parity isosurface mesh with ``` isosurface "0.04" "filename.cub"  ```  
3a!. If the response is something like ``` isosurface1 created  with cutoff=0.0 min=0.0 max=0.0; isosurface count: 0 ``` than 3b did not work, maybe you were impatient and did not wait until the confole windows of cubegen finished?
3b. click inside the workspace and do "File=> Export=> X3D Model"  
3c. Save as "...-positive.x3d"

4a. create negative parity isosurface mesh with "isosurface -0.04 "filename.cub"  
4b. click inside the workspace and do "File=> Export=> X3D Model"  
4c. Save as "...-negative.x3d"  

-in blender
1. import "...-positive.x3d" and "...-negative.x3d"
