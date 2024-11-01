Requirment:
1) Unity Hub.
2) Any Version Unity
3) Visual Studio Code

INSTRUCTION:

Choose the Charcter model or the parent file to which the character model is connected and then move (drag and drop) the imported Cs. script and attach it to the parent file in the inspector section.




EXPLANATION :
1). Vector2 inputVector = new Vector2(0,0);

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

2). while degugging this strain of code i further added the following code.

 inputVector = inputVector.normalized;
 
this was done in order to fix an issue that occured when pressing two keys i. 'A' and 'S' or 'W' and 'D'
witout this line the vaule overlapped.

At this stage of the code the character can move upward and sideways when each of the assigned keys are pressed.
how ever as the objective is to make a script that moves the character in the foward or backwards direction we use the following piece of code


