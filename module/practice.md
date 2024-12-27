## レベル1（基礎的な理解）
### 問題1:
新しいモジュールGreetingsを定義し、その中にメソッドhelloを作成して「Hello, World!」と出力するコードを書きなさい。

### 問題2:
以下のコードに不足している部分を補い、モジュールMathOperationsをクラスCalculatorにミックスインしてaddメソッドを使用できるようにしなさい。

```ruby
module MathOperations
  def add(a, b)
    a + b
  end
end

class Calculator
  # ここにミックスインのコードを追加
end

calc = Calculator.new
puts calc.add(5, 3)  # 出力: 8
```
## レベル2（モジュールの定数とメソッド）
### 問題1:
モジュールConstantsを定義し、その中に円周率を表す定数PIを3.14159として定義しなさい。また、PIを出力するコードを書きなさい。

### 問題2:
以下のモジュールUtilitiesにクラスメソッドgreetを追加し、「こんにちは！」と出力するようにしなさい。

```ruby
module Utilities
  # クラスメソッドgreetを定義
end

Utilities.greet  # 出力: こんにちは！
```
## レベル3（ミックスインとインスタンスメソッド）
### 問題1:
モジュールFlyableを定義し、その中にインスタンスメソッドflyを作成して「飛んでいます！」と出力するコードを書きなさい。その後、クラスBirdにこのモジュールをミックスインし、flyメソッドを呼び出しなさい。

### 問題2:
以下のモジュールSwimmableを定義し、swimメソッドを追加しなさい。そして、クラスFishにこのモジュールをミックスインして、swimメソッドを使用できるようにしなさい。

```ruby
module Swimmable
  # swimメソッドを定義
end

class Fish
  # ミックスインのコードを追加
end

nemo = Fish.new
nemo.swim  # 出力: （適切なメッセージ）
```
## レベル4（ネストしたモジュールと名前空間）
### 問題1:
モジュールAnimalsの中にモジュールMammalsをネストし、その中にクラスDogを定義して、メソッドspeakが「ワンワン」と出力するようにしなさい。Dogクラスのインスタンスを作成し、speakメソッドを呼び出しなさい。

### 問題2:
以下の名前空間を使用して、モジュールVehicles::Land内にクラスCarを定義し、driveメソッドで「運転しています」と出力するコードを書きなさい。その後、Carクラスのインスタンスを作成してdriveメソッドを呼び出しなさい。

```ruby
module Vehicles
  module Land
    # クラスCarを定義
  end
end

car = Vehicles::Land::Car.new
car.drive  # 出力: 運転しています
```
## レベル5（高度なモジュール使用法）
### 問題1:
モジュールSingletonLoggerを作成し、シングルトンパターンを利用してログメッセージを記録するメソッドlogを定義しなさい。logメソッドは受け取ったメッセージをコンソールに出力します。SingletonLoggerを使用して「アプリケーションが開始されました」というメッセージをログに記録しなさい。

### 問題2:
モジュールEnumerableExtensionsを定義し、Arrayクラスにミックスインして新しいメソッドsecondを追加しなさい。secondメソッドは配列の2番目の要素を返します。以下のコードが正しく動作するように実装しなさい。


```ruby
module EnumerableExtensions
  # secondメソッドを定義
end

class Array
  include EnumerableExtensions
end

arr = [10, 20, 30, 40]
puts arr.second  # 出力: 20
```
