# rails generate
코드를 자동으로 생성해주는 rails command line이다. 

## model
DB의 model을 자동으로 생성할 수 있다. 

### 사용법
```zsh
rails generate model <model_name> <column_name>:<data_type>
```
- 모델 클래스를 만들고 지정한 타입의 변수를 만들며 migration 파일을 생성한다. 
- generate 대신 g를 입력해도 된다. 

```zsh
rails db:migrate
```
- 실제로 DB에 테이블을 만든다. 

```zsh
rails generate migration add_<column_name>_to_<table_name> <column_name>:<data_type>
```
- 지정한 table에 column을 추가한다. 