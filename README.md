# sit737-2025-prac7p
1. Enable Kubernetes on Docker Desktop
•	Launch Docker Desktop from the system tray.
•	Navigate to the Settings panel.
•	Under the Kubernetes section, enable the Kubernetes option.
•	Apply the changes and allow Docker to restart for the configuration to take effect.
2. YAML file creation:
•	Create a CreateConfigMap.yaml to store the MongoDB configuration
•	Create createMongoDbSecret.yaml to store the sensitive information like DB passwords.
•	Create createHeadlessService.yaml 
•	Create createStatefulSet.yaml to set the environment variables and mount persistent storage.
3. Apply these YAML files:
•	kubectl apply -f createConfigMap.yaml
•	kubectl apply -f createMongoDbSecret.yaml
•	kubectl apply -f createHeadlessService.yaml
•	kubectl apply -f createStatefulSet.yaml
4. Verify the pod status:
•	Verify the pod status using the command kubectl get pods. Three MongoDB pods are created.(mongo-0, mongo-1, mongo-2)
5. Access the primary pod:
•	Access the primary Mongo-0 pod and log in to the shell. Use the command - kubectl exec -it mongo-0 to access the shell.
•	Insert a few test data in the testdb in the primary pod.
6. Verify the Replication:
•	Exit from the primary pod and log in to any secondary pod.
•	Use the command kubectl exec -it mongo-1 to access the shell for the secondary pod.
•	Use command rs.slaveOk() and db.notes.find() to read the data.
•	The data is available in secondary pod and this confirms the replication of the database. 
7. Push Code to Repository
•	Initialize a Git repository (git init).
•	Add and commit files using the commands - git add . & git commit -m "Initial commit".
•	Push to a GitHub repository.
