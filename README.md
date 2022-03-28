# Entando Project Template for React Micro frontends

This is a simple template that can be used to create, build and deploy react micro frontends to Entando ACP.

# Deployment and installation

With this configuration, you can use the ent cli (https://developer.entando.com/next/docs/reference/entando-cli.html) to perform the full deployment sequence:

### Setup the project directory

1. Prepare the bundle directory: `cp -r bundle_src bundle`
2. Initialize the project: `ent prj init`
3. Initialize publication: `ent prj pbs-init` (requires the git bundle repo url)
4. Attach to kubernetes for an Entando application via ent attach-kubeconfig config-file or similar

### Publish the bundle

1. Build: `ent prj fe-build -a` (to just build the frontend, including changes from bundle_src)
2. Publish: `ent prj fe-push` (publish the frontend)
3. Deploy (after connecting to k8s above): `ent prj deploy`
4. Install the bundle via 1) App Builder, 2) `ent prj install`, or 3) `ent prj install --conflict-strategy=OVERRIDE` on subsequent installs.
5. Iterate steps 1-4 to publish new versions.

## Refer to this [Readme](https://github.com/entando-samples/ent-project-template-react/tree/master/ui/widgets/widgets-dir) to learn further about React app setup.

## Local testing of the project

You can use this command from the application folder to run the local stack

- `ent prj fe-test-run` - to run the React frontend
