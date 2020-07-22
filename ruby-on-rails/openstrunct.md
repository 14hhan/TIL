# OpenStruct
해시와 비슷한 ruby의 내장 자료구조이다. 
## 사용 예시
```ruby
person = OpenStruct.new

person.name = "Jane Doe"
person.age = 50

person.name     # => "Jane Doe"
person.age      # => 50
person.height   # => nil
```
- 내부에서 해시를 이용하여 attribute와 value를 저장한다. 해시를 이용하여 초기화 될 수도 있다. 
```ruby
pet = OpenStruct.new(:name => "Choco", :owner => "Jane Doe")
=> #<OpenStruct name="Choco", owner="Jane Doe">
```