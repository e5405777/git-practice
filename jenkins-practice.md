# Jenkins Practice

Under Execute Shell, we can check which node the build is running on.

```bash
echo "Node name: $NODE_NAME"
echo "Hostname: $(hostname)"
echo "Workspace: $WORKSPACE"
