# Epoch Archive Backup & Restore Guide `epoch-archive-testnet`

Welcome to the Epoch Archive Backup & Restore guide. This README is designed to provide you with a comprehensive walkthrough to manage backups and restoration for your system using the provided Makefile.

## Prerequisites

- Ensure you have the necessary tools installed, such as the latest `libra-framework`, `git`, `jq`, `bc`, `curl`, and `awk`.
- The Makefile is designed for libra-framework v6.9.x (soon v7) Ensure you are using the correct version.

## Getting started

  Clone the repo and prepare the binary:
  ```bash
  cd ~
  git clone https://github.com/0LNetworkCommunity/epoch-archive-testnet
  cd ~/epoch-archive-testnet
  make bins
  ```


## Restoring to the latest version public backup

### Restoring from the latest backup is most likely all you will need to start syncing:
    ```bash
    cd ~/epoch-archive-testnet
    make restore-all
    ```

## Here are some other tools you can make use of
  
2. **Wipe Existing Database**:
    ```bash
    make wipe-db
    ```

3. **Restore Genesis Data**:
    ```bash
    make restore-genesis
    ```

4. **Restore to a Specific Version**:
    ```bash
    make VERSION_START=[db_starting_transaction] VERSION=[db_target_transaction] restore-latest
    ```


## Creating and Maintaining Backups

1. **Prepare Archive Path**:
    ```bash
    make prep-archive-path
    ```

2. **Backup Genesis Data**:
    ```bash
    make backup-genesis
    ```

3. **Continuous Backup**:
    ```bash
    make backup-continuous
    ```

4. **Backup by Epoch**:
    ```bash
    make backup-epoch
    ```

5. **Backup State Snapshot**:
    ```bash
    make backup-snapshot
    ```

6. **Backup Transactions**:
    ```bash
    make backup-transaction
    ```

7. **Setup Git for Backup**:
    ```bash
    make git-setup
    ```

8. **Start Continuous Backup**:
    ```bash
    make start-continuous
    ```

9. **Stop Continuous Backup**:
    ```bash
    make stop-continuous
    ```

10. **Backup Logging Cleanup**:
    ```bash
    make log-cleanup
    ```

11. **Scheduled Tasks**:
    This is what we use to continually provide public backups as they become available:
    ```bash
    make cron
    ```

## Other Commands

- **`make check`**: Validates the environment and displays the configuration.
- **`make wipe-backups`**: Deletes all backups.
- **`make git`**: Commits and pushes the recent backups to the repository.
- **`make git-sling-recent`**: Commits and pushes the 20 most recent backups to the repository.
- **`make git-sling-all`**: Commits and pushes all backups to the repository in batches.

## Contribution

Your contributions are always welcome! Feel free to improve on any of the command explanations or add more clarity as needed.
