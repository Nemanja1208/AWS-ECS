### Documentation source - `https://aws.amazon.com/getting-started/hands-on/deploy-docker-containers/?ref=gsrchandson`

# Implementation steps

1. Set up your first run with `Amazon ECS`

   The Amazon ECS first-run wizard will guide you through creating a cluster and launching a sample web application. In this step, you will enter the Amazon ECS console and launch the wizard.

2. Create `container` and task definition

   A task definition is like a blueprint for your application. In this step, you will specify a task definition so Amazon ECS knows which Docker image to use for containers, how many containers to use in the task, and the resource allocation for each container.

   - In the `Container` definition field, select `sample-app`

   - The task definition comes preloaded with default configuration values. Click next

3. Define your service

   Now that you have created a task definition, you will configure the Amazon ECS service. A service launches and maintains copies of the task definition in your cluster. For example, by running an application as a service, Amazon ECS will auto-recover any stopped tasks and maintain the number of copies you specify.

   - Service options come preloaded with default configuration values.
   - Service name: The default sample-app-service is a web-based "Hello World" application provided by AWS. It is meant to run indefinitely; because it is running as a service, it will restart if the task becomes unhealthy or unexpectedly stops.
   - Number of desired tasks: Leave the default value of 1. This will create one copy of your task.

   `Load balancing`:
   You have the option to use a load balancer with your service.
   Amazon ECS can create an Elastic Load Balancing (ELB) load balancer to distribute the traffic across the container instances your task is launched on.

- Select the Application Load Balancer option.

- The default values for Load balancer listener port and Load balancer listener protocol are set up for the sample application. Review your settings and choose Next.

4. Configure your `cluster`

   - Your `Amazon ECS` tasks run on a cluster, which uses `AWS Fargate` to provide the compute engine so that you do not need to manage servers. In this step, you will configure the cluster.

   - In the `Cluster` name field, enter `sample-cluster` and choose Next.

5. Launch and view your resources

   In the previous steps, you configured your task definition (which is like an application blueprint), the Amazon ECS service (which launches and maintains copies of your task definitions), and your cluster. In this step, you will review, launch, and view the resources you create.

   - You have a final chance to review your task definition, task configuration, and cluster configuration before launching. Choose Create.

   - You are on a Launch Status page that shows the status of your launch and describes each step of the process. After the launch is complete, choose View service.

6. Open the sample application

   In this step, you will verify that the sample application is up and running by pointing your browser to the load balancer DNS name.

   - On the sample-app-service page, select the Details tab and select the entry under Target Group Name.

   - On the Target groups page, select the target group name.

   - In the Details section, choose the Load balancer link.

   - In the Description tab, select the two page icon next to the load balancer DNS to copy the DNS name to your clipboard.

   - Paste it into a new browser window, and press enter to view the sample application (in this case, a static webpage).

### Good work, you deployed a `docker container` to a `AWS ECS`.

7. Clean up

   Throughout this guide, you've launched three resources: an `Amazon ECS cluster`, `AWS Fargate` to run your container, and a `load balancer`. In this step, you will clean up all your resources to avoid unwanted charges.

   - Navigate back to the `Amazon ECS` console page and select the cluster name (sample-cluster).

   - Choose Delete Cluster to delete the cluster.
