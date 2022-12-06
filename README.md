# phishing_test
AWS workmail, gophish를 사용한 피싱메일훈련 테스트

## 1. gophish Install(https://github.com/gophish/gophish)   

### 1) Amazon Linux2 기준 gophish 설치
---


```
sudo yum install git
sudo yum install golang
git clone https://github.com/gophish/gophish.git
cd gophish 
build
```
### 2) gophish config.json 수정(https://github.com/gophish/gophish/blob/master/config.json)
---
#### - 수정 전
```json
"admin_server": {
		"listen_url": "127.0.0.1:3333",
		"use_tls": true,
		"cert_path": "gophish_admin.crt",
		"key_path": "gophish_admin.key",
		"trusted_origins": []
	},
```
#### - 수정 후
```json
"admin_server": {
		"listen_url": "0.0.0.0:3333", # EC2에 설치하므로 외부에서 오픈되어야 하며, ACL은 보안그룹으로 제어
		"use_tls": true,
		"cert_path": "gophish_admin.crt",
		"key_path": "gophish_admin.key",
		"trusted_origins": []
	},
```

### 3) gophish 실행
---
#### - 일반 실행 시 
```
./gophish
```
#### - 상시 실행 시 백그라운드 실행
```
nohup ./gophish &
```
#### - 백그라운드 실행 후 초기 ID/PW 확인
```
tail -f nohup.out
```

## 2. 피싱 공격자 메일 생성 AWS WorkMail 만들기
---
참고 URL
#### AWS WorkMail 생성 https://qiita.com/sugimount-a/items/bf53ddfb1478d3fa0f23
#### AWS WorkMail SMTP 설정 https://qiita.com/sugimount-a/items/e148731f56e7dd6a7fe8




