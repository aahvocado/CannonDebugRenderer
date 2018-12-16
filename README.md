# CannonDebugRenderer
The original CannonDebugRenderer.js - https://github.com/schteppe/cannon.js/blob/master/tools/threejs/CannonDebugRenderer.js

Updated the original file since it wasn't built for bundlers. Since it's expected to be it's own module, it expects both Cannon and Three as a dependency. 

I've made ESLint ignore this file since there were some minor warnings but may come back to properly update this.

## Usage
Bring in the module then initialize it as a new object, passing in parameters like you would with the original.

```
import CannonDebugRenderer from './CannonDebugRenderer';

...

// pass the Three.js scene and the Cannon.js world
const debugRenderer = new CannonDebugRenderer(scene, world);

...

// update the CannonDebugRenderer as you update the Three.js scene
function render() {
  requestAnimationFrame(render);
  world.step(1/60);                 
  debugRenderer.update();
  renderer.render(scene, camera);
}
```
