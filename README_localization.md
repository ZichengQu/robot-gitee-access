# Preparation

Note for this project `robot-gitee-access`.

## Step 1. hook_secret for Gitee

Please modify the hook_secret in `config/hook_secret`. WebHook 密码/签名密钥 -> 签名密钥 (不是WebHook密码)

## Step 2. Listen to org/repo

Please modify the `repos` in `config/robot-access.yaml`, the content should be `org/repo`.

## Step 3. Start the service

Make sure that be in the project path, and run the following command:

```sh
go run . -plugin-config=config/robot-access.yaml --port=30008 --hmac-secret-file=config/hook_secret
```

or

```sh
chmod 755 ./run_commond.sh
./run_commond.sh
```

## Other notice

The webhook URL should be `http://ip_address:30008/gitee-hook`
