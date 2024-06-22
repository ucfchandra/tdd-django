# TDD in Containerized Django

Following the instructions to OBEY THE TESTING GOAT in the upcoming Third edition of Test-Driven Development with Python by Harry Percival. Based on a containerized Django 5 template that works with Odo for development with live-reloading.

Ensure you have Podman, Odo, and Django installed. Then pull the repository and use the following command:

`ODO_PUSH_IMAGES=false odo dev --platform=podman --port-forward 8000:8000`

Now make a change in the Django app folder. Odo will track that change and live-reload the Django application.

If you want to see the live logs of your application for debugging purposes, go to another terminal while odo is running and use the following command:

`odo logs --follow --platform=podman`

Now, you can write tests. Run the unit test from your local development environment and run the functional test on the running container. It will fail. Then write the code. Wait for a couple seconds for odo to reload the app, then run the functional test again. It will pass. Excellent workflow for TDD in Django while remaining in a containerized environment with no need for venv!
