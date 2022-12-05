# Na-Hong
3D star rain
I used the 3D transformations I learned in Lesson 6, mainly using only Three.js to make a different scene where stars fall from the sky. Actually, at first I set up the petals falling scene, but the effect was too generic, so I replaced it with a shower of stars. Since I wanted to make the effect of the galaxy in the universe, but it was too complicated and always failed, so I gave up using the particle loop to show the effect, and then used the star texture to show the star group. Although this is not the most complicated one in my project, but I feel it is the best looking one.

Three.js is a framework for simplifying the development of 3D scenes based on the API package of WebGL. I first created the Scene, and then grouped them in the Scene for easy management. 

In Three.js, I used Sprite to simulate stars, and the texture of stars Pasted on the Sprite. Spirit could be textured very well, so I don't need to create complicated geometry again, which is very convenient. There were many stars, I generated 400, added them to the group, and then added them to the scene. I set the background to black, and the textures of the stars were light color, which would give people a feeling of stars shining in the dark. All the Sprites were randomly pasted with texture maps of stars of different colors, and then set up and down scaling, and then randomly set a position in the scene. I added a coordinate system aid to the Scene. Then according to the code, the x range of the star is random -1000 to 1000, and the y range is 0 to 2000. Then when I created the camera, I specified the range that can be displayed in 2D. Wherever the camera is within this range, you can see the star shower. 

I used OrthographicCamera in Camera, although there was no perspective effect, but this could clearly observe every star, and there would be no sense of clutter. In the parameters of the orthographic camera, the far and near are set to 1 and 1000, the up and down are set to 200, and the left and right can be calculated according to the aspect ratio. This is the extent of the two-dimensional picture that the camera sees. With the various objects in the scene Scene and the camera Camera, I start to use the renderer Renderer to render the picture. RequestAnimation is a good way to render frame by frame continuously.

In the set cycle, before each re-rendering, the position of the stars will be modified to produce a falling effect. If it exceeds the range, it will move to the top to start falling again, thus producing an uninterrupted star rain effect. 

This process is very fast and simple, and the range of rendering is relatively small, so the error of the effect is not very large. And it can be realized without additional functions. I will try to use the perspective function to make particles again later Milky Way, while adding animation effects.

Mimic:
https://mimicproject.com/code/5ff3dc15-e1f0-9c95-0508-20f25094505a
