# Dart 비동기 프로그래밍
비동기 작업은 다른 작업이 끝나는 것을 기다리는 동안에도 프로그램이 실행되도록 해 준다. 비동기 작업의 예로는 아래와 같은 것들이 있다. 
- 네트워크에서 데이터를 가져오기
- 데이터베이스에 데이터를 쓰기
- 파일로부터 데이터를 읽어오기
Dart에서는 비동기 작업을 구현하기위해 `Future` 클래스와 `async`, `await` 키워드를 사용할 수 있다. 

## futures
`future`는 클래스 `Future`의 인스턴스이다. future는 비동기 작업의 결과를 나타내며 미완료와 완료의 총 두 가지 상태를 가질 수 있다. 

**미완료**

어떤 비동기 함수를 호출하면, 그 함수는 미완료된 future를 반환한다. 이 future는 비동기 작업이 끝나기를 기다리거나 에러를 일으킨다. 

**완료**

만약 비동기 작업이 성공한다면, future는 값을 반환하며 완료된다. 아닐 경우 에러를 발생시키며 완료된다. 

**값을 반환하며 완료되는 경우**

`Future<T>`타입의 경우 future는 T를 반환하며 완료된다. 만약 future가 사용 가능한 값을 반환하지 않으면 그 future의 타입은 `Future<void>`이다. 

**에러를 일으키며 완료되는 경우**

함수에 의해 실행된 비동기 작업이 어떠한 이유로든 실패한다면 future는 에러와 함께 완료된다. 

### 사용 예시
```dart
Future<void> fetchUserOrder() {
  // Imagine that this function is fetching user info from another service or database.
  return Future.delayed(Duration(seconds: 2), () => print('Large Latte'));
}

void main() {
  fetchUserOrder();
  print('Fetching user order...');
}
```

## async와 await
`async`와 `await` 키워드는 선언적인 방법으로 비동기 함수를 정의하고 그 결과를 사용하는 것을 가능하게 한다. 

**사용법**

- async 함수를 이용하기 위해서는 `async`를 함수의 body 이전에 선언해 주어야 한다. 
- `await`은 async 함수에서만 사용 가능하다. 

### 사용 예시
```dart
Future<String> createOrderMessage() async {
  var order = await fetchUserOrder();
  return 'Your order is: $order';
}

Future<String> fetchUserOrder() =>
    // Imagine that this function is more complex and slow.
    Future.delayed(
      Duration(seconds: 2),
      () => 'Large Latte',
    );

Future<void> main() async {
  print('Fetching user order...');
  print(await createOrderMessage());
}
```