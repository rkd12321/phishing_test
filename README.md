# phishing_test
AWS workmail, gophish를 사용한 피싱메일훈련 테스트

## 1. gophish Install(https://github.com/gophish/gophish)   

### Amazon Linux2 기준 gophish 설치
---


```
sudo yum install git
sudo yum install golang
git clone https://github.com/gophish/gophish.git
cd gophish 
build
```
### gophish config.json 수정(https://github.com/gophish/gophish/blob/master/config.json)
---
```json
"admin_server": {
		"listen_url": "127.0.0.1:3333",
		"use_tls": true,
		"cert_path": "gophish_admin.crt",
		"key_path": "gophish_admin.key",
		"trusted_origins": []


```


### gophish 실행
---
```
./gophish

```

## 2. Telegram Bot Token 확인

## 3. Telegram chatID 확인 

