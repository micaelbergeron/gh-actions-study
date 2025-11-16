# gh-actions-study
Various studies on GH Actions

## File-Conditional Workflow

This repository demonstrates a GitHub Actions workflow that conditionally runs jobs based on the presence of a specific file.

### How It Works

The workflow `.github/workflows/file-conditional.yml` implements the following pattern:

1. **Check File Step**: Checks if `config/enable-workflow.txt` exists
2. **Conditional Job**: Only runs if the trigger file is present
3. **Skip Notification**: Runs when the file is absent to explain why the job was skipped

### Usage

- **Enable the workflow**: Create or keep the file `config/enable-workflow.txt`
- **Disable the workflow**: Delete the file `config/enable-workflow.txt`

This pattern is useful for:
- Controlling expensive or optional CI jobs
- Feature flags in monorepos
- Environment-specific configurations
- Temporarily disabling workflows without modifying workflow files

### Testing

You can test this by:
1. Pushing changes with the file present - the conditional job will run
2. Deleting the file and pushing - the job will be skipped
