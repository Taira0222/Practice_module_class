## レベル1（基礎的な理解）
### 問題1:
新しいモジュールGreetingsを定義し、その中にメソッドhelloを作成して「Hello, World!」と出力するコードを書きなさい。

解答1:

```ruby
module Greetings
  def self.hello
    puts "Hello, World!"
  end
end

# メソッドの呼び出し
Greetings.hello  # 出力: Hello, World!
```
#### 説明:
Greetingsモジュールを定義し、helloメソッドをモジュールメソッドとして定義するためにself.helloとしました。このメソッドを呼び出すには、Greetings.helloとします。

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
#### 解答2:

```ruby
module MathOperations
  def add(a, b)
    a + b
  end
end

class Calculator
  include MathOperations  # ミックスインを追加
end

calc = Calculator.new
puts calc.add(5, 3)  # 出力: 8
```
#### 説明:
CalculatorクラスにMathOperationsモジュールをミックスインするために、include MathOperationsを追加します。これにより、Calculatorのインスタンスでaddメソッドが使用可能になります。

## レベル2（モジュールの定数とメソッド）
### 問題1:
モジュールConstantsを定義し、その中に円周率を表す定数PIを3.14159として定義しなさい。また、PIを出力するコードを書きなさい。

解答1:

```ruby
module Constants
  PI = 3.14159
end

# 定数の出力
puts Constants::PI  # 出力: 3.14159
```
#### 説明:
Constantsモジュール内に定数PIを定義し、名前空間演算子::を用いてPIを参照・出力します。

### 問題2:
以下のモジュールUtilitiesにクラスメソッドgreetを追加し、「こんにちは！」と出力するようにしなさい。

```ruby
module Utilities
  # クラスメソッドgreetを定義
end

Utilities.greet  # 出力: こんにちは！
```
### 解答2:
```ruby
module Utilities
  def self.greet
    puts "こんにちは！"
  end
end

# クラスメソッドの呼び出し
Utilities.greet  # 出力: こんにちは！
```

#### 説明:
Utilitiesモジュールにクラスメソッドとしてgreetを定義するために、self.greetとします。これにより、Utilities.greetでメソッドを呼び出せます。

## レベル3（ミックスインとインスタンスメソッド）
### 問題1:
モジュールFlyableを定義し、その中にインスタンスメソッドflyを作成して「飛んでいます！」と出力するコードを書きなさい。その後、クラスBirdにこのモジュールをミックスインし、flyメソッドを呼び出しなさい。

#### 解答1:

```ruby
module Flyable
  def fly
    puts "飛んでいます！"
  end
end

class Bird
  include Flyable  # ミックスイン
end

bird = Bird.new
bird.fly  # 出力: 飛んでいます！
```
#### 説明:
Flyableモジュールにインスタンスメソッドflyを定義し、Birdクラスにinclude Flyableでミックスインします。これにより、Birdのインスタンスでflyメソッドが使用可能になります。

問題2:
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
#### 解答2:

```ruby
module Swimmable
  def swim
    puts "泳いでいます！"
  end
end

class Fish
  include Swimmable  # ミックスインを追加
end

nemo = Fish.new
nemo.swim  # 出力: 泳いでいます！
```
#### 説明:
Swimmableモジュールにswimメソッドを定義し、Fishクラスにinclude Swimmableでミックスインします。これにより、Fishのインスタンスでswimメソッドが使用可能になります。

## レベル4（ネストしたモジュールと名前空間）
### 問題1:
モジュールAnimalsの中にモジュールMammalsをネストし、その中にクラスDogを定義して、メソッドspeakが「ワンワン」と出力するようにしなさい。Dogクラスのインスタンスを作成し、speakメソッドを呼び出しなさい。

#### 解答1:

```ruby
module Animals
  module Mammals
    class Dog
      def speak
        puts "ワンワン"
      end
    end
  end
end

dog = Animals::Mammals::Dog.new
dog.speak  # 出力: ワンワン
```
#### 説明:
Animalsモジュール内にMammalsモジュールをネストし、その中にDogクラスを定義します。Dogクラスにspeakメソッドを定義し、名前空間を通じてクラスにアクセスします。

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
#### 解答2:

```ruby
module Vehicles
  module Land
    class Car
      def drive
        puts "運転しています"
      end
    end
  end
end

car = Vehicles::Land::Car.new
car.drive  # 出力: 運転しています
```
#### 説明:
Vehiclesモジュール内にLandモジュールをネストし、その中にCarクラスを定義します。Carクラスにdriveメソッドを定義し、指定された名前空間を通じてアクセスします。

## レベル5（高度なモジュール使用法）
### 問題1:
モジュールSingletonLoggerを作成し、シングルトンパターンを利用してログメッセージを記録するメソッドlogを定義しなさい。logメソッドは受け取ったメッセージをコンソールに出力します。SingletonLoggerを使用して「アプリケーションが開始されました」というメッセージをログに記録しなさい。

#### 解答1:
```ruby
require 'singleton'

module SingletonLogger
  include Singleton

  def log(message)
    puts "[LOG]: #{message}"
  end
end

# シングルトンインスタンスの取得と使用
logger = SingletonLogger.instance
logger.log("アプリケーションが開始されました")  # 出力: [LOG]: アプリケーションが開始されました
```
#### 説明:
RubyのSingletonモジュールを利用してSingletonLoggerをシングルトンとして定義します。これにより、SingletonLogger.instanceで唯一のインスタンスにアクセスできます。logメソッドを定義し、メッセージをコンソールに出力します。

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
#### 解答2:

```ruby
module EnumerableExtensions
  def second
    self[1]  # 配列のインデックスは0から始まるため、2番目の要素はインデックス1
  end
end

class Array
  include EnumerableExtensions
end

arr = [10, 20, 30, 40]
puts arr.second  # 出力: 20
```
#### 説明:
EnumerableExtensionsモジュールにsecondメソッドを定義し、self[1]で配列の2番目の要素を返します。Arrayクラスにinclude EnumerableExtensionsでミックスインし、Arrayのインスタンスでsecondメソッドを使用可能にします。