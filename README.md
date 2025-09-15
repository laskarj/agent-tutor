# agent-tutor

## Submodules

This repository uses submodules. To clone the repository and its submodules, use:

```bash
git clone --recurse-submodules
```

If you have already cloned the repository without the submodules, you can initialize and update them with:

```bash
git submodule init
git submodule update
```

To update the submodules to the latest commit on their respective branches, use:

```bash
git submodule update --remote
```

## Running LiveKit Locally

To run LiveKit locally for development, you can use the provided Docker Compose configuration. This will start a LiveKit server and a Redis instance.

1.  **Start the services:**

    Use the following command to start the LiveKit server and Redis in detached mode:

    ```bash
    docker-compose --profile livekit up -d
    ```

2.  **Get API credentials:**

    The development server will print the API key and secret in the logs. You can retrieve them with:

    ```bash
    docker-compose logs livekit
    ```

    In this case the API key is `devkey` and the secret is `secret`.

3.  **Generate a join token:**

    To connect to the LiveKit server, you need a join token. You can generate one using the [LiveKit CLI](https://docs.livekit.io/cli/).

    Once you have the CLI installed, use the API key and secret from the previous step to create a token:

    ```bash
    livekit-cli create-token --api-key <your-api-key> --api-secret <your-api-secret> --join --room my-room --identity user
    ```

4.  **Stopping the services:**

    To stop the LiveKit server and Redis, run:

    ```bash
    docker-compose --profile livekit down
    ```
