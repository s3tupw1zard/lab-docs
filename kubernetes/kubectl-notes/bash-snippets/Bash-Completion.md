## Temporary

Enable Bash completion in the current shell:

```bash
bash
source <(kubectl completion bash) # set up autocomplete in bash into the current shell, bash-completion package should be installed first.
```

## Permanently

Enable Bash completion permanently:

```bash
echo "source <(kubectl completion bash)" >> ~/.bashrc # add autocomplete permanently to your bash shell.
```
