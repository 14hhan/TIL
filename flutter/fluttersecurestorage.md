# FlutterSecureStorage
secure storage에 데이터를 저장해놓기 위한 플러터 플러그인이다. 
## 사용 예시
```dart
import 'package:flutter_secure_storage/flutter_secure_storage.dart';

// Create storage
final storage = new FlutterSecureStorage();
// Read value 
String value = await storage.read(key: key);
// Read all values
Map<String, String> allValues = await storage.readAll();
// Delete value 
await storage.delete(key: key);
// Delete all 
await storage.deleteAll();
// Write value 
await storage.write(key: key, value: value);
```