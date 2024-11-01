Requirment:
1) Unity Hub.
2) Any Version Unity
3) Visual Studio Code

INSTRUCTION:

Choose the Charcter model or the parent file to which the character model is connected and then move (drag and drop) the imported Cs. script and attach it to the parent file in the inspector section.




EXPLANATION :
1).  Vector2 inputVector = new Vector2(0,0);
        
        if(Input.GetKey(KeyCode.W)) {
            inputVector.y = +1;
        }
        if(Input.GetKey(KeyCode.S)) {
            inputVector.y = -1;
        }
        if(Input.GetKey(KeyCode.A)) {
            inputVector.x = -1;
        }
        if(Input.GetKey(KeyCode.D)) {
            inputVector.x = +1;
        }

The preceeding code is used to asign the input keys which are you to move the direction of the objact or character.
a vector2 is used to take the x and y coordnates of the character.

2).while degugging this strain of code i further added the following code.

 {inputVector = inputVector.normalized;}
 
 this was done in order to fix an issue that occured when pressing two keys i. 'A' and 'S' or 'W' and 'D'
 witout this line the vaule overlapped.

At this stage of the code the character can move upward and sideways when each of the assigned keys are pressed.
 how ever as the objective is to make a script that moves the character in the foward or backwards direction we use the following piece of code

     Vector3 moveDir = new Vector3( inputVector.x, 0f, inputVector.y); 
 
 the oject can move on the z axis .
 NOTE! how the Vector3 variable cannot be assigned in the start of the code as it would require the inclusion of two new input keys.
The following code is used to transform or move the actual object 

       transform.position += moveDir * Time.deltaTime;

  here an addition operator is used as we have to changer the postion sing the assignment operator will fix the object at (0,0) position.
  Time.deltaTime is used in order to keep the character movement to a normal ammount when the framerate is increased drastically


 At this stage the cahnge in the change in dirction the character takes are almost instantaneous 
 in order to fix this i add both a both a slurp function but also the float var that determines the speed of the rotations
 as well as a float var for determining the speed of the character or object.
    [SerializeField] private float movement =7f;

        float rotatespeed = 9f;
        transform.position += moveDir * movement * Time.deltaTime;
        transform.forward = Vector3.Slerp(transform.forward, moveDir, Time.deltaTime * rotatespeed);

 The movement var is then multilpied by the movDir Vector3. The float for movement is kept as a privite class in order to prevent 
 as changes being made to that var.[SerializeField] is also used in order to change the value of the var form the unity hub


