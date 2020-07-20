# HTTParty
RESTful 웹 서비스를 쉽게 도와주는 Ruby Gem이다. 
작업 중 외부 API로 post 하기위해 사용했다. 
## 사용 예시
- POST
```ruby
url = "https://api.example.com/..."
api_message = { api_key: "my_api_key", attribute: "my_attribute", ... }

HTTParty.post(
    url,
    body: JSON.dump(api_message),
    headers: { "Content-Type" => "application/json" }
)