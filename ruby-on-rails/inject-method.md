# inject
연속적으로 메서드를 적용한 결과를 리턴한다. 
해시 메서드로, inject를 통해 키를 추가하거나 삭제할 수도 있다. 
## 사용 예시
```ruby
[1, 2, 3].inject(0){|sum, item| sum += item}
=> 6
```
- 초기값을 생략해도 된다. 
```ruby
[1, 2, 3].inject{|item, sum| sum += item}
=> 6
```
- 적용할 함수 이름을 심볼로 직접 받을 수도 있다. 
```ruby
[1, 2, 3].inject(:+)
=> 6
```
```ruby
fruit = { name: 'apple', color: 'green', shape: 'round' }
=> {:name => "apple", :color => "green", :shape => "round"}

new_fruit = fruit.inject({}) { |memo, (k, v)| memo[k.to_s] = v.upcase; memo }
=> {"name" => "APPLE", "color" => "GREEN", "shape" => "ROUND"}
```