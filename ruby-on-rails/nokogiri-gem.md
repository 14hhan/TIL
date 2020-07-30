# Nokogiri
HTML, XML 등을 파싱할 수 있는 Ruby Gem 이다. 웹 크롤링 작업하며 스크래핑 한 파일을 파싱할 때 사용했다. 
## 사용 예시
```ruby
doc = Nokogiri::HTML(File.open("path/to/file/file_name.html"), nil, 'utf-8')
nodeset = doc.xpath("copied_xpath") # Chrome의 Inspect기능을 사용하여 파싱하고자 하는 nodeset의 xpath를 복사한다. 

nodeset.children # nodeset이 포함하고 있는 모든 node의 children을 반환한다. 
nodeset.at(index) # 입력한 index의 node를 반환한다. 
nodeset.at("name") # 입력한 name의 node를 반환한다. 
nodeset.text # 포함하고 있는 모든 텍스트를 string으로 반환한다. 
```