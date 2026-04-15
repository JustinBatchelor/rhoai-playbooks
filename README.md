# AI Workspace Playbooks

Playbooks that consume the `rhoai.ai_workspace` Ansible collection to
provision and tear down self-service AI coding workspaces on OpenShift.

## Setup

Install the required collections:

```bash
ansible-galaxy collection install -r collections/requirements.yml
```

For local development against the collection source:

```bash
cd ../rhoai-ai-workspace-collection
ansible-galaxy collection build .
ansible-galaxy collection install rhoai-ai_workspace-1.0.0.tar.gz --force
```

## Usage

### Provision a workspace

```bash
ansible-playbook playbooks/provision-workspace.yml \
  -e username=jbatchel \
  -e git_repo=https://github.com/org/repo.git \
  -e ai_model=qwen25-coder-14b
```

### Tear down a workspace

```bash
ansible-playbook playbooks/teardown-workspace.yml \
  -e username=jbatchel
```

## AAP Job Template Configuration

See the main project [README](../docs/README.md) for AAP Job Template
survey setup instructions.
