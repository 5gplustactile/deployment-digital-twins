# deployment-digital-twins
This repo is aimed to create digital twins as code

## Procedure
**Creating cluster DT:**

1. Go to deployment-digital-tiwns repo.
  Create the ```dt/NAME_DT``` branch.
  Creates the workspace to store the argocd app
  to the digital twin (ex. telefonica/main.yaml)

    1.1. Add the content of Argocd app using the 
       ```examples/digital-twin/main.yaml``` template in the
       workspace main yaml file ```(ex. telefonica/main.yaml)```.
       It is important to knows the ```spec.destination.server```
       endpoint where the digital twin will be deployed.
       Checks all the main.yaml and push the changes in
       ```dt/NAME_DT``` branch

2. Once pushed. A pipeline will be triggered. A PR will be
    created automatically from ```dt/NAME_DT``` into main
    wait until all steps are successfully completed.

3. Merge the changes into main. A new pipeline will be triggered
   to adapt the argocd app (```main.yaml```) to the enviroment.

4. Go to the ArgoCd GUI, filter with digital-twins project and
   see the objects created.
    
