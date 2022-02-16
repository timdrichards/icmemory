# icmemory

A memory diagram visualizer, checker, and grader

# MHz Example File Description

The file always begins with 2 objects. The first object is the stack and, in
this example, contains 2 frames. The first frame is for a function named “Bob”
and the second frame is for a function named “BobJr”.

Each frame (and object) is given a unique identifier. For simplicity, stack
frame id’s start with “STACK” and objects in the heap id’s start with “HEAP”.
After the identifier is a number that reflects the order it was created.

The second object specifies the heap and any objects in the heap. In this
example there are two objects. One object is of type “Blob” and the second
object is of type “BiggerBlob”.

“ROOTSTACK” is the ID for the “box” that defines the entirety of the STACK.

“ROOTHEAP” is the ID for the “box” that defines the entirety of the STACK.

We used “boxes” to define most things drawn as a box to keep the code reasonably
simple and reusability high.

There is then an array that specifies all of the variables/fields (this assumes
that references are only to objects and cannot point into objects). There is an
array entry for each frame and object. Each entry is an objects with 2 key-value
pairs. One key is “ID” with a value specifying the ID of the “box” whose
variables/fields/stuff is being entered. (edited)

The other key is “FIELDS” and its value is an array of variables/fields/stuff
that exist in the box. Each variable/field has a “label” (its name), an ID (a
unique string that identifies if it is a primitive or reference).

References can also have an “Edge” key whose value is the box that it points to.

Frames/objects that do not have any variables/fields/stuff would still have an
entry in this array. In those cases, the value for the “Fields” key would be an
empty array.

Reviewing this, we included the X & Y for the top-left corner of each thing in
this encoding along with the height it needed.

I am not sure why this was done, but it would be easy to either write a grader
program that could ignore that information OR create a secondary file with that
information (kinda like how HTML uses CSS files for formatting info)
