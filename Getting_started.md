1) Navigate into the folder
        ```
        cd C:\Users\marcu\projects\Ex_Files_Learning_Kubernetes_Upd\Exercise Files\03_04


        # Enter - kubectl gets the status of the running clusters
        kubectl get all

        # Deploy application - create resource -f (file)
        kubectl create -f .\helloworld.yaml
        kubectl get all

        # Access the webpage by creating service construct. Do this by exposing the name as type of >
        kubectl expose deployment helloworld --type=NodePort
        kubectl get all

        # Run application which references the helloworld container
        minikube service helloworld
        ```

2) Let's look at deployment

        ```
        # first deployment - deploy two artefacts
        kubectl get deployment
        kubectl get delpoyment helloworld -o yaml
        kubectl get service
        kubectl get service helloworld -o yaml

        # second
        kubectl
        ```

