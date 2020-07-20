# 암호화 인증서
암호화 인증서를 이용하여 보안키를 암호화 하여 사용할 수 있도록 하는 rails의 기능이다. 
암호화 인증서는 config/credentials.yml.enc 파일에 저장된다. 
## 사용법
- 터미널에서 암호화 되지 않은 인증서를 등록, 관리한다.
```zsh
bin/rails credentials:edit
```
- 암호화된 인증서 값을 호출한다. 
```ruby
Rails.config.saved_key_name
```