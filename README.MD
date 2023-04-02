# Single Git Accounts Config

```sh
ssh-keygen -C "user@example.com" -f id_rsa -P ""
```

# Multiple Git Accounts Config

## Create Azure Devops SSH Key

```sh
ssh-keygen -C "userAzure@example.com" -f azure -P ""
```

## Test Azure Devops SSH Key

```sh
ssh -T git@ssh.dev.azure.com
```

## Create Github SSH Key

```sh
ssh-keygen -C "userGithub@example.com" -f github -P ""
```

## Test Github SSH Key

```sh
ssh -T git@github.com
```

## Insert this content into the ~/.ssh/config file

    # azure devops
    Host ssh.dev.azure.com
    IdentityFile ~/.ssh/azure
    HostkeyAlgorithms +ssh-rsa
    PubkeyAcceptedAlgorithms +ssh-rsa

    # github
    Host github.com
    User git
    Hostname github.com
    IdentityFile ~/.ssh/github
    PreferredAuthentications publickey