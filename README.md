# aws-doc


## Summary
return [Summary](#summary)

<!-- TOC -->

- [aws-doc](#aws-doc)
  - [Summary](#summary)
  - [安裝 VMware Tools](#安裝-vmware-tools)
  - [AWS Command Line Interface](#aws-command-line-interface)
    - [AWS 命令列界面 (CLI) 下載](#aws-命令列界面-cli-下載)
    - [設定AWS CLI](#設定aws-cli)
      - [取得 Access key ID 和 Secret access key](#取得-access-key-id-和-secret-access-key)
      - [配置 credentials](#配置-credentials)
      - [安裝 Node.js 後，安裝 AWS CDK Toolkit（cdk命令）：](#安裝-nodejs-後安裝-aws-cdk-toolkitcdk命令)

<!-- /TOC -->

## 安裝 VMware Tools
return [Summary](#summary)

```
// 如果掛接點目錄尚不存在，請加以建立
mkdir /mnt/cdrom

// 掛接 CD-ROM 光碟機
mount /dev/cdrom /mnt/cdrom

// 解壓縮到此 /tmp 資料夾中
cd /tmp

// 解壓縮安裝程式
tar zxpf /mnt/cdrom/VMwareTools-x.x.x-yyyy.tar.gz

// 卸載 CD-ROM 映像
umount /dev/cdrom

// 執行安裝程式
cd vmware-tools-distrib
sudo ./vmware-install.pl

```





## AWS Command Line Interface
return [Summary](#summary)

AWS Command Line Interface 第 2 版使用者指南
https://docs.aws.amazon.com/zh_tw/cli/latest/userguide/cli-configure-quickstart.html


### AWS 命令列界面 (CLI) 下載
return [Summary](#summary)

https://aws.amazon.com/tw/cli/

```
// 下載
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

// 解壓縮
unzip awscliv2.zip

// 安裝
sudo ./aws/install

// 確認安裝成功
aws --version
```

### 設定AWS CLI
return [Summary](#summary)

#### 取得 Access key ID 和 Secret access key
return [Summary](#summary)

- 進到IAM<https://console.aws.amazon.com/iam/>
- 選擇 Users (使用者)
- 選擇 Security credentials (安全憑證) 標籤
- 在 Access keys (存取金鑰) 區段中，選擇 Create access key (建立- 存取金鑰)
- 可以下載csv，取得 `Access key ID` 和 `Secret access key`

#### 配置 credentials
return [Summary](#summary)


```
aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-1
Default output format [None]: json
```


~/.aws/credentials
```
[default]
aws_access_key_id=AKIAIOSFODNN7EXAMPLE
aws_secret_access_key=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
```

~/.aws/config
```
[default]
region=us-west-2
output=json
```

配置完成可以用 AWS-cli 查看S3

```
user@ubuntu:~$ aws s3 ls
2022-03-29 07:51:51 aws-cloudtrail-logs-726526211588-798c0c84
2022-04-09 01:39:07 cfc104-project1-wordpress-s3
2022-03-25 08:52:38 codepipeline-ap-northeast-1-53625009056
```




#### 安裝 Node.js 後，安裝 AWS CDK Toolkit（cdk命令）：
```
npm install -g aws-cdk
```


update cdk v2
```
npm update -g aws-cdk
```







