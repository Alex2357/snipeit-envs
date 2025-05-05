
# Environment Configuration

This repository contains configuration files for different environments of the SnipeIT system.

Each environment is described in a separate YAML file following a standard format. These files define the Docker image tags that will be used when setting up or updating the system.

## Repository Structure

```
repo/
├── README.md
├── dev-env-config.yaml
├── test-env-config.yaml
└── prod-env-config.yaml
```

The number of environment files is flexible.  
You can create as many environment files as needed (for example: `dev`, `test`, `prod`), but please be mindful — each file will trigger creation or update of a real environment based on its settings.

## Configuration File Format

Each environment file must have the following structure:

```yaml
env: <environment-name>
snipeitImageTag: "<snipeit-docker-image-tag>"
mariadbImageTag: "<mariadb-docker-image-tag>"
snipeitHost: "<environment-name>.snipeit" # subdomain when you access it must have 42!!!
```

### Example

```yaml
env: dev
snipeitImageTag: "v8.0.4"
mariadbImageTag: "11.1.0-debian-11-r36"
snipeitHost: "<environment-name>.snipeit" # subdomain when you access it must have 42!!!
```

## How to Add or Update an Environment

- To create a new environment, add a new file named `<env>-env-config.yaml`.
- To update an existing environment, modify the corresponding `*-env-config.yaml` file.
- Always follow the structure shown above.
- Make sure the `env` field matches the environment name you want to set up.
- Use correct and verified Docker image tags.

## Important

Once changes are merged into the `main` branch:

- The system will automatically apply the new or updated configuration.
- No further action will be needed after merging.

Please review your changes carefully before raising a pull request.
