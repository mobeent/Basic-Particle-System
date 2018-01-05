# Basic-Particle-System

The project was making a basic particle system with support for all different APIs

* Simulated Rain drops, Number of particles = 3000
* Made Particle Mesh class which is a child of the mesh class so that the particles can be rendered by passing the particles in a single vertex buffer for a single emitter
* The Particle System creates an emitter which stores the information for each particle, the emitter is made at the start of the engine
* The emitter creates particles and uses the ParticleMesh class to use mesh functions and load the buffers that contain information for each particle
* The buffers are passed to custom functions which are used to make a vertex buffer which is transferred to GPU memory
* A custom effect is created which loads the custom Vertex and Pixel Shaders to render the particles on the screen
* From here there are two different approaches taken to update the particles on the screen.
* The frist approach is to update the particles at each frame and then send the new attributes of the particle in a vertex buffer to the GPU in the same way as before
* The second approach is to send all attributes of the particles to the shaders only once and then use these attributes to update the particles on the GPU side so everything is being done in parallel and performance is increased
