# cs418-fa21-project

yans3

https://megavako.github.io/uiuc-cs418-yans3/

Photorealistic Rendering Machine Project
In order to show off your knowledge and skill in computer graphics, you'll write your own WebGL webpage that includes a photorealistic rendering of any scene you like. For inspiration, here is a rendering of a teapot decorated with the University of Illinois logo, reflecting Memorial Stadium.


The teapot model is provided, but you can make your scene out of any models you like. The one requirement is that the models must be polygonal mesh models and at least some portion of these models must represent a smooth non-flat surface.

Required Elements

Your project should consist of the following required elements totalling 100 points corresponding to completing 100% of the assignment. The example teapot above, with its Illinois logo texture and Memorial Stadium reflection, minimally satisfies all of these required elements.

50 points: Geometry Processing. Proper processing and projection of meshed models, including all vertex attributes.
10 points: Smooth Per-Pixel Shading. Smooth surfaces have no flat faceted regions, or Gouraud color interpolation.  (In the example above, there are some reflection anomalies where the body of the teapot meets the bottom of the handle. These are due to the fact that the normals are averages of adjacent face normals, so no points would be taken off for such artifacts.)
10 points: Diffuse Reflectance. The scene should be illuminated by at least one light source, and at least one surface should exhibit some form of diffuse reflection such that surfaces oriented away from the light source do not reflect any light from it.
10 points: Specular Highlights. The scene should be illuminated by at least one light source, and at least one surface should exhibit some form of specular reflection in the form of a specular "gleam" highlight. You can use the Phong or Blinn formula for this specular highlight.
10 points: Surface Texture. The base object color used for diffuse reflectance of at least one of the surfaces should be the result of a texture map. You will need to create texture coordinates in order to do the texture mapping. The texture coordinates in the example above were computed based on the model coordinates using a cylindrical texture coordinate formula.
10 points: Reflective Surface. The specular reflectance of at least one of the surfaces should include a reflection obtained from an environment map.
Bonus Elements

In addition, your project can include any number or combination of the following bonus elements, though a maximum of 40 additional bonus points will be applied based on these bonus elements.

10 points: Scene Mirror. The scene includes a flat mirror that shows a reflection of at least one object in the scene. The mirror is implemented by drawing the reflected objects using a modelview matrix that includes a reflection matrix.
10 points: Shadow Projection. The scene exhibits a shadow cast by one object onto a plane (e.g. a floor) by redrawing the object using a different modelview matrix. (Credit for shadow projection will not be available for anyone implementing shadow buffering.)
20 points: Shadow Buffering. The scene exhibits a shadow cast by one object onto another object by utilizing a z-buffer from the light's perspective.
10 points: Procedural Texture. At least one surface exhibits a texture color resulting from computation instead of a texture map lookup.
20 points: Bump Mapping. At least one surface in the scene has surface normals that have been modified by a texture map to create a recognizable embossed detail in the surface.
10 points: Other Lighting Models. The diffuse and/or specular lighting for one of the models is computed using a published model other than Lambertian diffuse, Phong specular and Blinn specular. Must include a reference to the specific lighting model used.
Grading

This assignment will be TA graded and has a hard deadline of Sunday Dec. 4th 2021 at 11:59pm CST. Late penalties will be applied at the rate of 10% per day.

This assignment will represent the "4th credit" for students taking this course for four credits instead of three credits. Four-credit students include all graduate students, whereas undergrad students typically take the course for three credits.

Four-Credit Students: This assignment will represent 25% of your final grade, whereas the rubric in the syllabus (including the weekly quizzes, periodic autograded assessments and exams) represents 75% of your final grade. A maximum of 40% extra credit can be earned by completing bonus elements for this assignment, resulting in as much as 140% for the entire assignment which would result in an additional 10% extra credit applied to your course grade.

Three-Credit Students: You do not need to complete this assignment and your grade will not be penalized for not completing this assignment. However, you are allowed to complete this assignment and any points you receive for this assignment in excess of the required 100 points will be applied as extra credit toward your final grade. A maximum of 40 additional points can be earned by completing bonus elements for this assignment, which would result in an additional 10% extra credit for your course grade.

Instructions on how to submit your project will be posted later at Week 14.

Boilerplate Code on GitHub

I have set up a photorealistic boilerplate to get you started. You can find the boilerplate code at https://github.com/jch-uiuc/cs418-fa21-project and see its output at https://jch-uiuc.github.io/cs418-fa21-project/, which I've reproduced below. This boilerplate code loads the teapot geometry, generates normals and sends the vertices and their attributes to the GPU. This code also loads two textures (an Illinois logo and a stadium spheremap) and displays a 50-50 blend of these textures on the teapot, using the teapot vertices' x and y model coordinates as their texture coordinates (s,t).


Web Page Hosting using GitHub Pages

We'll be using GitHub Pages to host these projects, to ensure they can be accessed and graded fairly and anonymously. To get set up please perform the following steps to create your own GitHub page and initialize it with this boilerplate code to make sure it is working.

Go to github.com and create a GitHub account (if you don't already have one).
 On the repositories tab of your account, click the green "New" button to create a new repository.
Give the repository a unique name, such as "uiuc-cs418-<netid>" where <netid> is your Net ID.
The next page will give you four options to setup your new repository. Pick the fourth option "... or import code from another repository" by clicking its "Import code" button.
Enter the following repository clone URL and press "Begin import."
https://github.com/jch-uiuc/cs418-fa21-project.git
This will set up a repository for you on GitHub. In order to view the WebGL webpage generated by the index.html file, click on the "Settings" tab and then select the "Pages" item on the left side of the screen.
Under "Source" select your "main" branch, and then click the "Save" button.
 You should see a message stating your site is ready to be published, and a link to the published webpage. WARNING: THIS LINK MAY TAKE AS LONG AS 20 MINUTES TO BECOME ACTIVE AND/OR TO REFLECT CHANGES TO YOUR REPOSITORY. Please be patient and give it 20 minutes if it shows a 404 error or doesn't reflect your changes.
Code Development

See also the Texture Mapping Boilerplate at the end of Week 7 for details on how to download and run a local web server to write and debug code on your own computer. The local web server is often needed to overcome CORS permissions for using images as textures in web pages.
