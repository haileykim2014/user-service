# user-service
살말 프로젝트
유저서비스

## Getting started
- application.yml 에서 연결할 db 주소 설정을 확인해주세요.
- 아래의 내용과 같이 application-oauth.yml 파일을 따로 생성해주세요.
```
spring:
  security:
    oauth2:
      client:
        registration:
          google:
            clientId: {{id값 설정}}
            clientSecret: {{키값 설정}}
            scope: profile,email

# 토큰 관련 secret Key 및 RedirectUri 설정
app:
  auth:
    tokenSecret: {{키값 설정}}
    tokenExpiry: 1800000
    refreshTokenExpiry: 604800000
  oauth2:
    authorizedRedirectUris:
      - http://localhost:3000/oauth/redirect

# jwt secret key 설정
jwt.secret: {{키값 설정}}
```
