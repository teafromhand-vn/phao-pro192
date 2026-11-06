# PRO192 Java Practical Exam – Comprehensive Cheat Sheet
## Sổ tay tra cứu theo keyword tiếng Anh → cách hiểu → câu lệnh Java → code mẫu

> **Mục tiêu:** Khi đọc đề tiếng Anh, tìm keyword (ví dụ *remove the last character of each word*, *sum prices of all items whose type contains more uppercase than lowercase letters*), tra đúng mục và lấy pattern code để sửa theo tên class/field/điều kiện của đề.
>
> **Nguồn và phạm vi**
>
> - Các dạng được đánh dấu **[ĐÃ XUẤT HIỆN TRONG ĐỀ MẪU]** được rút ra từ 8 PDF PRO192 bạn đã gửi.
> - Các dạng được đánh dấu **[MỞ RỘNG – CÓ THỂ DÙNG]** là cú pháp/thuật toán Java phổ biến có thể giúp xử lý biến thể đề thực hành. Không có nghĩa chắc chắn đã xuất hiện hoặc chắc chắn sẽ thi.
> - Đề đang thi luôn là nguồn quyết định cuối cùng: làm đúng method signature, điều kiện, ngưỡng, thứ tự xử lý và format output được ghi trong đề.
>
> **Môi trường:** Ưu tiên cú pháp tương thích Java 8/JDK 1.8. Tránh dùng API chỉ có ở Java mới hơn nếu không chắc phòng thi hỗ trợ.

---

# MỤC LỤC TRA CỨU

> **Cách đọc:** các bảng keyword/cú pháp là mục lục tra nhanh. Khi cần làm bài, xem phần **Case Cookbook** ở cuối tài liệu: mỗi tình huống có một block code hoàn chỉnh (method/class), không chỉ có một dòng biểu thức.

1. [Tra cứu keyword tiếng Anh nhanh](#1-tra-cứu-keyword-tiếng-anh-nhanh)
2. [Đọc UML và dựng class nhanh](#2-đọc-uml-và-dựng-class-nhanh)
3. [String – thư viện biến đổi chuỗi](#3-string--thư-viện-biến-đổi-chuỗi)
4. [Character – đếm và phân loại ký tự](#4-character--đếm-và-phân-loại-ký-tự)
5. [Number – xử lý chữ số và thuật toán số](#5-number--xử-lý-chữ-số-và-thuật-toán-số)
6. [Condition – điều kiện và công thức](#6-condition--điều-kiện-và-công-thức)
7. [List/ArrayList – thư viện xử lý danh sách](#7-listarraylist--thư-viện-xử-lý-danh-sách)
8. [Inheritance – kế thừa và override](#8-inheritance--kế-thừa-và-override)
9. [Interface – implement và xử lý method](#9-interface--implement-và-xử-lý-method)
10. [Array – mảng một chiều](#10-array--mảng-một-chiều)
11. [Input, output, formatting, utility methods](#11-input-output-formatting-utility-methods)
12. [NetBeans – thao tác IDE và workflow phòng thi](#12-netbeans--thao-tác-ide-và-workflow-phòng-thi)
13. [Lỗi compile/runtime và cách sửa](#13-lỗi-compileruntime-và-cách-sửa)
14. [Boundary tests – kiểm tra trường hợp biên](#14-boundary-tests--kiểm-tra-trường-hợp-biên)
15. [Các pattern xác nhận từ 8 đề đã gửi](#15-các-pattern-xác-nhận-từ-8-đề-đã-gửi)
16. [Checklist 90 phút](#16-checklist-90-phút)
17. [Case Cookbook – code theo từng tình huống](#46-class--full-code-cho-từng-case)
18. [Bổ sung biến thể kế thừa và kiểm tra cú pháp](#58-bổ-sung-biến-thể-kế-thừa-và-kiểm-tra-cú-pháp)
19. [Độ dài chuỗi – toàn bộ thao tác](#59-độ-dài-chuỗi-string-length--toàn-bộ-thao-tác)

---

# 1. TRA CỨU KEYWORD TIẾNG ANH NHANH

Đây là mục nên dùng đầu tiên khi nhìn đề. Tìm cụm tiếng Anh, xác định hành động, rồi chuyển sang câu lệnh.

## 1.1. Từ khóa so sánh và điều kiện

| Keyword trong đề | Nghĩa | Java |
|---|---|---|
| greater than | lớn hơn | `a > b` |
| more than | nhiều hơn/lớn hơn | `a > b` |
| less than | nhỏ hơn | `a < b` |
| fewer than | ít hơn | `a < b` |
| greater than or equal to | lớn hơn hoặc bằng | `a >= b` |
| at least | ít nhất | `a >= b` |
| no less than | không ít hơn | `a >= b` |
| less than or equal to | nhỏ hơn hoặc bằng | `a <= b` |
| at most | nhiều nhất | `a <= b` |
| no more than | không nhiều hơn | `a <= b` |
| equal to | bằng | `a == b` |
| exactly | chính xác bằng | `a == b` |
| not equal to | khác | `a != b` |
| between x and y | nằm trong khoảng | `a >= x && a <= y` |
| either ... or ... | một trong hai | `cond1 || cond2` |
| both ... and ... | cả hai | `cond1 && cond2` |
| neither ... nor ... | không cái nào | `!cond1 && !cond2` |
| otherwise | nếu không | `else` |
| if ... | nếu | `if (...)` |
| unless ... | trừ khi | điều kiện phủ định; đọc kỹ ngữ cảnh |
| divisible by | chia hết cho | `n % d == 0` |
| not divisible by | không chia hết | `n % d != 0` |
| positive | dương | `n > 0` |
| negative | âm | `n < 0` |
| non-negative | không âm | `n >= 0` |
| even | chẵn | `n % 2 == 0` |
| odd | lẻ | `n % 2 != 0` |

**Cẩn thận các cặp dễ nhầm:**

| Đề ghi | Đúng | Không phải |
|---|---|---|
| at least 5 | `>= 5` | `> 5` |
| more than 5 | `> 5` | `>= 5` |
| at most 5 | `<= 5` | `< 5` |
| less than 5 | `< 5` | `<= 5` |
| exactly 5 | `== 5` | `>= 5` |

## 1.2. Từ khóa số lượng, thống kê

| Keyword | Ý nghĩa | Pattern |
|---|---|---|
| sum / total | tổng | `sum += value;` |
| count / number of | đếm số lượng | `count++;` |
| frequency | tần suất/số lần xuất hiện | tăng counter khi khớp |
| average / average value | trung bình | `(double) sum / count` |
| maximum / largest / highest | lớn nhất | so sánh `>` |
| minimum / smallest / lowest | nhỏ nhất | so sánh `<` |
| range | khoảng max - min | `max - min` |
| number of digits | số chữ số | `String.valueOf(n).length()` hoặc loop |
| distinct / different / unique | khác nhau/không trùng | mảng đánh dấu hoặc Set |
| duplicate / repeated | trùng/lặp | kiểm tra đã xuất hiện |
| all | tất cả | duyệt toàn bộ |
| any | ít nhất một | tìm thấy thì có thể dừng |
| each / every | từng/mỗi | loop |
| first | đầu tiên | index từ trái sang phải |
| last | cuối cùng | index cuối hoặc duyệt ngược |
| longest | dài nhất | max `length()` |
| shortest | ngắn nhất | min `length()` |
| most | nhiều nhất | tìm max của số đếm |
| least / fewest | ít nhất | tìm min của số đếm |

## 1.3. Từ khóa String

| Keyword | Nghĩa | Java |
|---|---|---|
| character / char | ký tự | `char` |
| first character | ký tự đầu tiên | `s.charAt(0)` |
| last character | ký tự cuối cùng | `s.charAt(s.length()-1)` |
| first letter | chữ cái đầu | thường `charAt(0)` nếu đề đảm bảo chữ |
| first alphabetic character | ký tự chữ cái đầu tiên | loop + `Character.isLetter()` |
| each character | từng ký tự | loop `i < s.length()` |
| each word | từng từ | `split()` + loop |
| first character of each word | ký tự đầu mỗi từ | `word.charAt(0)` |
| last character of each word | ký tự cuối mỗi từ | `word.charAt(word.length()-1)` |
| uppercase / capital letter | chữ hoa | `Character.isUpperCase()` |
| lowercase | chữ thường | `Character.isLowerCase()` |
| letter / alphabetic | chữ cái | `Character.isLetter()` |
| digit / numeric character | chữ số | `Character.isDigit()` |
| non-letter | không phải chữ cái | `!Character.isLetter(c)` |
| contains | chứa | `s.contains(x)` |
| starts with / begins with | bắt đầu bằng | `s.startsWith(x)` |
| ends with | kết thúc bằng | `s.endsWith(x)` |
| replace | thay thế | `replace()` hoặc substring + nối |
| remove / delete | xóa | substring / loop / remove list |
| append | nối thêm vào cuối | `+=` hoặc `StringBuilder.append()` |
| prepend | nối thêm vào đầu | `prefix + s` |
| concatenate | nối chuỗi | `a + b` |
| reverse | đảo ngược | `StringBuilder.reverse()` |
| extract | trích/lấy ra | `substring()` |
| split / separate | tách | `split()` |
| trim | bỏ khoảng trắng đầu/cuối | `trim()` |
| ignore case / case-insensitive | không phân biệt hoa thường | `equalsIgnoreCase()` hoặc lowercase |
| case-sensitive | phân biệt hoa thường | `equals()` / method thường |

## 1.4. Từ khóa List/Collection

| Keyword | Nghĩa | Java |
|---|---|---|
| list of objects | danh sách object | `List<Type>` |
| add / insert | thêm | `list.add(x)` |
| get / retrieve | lấy phần tử | `list.get(i)` |
| update / modify / set | cập nhật | `list.set(i, x)` hoặc setter của object |
| remove / delete | xóa | `list.remove(i)` / `Iterator.remove()` |
| clear all | xóa hết | `list.clear()` |
| sort ascending | sắp tăng | Comparator thuận |
| sort descending | sắp giảm | Comparator đảo |
| in ascending order | theo thứ tự tăng | Comparator thuận |
| in descending order | theo thứ tự giảm | Comparator đảo |
| search / find | tìm kiếm | loop + điều kiện |
| minimum price | giá nhỏ nhất | min loop |
| maximum price | giá lớn nhất | max loop |
| whose ... | những object mà ... | `if (object.field meets condition)` |
| satisfying the condition | thỏa điều kiện | `if (condition)` |
| remove all items whose ... | xóa tất cả phần tử mà ... | duyệt ngược/Iterator |
| keep the original order | giữ thứ tự ban đầu | không sort; append các item hợp lệ |
| first matching item | phần tử đầu tiên khớp | loop + `break` |
| all matching items | tất cả phần tử khớp | duyệt hết |

## 1.5. Từ khóa OOP và method

| Keyword | Nghĩa | Java |
|---|---|---|
| field / attribute | thuộc tính | biến khai báo trong class |
| constructor | hàm khởi tạo | tên trùng class, không return type |
| default constructor | constructor không tham số | `ClassName()` |
| parameterized constructor | constructor có tham số | `ClassName(args)` |
| getter / accessor | lấy field | `return field;` |
| setter / mutator | cập nhật field | `this.field = value;` |
| superclass / parent class | lớp cha | class được kế thừa |
| subclass / child class | lớp con | `extends Parent` |
| inherit / inheritance | kế thừa | `extends` |
| implement an interface | triển khai interface | `implements Interface` |
| override | ghi đè method | `@Override` |
| call parent constructor | gọi constructor cha | `super(args)` |
| return a String | trả chuỗi | return type `String` |
| string of format / String in the format | trả về một chuỗi theo format chỉ định | ghép field bằng `+`, giữ đúng thứ tự/ký tự phân cách |
| do not format | không format | nối/trả giá trị nguyên trạng |
| without spaces | không có khoảng trắng | không thêm `" "` |
| separated by comma | phân tách bằng dấu phẩy | `a + "," + b` |
| two decimal places | 2 chữ số thập phân | `String.format("%.2f", x)` |

---

# 2. ĐỌC UML VÀ DỰNG CLASS NHANH

## 2.1. UML → Java

| UML | Java |
|---|---|
| `+` | `public` |
| `-` | `private` |
| `#` | `protected` |
| `name: String` | `String name;` |
| `price: int` | `int price;` |
| `getName(): String` | `public String getName()` |
| `setPrice(price:int): void` | `public void setPrice(int price)` |
| `Person()` | `public Person()` |
| `Person(name:String, age:int)` | `public Person(String name, int age)` |
| `toString(): String` | `public String toString()` |

## 2.2. Khung class

```java
public class Product {
    private String name;
    private int price;

    public Product() {
        name = "";
        price = 0;
    }

    public Product(String name, int price) {
        this.name = name;
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getPrice() {
        return price;
    }

    public void setPrice(int price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return name + "," + price;
    }
}
```

## 2.3. Generate Code trong NetBeans

Dùng IDE cho phần lặp lại:
- Generate default constructor.
- Generate constructor từ fields.
- Generate getters/setters.
- Generate `toString()` nếu phù hợp, nhưng phải kiểm tra output format.
- Generate/implement abstract methods khi class implements interface hoặc extends abstract class.

**Lưu ý phím tắt:** trong NetBeans thường có `Alt + Insert` để mở Generate Code. `Alt + Enter` thường hiển thị editor hints/fix tùy vị trí và keymap. Nếu máy bạn đã quen thao tác khác, dùng menu **Source → Insert Code** để tìm đúng chức năng.

**Không tin tuyệt đối code IDE sinh ra:**
- Setter mặc định chỉ gán field, không biết yêu cầu cộng dồn hay kiểm tra ngưỡng.
- `toString()` tự sinh có thể thêm tên field/dấu ngoặc/format không giống đề.
- Constructor tự sinh không tự áp dụng rule như `refresh < 0` thì set về 0.

## 2.4. Constructor

### Default constructor

```java
public Product() {
    name = "";
    price = 0;
}
```

### Parameterized constructor

```java
public Product(String name, int price) {
    this.name = name;
    this.price = price;
}
```

### Constructor gọi constructor khác cùng class

```java
public Product() {
    this("", 0);
}
```

`this(...)` phải là câu lệnh đầu tiên trong constructor.

### Constructor lớp con

```java
public SpecialProduct(String name, int price, int quantity) {
    super(name, price);
    this.quantity = quantity;
}
```

## 2.5. Getter / Setter – mẫu và biến thể

```java
public int getPrice() {
    return price;
}

public void setPrice(int price) {
    this.price = price;
}
```

Cộng dồn:

```java
public void setPrice(int value) {
    price += value;
}
```

Cập nhật theo công thức:

```java
public void setAge(int newAge) {
    age = newAge + name.length();
}
```

Có điều kiện:

```java
public void setRefresh(double value) {
    if (value < 0) {
        refresh = 0;
    } else {
        refresh = value;
    }
}
```

---

# 3. STRING – THƯ VIỆN BIẾN ĐỔI CHUỖI

> Quy tắc: String index bắt đầu từ `0`; `substring(begin, end)` lấy từ begin đến trước end.

## 3.1. String methods cần nhớ

> **Phân biệt độ dài – rất dễ gây lỗi compile:**
> - Mảng (`int[]`, `char[]`, `String[]`): dùng `a.length` (**không có ngoặc**).
> - `String`: dùng `s.length()` (**có ngoặc**).
> - `StringBuilder`: dùng `sb.length()` (**có ngoặc**).
> - `List`: dùng `list.size()` (**có ngoặc**).


| Method | Tác dụng | Ví dụ |
|---|---|---|
| `s.length()` | độ dài | `"Java".length()` → 4 |
| `s.charAt(i)` | ký tự ở index | `"Java".charAt(0)` → J |
| `s.substring(i)` | từ i đến hết | `"Java".substring(1)` → ava |
| `s.substring(i,j)` | i đến trước j | `"Java".substring(0,2)` → Ja |
| `s.indexOf(x)` | index đầu của x; không có → -1 | `"banana".indexOf("na")` → 2 |
| `s.lastIndexOf(x)` | index cuối của x | `"banana".lastIndexOf("na")` → 4 |
| `s.contains(x)` | có chứa x? | boolean |
| `s.startsWith(x)` | bắt đầu bằng x? | boolean |
| `s.endsWith(x)` | kết thúc bằng x? | boolean |
| `s.equals(x)` | so sánh nội dung | boolean |
| `s.equalsIgnoreCase(x)` | so sánh không phân biệt hoa thường | boolean |
| `s.toUpperCase()` | chuyển hoa | String mới |
| `s.toLowerCase()` | chuyển thường | String mới |
| `s.trim()` | bỏ space đầu/cuối | String mới |
| `s.replace(a,b)` | thay tất cả ký tự/chuỗi khớp | String mới |
| `s.replaceAll(regex,repl)` | thay theo regex | String mới |
| `s.split(" ")` | tách theo space | String[] |
| `String.join(" ", arr)` | nối các phần tử bằng space | String |
| `String.valueOf(x)` | đổi thành String | String |
| `s.isEmpty()` | chuỗi rỗng? | boolean |

`String` là immutable: những method như `toUpperCase()`, `replace()` không sửa chuỗi cũ; phải gán lại hoặc return kết quả.

## 3.2. Lấy / bỏ / thay ký tự đầu và cuối

### Lấy ký tự đầu

```java
char first = s.charAt(0);
```

### Lấy ký tự cuối

```java
char last = s.charAt(s.length() - 1);
```

### Bỏ ký tự đầu

```java
s = s.substring(1);
```

### Bỏ ký tự cuối

```java
s = s.substring(0, s.length() - 1);
```

### Thay ký tự đầu bằng `newChar`

```java
s = newChar + s.substring(1);
```

### Thay ký tự cuối bằng `newChar`

```java
s = s.substring(0, s.length() - 1) + newChar;
```

### Thay ký tự tại index `i`

```java
s = s.substring(0, i) + newChar + s.substring(i + 1);
```

**[ĐÃ XUẤT HIỆN TRONG ĐỀ MẪU]** Các yêu cầu đổi biến thể giữa:
- Bỏ ký tự đầu hoặc cuối của name.
- Thay ký tự đầu tiên là alphabetic character trong type.
- Thay ký tự đầu/cuối mỗi từ.

## 3.3. Viết hoa / viết thường

### Toàn bộ chuỗi viết hoa

```java
s = s.toUpperCase();
```

Keyword: `uppercase`, `capital letters`, `convert to upper case`.

### Toàn bộ chuỗi viết thường

```java
s = s.toLowerCase();
```

Keyword: `lowercase`, `convert to lower case`.

### Chữ đầu hoa, phần còn lại thường

```java
if (s != null && !s.isEmpty()) {
    s = s.substring(0, 1).toUpperCase()
      + s.substring(1).toLowerCase();
}
```

Keyword: `first letter capitalized`, `rest lowercase`.

### Đổi mỗi ký tự sang uppercase

```java
for (int i = 0; i < s.length(); i++) {
    char c = Character.toUpperCase(s.charAt(i));
}
```

## 3.4. Thay ký tự đầu tiên là chữ cái (first alphabetic character)

Đây **không giống** first character. Ví dụ `type = "12standard"`: ký tự đầu tiên là `'1'`, alphabetic character đầu tiên là `'s'`.

```java
int pos = -1;

for (int i = 0; i < s.length(); i++) {
    if (Character.isLetter(s.charAt(i))) {
        pos = i;
        break;
    }
}

if (pos != -1) {
    s = s.substring(0, pos)
      + newChar
      + s.substring(pos + 1);
}
```

Keyword: `first alphabetic character`, `first letter in the string`.

## 3.5. Tách chuỗi thành từ

### Đề đảm bảo đúng một space giữa các từ

```java
String[] words = s.split(" ");
```

### Đề có thể có nhiều khoảng trắng liên tiếp

```java
String[] words = s.trim().split("\\s+");
```

`\\s+` là regex cho một hoặc nhiều whitespace. Chỉ dùng nếu phù hợp quy tắc input; nếu đề nói delimiter là đúng một space thì `split(" ")` bám sát đề hơn.

### Duyệt từng từ

```java
for (String word : words) {
    // process word
}
```

### Ghép từ lại bằng một space

```java
String result = String.join(" ", words);
```

## 3.6. Biến đổi từng từ

### Thay ký tự đầu mỗi từ

```java
String[] words = s.split(" ");

for (int i = 0; i < words.length; i++) {
    String w = words[i];

    if (!w.isEmpty()) {
        words[i] = newChar + w.substring(1);
    }
}

s = String.join(" ", words);
```

### Thay ký tự cuối mỗi từ

```java
String[] words = s.split(" ");

for (int i = 0; i < words.length; i++) {
    String w = words[i];

    if (!w.isEmpty()) {
        words[i] = w.substring(0, w.length() - 1) + newChar;
    }
}

s = String.join(" ", words);
```

### Bỏ ký tự đầu mỗi từ

```java
String[] words = s.split(" ");

for (int i = 0; i < words.length; i++) {
    if (!words[i].isEmpty()) {
        words[i] = words[i].substring(1);
    }
}

s = String.join(" ", words);
```

### Bỏ ký tự cuối mỗi từ

```java
String[] words = s.split(" ");

for (int i = 0; i < words.length; i++) {
    String w = words[i];

    if (!w.isEmpty()) {
        words[i] = w.substring(0, w.length() - 1);
    }
}

s = String.join(" ", words);
```

### Viết hoa chữ cái đầu mỗi từ

```java
String[] words = s.split(" ");

for (int i = 0; i < words.length; i++) {
    String w = words[i];

    if (!w.isEmpty()) {
        words[i] = w.substring(0, 1).toUpperCase()
                   + w.substring(1);
    }
}

s = String.join(" ", words);
```

### Viết thường chữ cái đầu mỗi từ

```java
String[] words = s.split(" ");

for (int i = 0; i < words.length; i++) {
    String w = words[i];

    if (!w.isEmpty()) {
        words[i] = w.substring(0, 1).toLowerCase()
                   + w.substring(1);
    }
}

s = String.join(" ", words);
```

**[ĐÃ XUẤT HIỆN TRONG ĐỀ MẪU]** Một đề yêu cầu thay ký tự cuối của mỗi từ trong `type` bằng ký tự đầu của `price`; đề khác yêu cầu thay ký tự đầu mỗi từ bằng ký tự đầu của `price`.

## 3.7. Đếm số từ (count words)

```java
public int countWords(String s) {
    if (s == null || s.trim().isEmpty()) {
        return 0;
    }

    return s.trim().split("\\s+").length();
}
```

Nếu đề đảm bảo đúng một space:

```java
return s.isEmpty() ? 0 : s.split(" ").length();
```

Keyword: `number of words`, `count words`, `how many words`.

## 3.8. Đảo ngược chuỗi (reverse string)

Cách ngắn:

```java
String reversed = new StringBuilder(s).reverse().toString();
```

Cách dùng loop:

```java
String reversed = "";

for (int i = s.length() - 1; i >= 0; i--) {
    reversed += s.charAt(i);
}
```

Keyword: `reverse the string`, `characters in reverse order`.

## 3.9. Nối chuỗi (concatenate / append / prepend)

Nối vào cuối:

```java
s = s + extra;
// hoặc
s += extra;
```

Nối vào đầu:

```java
s = prefix + s;
```

Nối nhiều field không có space:

```java
return name + "," + price + "," + quantity;
```

Keyword:
- `append` → nối thêm vào cuối.
- `prepend` → thêm vào đầu.
- `concatenate` → ghép chuỗi.
- `without spaces` → không tự thêm `" "`.

## 3.10. Thay thế (replace)

Thay tất cả ký tự `'a'` thành `'x'`:

```java
s = s.replace('a', 'x');
```

Thay chuỗi con `"cat"` thành `"dog"`:

```java
s = s.replace("cat", "dog");
```

Xóa tất cả space:

```java
s = s.replace(" ", "");
```

Xóa tất cả dấu `-`:

```java
s = s.replace("-", "");
```

Keyword: `replace`, `replace all`, `remove all occurrences`.

## 3.11. Tìm chuỗi con / tiền tố / hậu tố

```java
s.contains("abc");      // contains
s.startsWith("ab");    // prefix
s.endsWith("xyz");     // suffix
s.indexOf("ab") >= 0;  // contains (index)
s.indexOf("ab") == -1; // does not contain
```

Keyword:
- `contains`: chứa ở bất kỳ vị trí nào.
- `starts with`: bắt đầu bằng.
- `ends with`: kết thúc bằng.
- `does not contain`: `!s.contains(x)`.

## 3.12. So sánh String

```java
s.equals(other);              // phân biệt hoa thường
s.equalsIgnoreCase(other);    // không phân biệt hoa thường
s.compareTo(other);           // thứ tự từ điển
```

Không dùng `==` để so sánh nội dung String:

```java
if (s.equals("Java")) {
    // ...
}
```

Keyword: `same string`, `equal`, `identical text`, `ignore case`.

## 3.13. Lọc từ theo điều kiện (filter words)

Ví dụ: giữ lại từ có số chữ cái khác số ký tự không phải chữ cái, giữ nguyên thứ tự, cách nhau bởi đúng một space.

```java
public String filterWords(String s) {
    if (s == null || s.isEmpty()) {
        return "";
    }

    String[] words = s.split(" ");
    String result = "";

    for (String word : words) {
        int letters = 0;
        int nonLetters = 0;

        for (int i = 0; i < word.length(); i++) {
            char c = word.charAt(i);

            if (Character.isLetter(c)) {
                letters++;
            } else {
                nonLetters++;
            }
        }

        if (letters != nonLetters) {
            if (!result.isEmpty()) {
                result += " ";
            }

            result += word;
        }
    }

    return result;
}
```

Keyword:
- `filter words`
- `return a new string consisting of all words`
- `keep the original order`
- `separated by a single space`
- `no leading or trailing spaces`
- `return an empty string if no word satisfies`.

## 3.14. Acronym – chữ viết tắt

**[ĐÃ XUẤT HIỆN TRONG ĐỀ MẪU]**

Keyword: `build an acronym`, `first character of each word`, `convert to uppercase`.

```java
public String buildAcronym(String str) {
    if (str == null || str.isEmpty()) {
        return "";
    }

    String[] words = str.split(" ");
    String result = "";

    for (String word : words) {
        if (!word.isEmpty()) {
            char c = word.charAt(0);

            if ((c >= 'A' && c <= 'Z')
                    || (c >= 'a' && c <= 'z')) {
                result += Character.toUpperCase(c);
            }
        }
    }

    return result;
}
```

Ví dụ:
- `"object oriented programming"` → `"OOP"`
- `"Java virtual machine"` → `"JVM"`
- `"123 data structure"` → `"DS"`

## 3.15. Palindrome (chuỗi đọc xuôi/ngược giống nhau) – mở rộng

Keyword: `palindrome`, `reads the same forwards and backwards`.

```java
public boolean isPalindrome(String s) {
    int left = 0;
    int right = s.length() - 1;

    while (left < right) {
        if (s.charAt(left) != s.charAt(right)) {
            return false;
        }

        left++;
        right--;
    }

    return true;
}
```

Nếu đề yêu cầu bỏ qua hoa/thường:

```java
s = s.toLowerCase();
```

Nếu đề yêu cầu bỏ qua space thì cần chuẩn hóa trước; không tự bỏ nếu đề không yêu cầu.

---

# 4. CHARACTER – ĐẾM VÀ PHÂN LOẠI KÝ TỰ

## 4.1. Character methods

| Method | Ý nghĩa |
|---|---|
| `Character.isLetter(c)` | có phải chữ cái |
| `Character.isDigit(c)` | có phải chữ số |
| `Character.isUpperCase(c)` | chữ hoa |
| `Character.isLowerCase(c)` | chữ thường |
| `Character.isWhitespace(c)` | whitespace |
| `Character.toUpperCase(c)` | đổi char sang uppercase |
| `Character.toLowerCase(c)` | đổi char sang lowercase |

## 4.2. Đếm chữ hoa/chữ thường/chữ số/chữ cái

```java
int upper = 0;
int lower = 0;
int digits = 0;
int letters = 0;
int others = 0;

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (Character.isUpperCase(c)) upper++;
    if (Character.isLowerCase(c)) lower++;
    if (Character.isDigit(c)) digits++;
    if (Character.isLetter(c)) letters++;
    if (!Character.isLetter(c)) others++;
}
```

**Cẩn thận:** `nonLetters` bao gồm số, dấu câu, space... Nếu đề nói `non-alphabetic characters`, có thể hiểu là mọi ký tự không phải chữ cái.

## 4.3. Kiểm tra chuỗi có chứa chữ hoa/chữ thường/chữ số

Có ít nhất một chữ hoa:

```java
boolean hasUpper = false;

for (int i = 0; i < s.length(); i++) {
    if (Character.isUpperCase(s.charAt(i))) {
        hasUpper = true;
        break;
    }
}
```

Có ít nhất một chữ số:

```java
boolean hasDigit = false;

for (int i = 0; i < s.length(); i++) {
    if (Character.isDigit(s.charAt(i))) {
        hasDigit = true;
        break;
    }
}
```

Không có chữ số:

```java
if (!hasDigit) {
    // ...
}
```

Keyword: `at least one`, `contains an uppercase letter`, `contains no digit`.

## 4.4. Đếm số lần một ký tự xuất hiện (frequency)

```java
int count = 0;
char target = 'a';

for (int i = 0; i < s.length(); i++) {
    if (s.charAt(i) == target) {
        count++;
    }
}
```

Đếm không phân biệt hoa/thường:

```java
if (Character.toLowerCase(s.charAt(i))
        == Character.toLowerCase(target)) {
    count++;
}
```

## 4.5. Đếm số ký tự khác nhau (distinct characters)

```java
boolean[] seen = new boolean[65536];
int count = 0;

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (!seen[c]) {
        seen[c] = true;
        count++;
    }
}
```

Cách trên dùng mảng đánh dấu theo giá trị `char`; với đề cơ bản giới hạn ASCII, có thể dùng mảng nhỏ hơn, nhưng `65536` bao phủ miền `char` Java.

## 4.6. Đếm số chữ số khác nhau trong một từ

**[ĐÃ XUẤT HIỆN TRONG MỘT ĐỀ IString]**

```java
boolean[] seen = new boolean[10];
int differentDigits = 0;

for (int i = 0; i < word.length(); i++) {
    char c = word.charAt(i);

    if (Character.isDigit(c)) {
        int d = c - '0';

        if (!seen[d]) {
            seen[d] = true;
            differentDigits++;
        }
    }
}
```

Ví dụ:
- `"a112"` có 2 digit khác nhau: 1, 2.
- `"a111"` có 1 digit khác nhau: 1.
- `"ab"` có 0 digit khác nhau.

## 4.7. Kiểm tra từng điều kiện với boolean

```java
boolean hasLower = false;
boolean hasUpper = false;

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (Character.isLowerCase(c)) hasLower = true;
    if (Character.isUpperCase(c)) hasUpper = true;
}

if (hasLower && hasUpper) {
    // has both
}
```

---

# 5. NUMBER – XỬ LÝ CHỮ SỐ VÀ THUẬT TOÁN SỐ

## 5.1. Bảng phép toán chữ số

| Mục đích | Code |
|---|---|
| Lấy chữ số cuối | `n % 10` |
| Bỏ chữ số cuối | `n / 10` |
| Chữ số chẵn | `digit % 2 == 0` |
| Chữ số lẻ | `digit % 2 != 0` |
| Số chẵn | `n % 2 == 0` |
| Số lẻ | `n % 2 != 0` |
| Chia hết cho d | `n % d == 0` |
| Số chữ số | `String.valueOf(n).length()` |
| Trị tuyệt đối | `Math.abs(n)` |
| Chữ số đầu | `String.valueOf(n).charAt(0)` |
| Giá trị lớn hơn | `Math.max(a,b)` |
| Giá trị nhỏ hơn | `Math.min(a,b)` |

## 5.2. Duyệt từng chữ số bằng while

```java
while (n > 0) {
    int digit = n % 10;

    // process digit

    n /= 10;
}
```

**Ví dụ:** `n = 1234` thì digit lần lượt là 4, 3, 2, 1 (từ phải qua trái).

Nếu cần xử lý từ trái qua phải, chuyển thành String:

```java
String s = String.valueOf(n);

for (int i = 0; i < s.length(); i++) {
    int digit = s.charAt(i) - '0';
}
```

## 5.3. Đếm số chữ số

Cách dùng String:

```java
int count = String.valueOf(n).length();
```

Cách dùng toán học:

```java
int countDigits(int n) {
    if (n == 0) return 1;

    n = Math.abs(n);
    int count = 0;

    while (n > 0) {
        count++;
        n /= 10;
    }

    return count;
}
```

## 5.4. Đếm chữ số chẵn/lẻ

```java
int even = 0;
int odd = 0;

if (n == 0) {
    even = 1;
} else {
    n = Math.abs(n);

    while (n > 0) {
        int digit = n % 10;

        if (digit % 2 == 0) {
            even++;
        } else {
            odd++;
        }

        n /= 10;
    }
}
```

**[ĐÃ XUẤT HIỆN TRONG ĐỀ MẪU]** Các biến thể `weight` có ít nhất hai chữ số lẻ hoặc hai chữ số chẵn; nếu đạt điều kiện thì nối type với số lượng chữ số tương ứng, nếu không thì nối với tổng số chữ số.

## 5.5. Tính tổng chữ số (sum of digits)

```java
int sum = 0;

n = Math.abs(n);

while (n > 0) {
    sum += n % 10;
    n /= 10;
}
```

Trường hợp n = 0, tổng chữ số là 0.

## 5.6. Tính tích chữ số (product of digits)

```java
int product = 1;
int temp = Math.abs(n);

if (temp == 0) {
    product = 0;
} else {
    while (temp > 0) {
        product *= temp % 10;
        temp /= 10;
    }
}
```

## 5.7. Đảo ngược số nguyên (reverse number)

```java
int reverse = 0;
int temp = Math.abs(n);

while (temp > 0) {
    int digit = temp % 10;
    reverse = reverse * 10 + digit;
    temp /= 10;
}
```

Nếu phải giữ dấu âm:

```java
if (n < 0) {
    reverse = -reverse;
}
```

## 5.8. Chữ số đầu tiên/cuối cùng

Chữ số cuối:

```java
int lastDigit = n % 10;
```

Chữ số đầu:

```java
int firstDigit = Integer.parseInt(
    String.valueOf(Math.abs(n)).substring(0, 1)
);
```

Hoặc:

```java
char firstDigit = String.valueOf(n).charAt(0);
```

Nếu cần nối vào String, `char` là đủ.

## 5.9. Decimal → Binary

**[ĐÃ XUẤT HIỆN TRONG ĐỀ MẪU]**

```java
public String decimalToBinary(int n) {
    if (n == 0) {
        return "0";
    }

    String result = "";

    while (n > 0) {
        int remainder = n % 2;
        result = remainder + result;
        n = n / 2;
    }

    return result;
}
```

Không dùng `Integer.toString(n, 2)`/`Integer.toBinaryString(n)` nếu đề yêu cầu tự cài thuật toán hoặc cấm built-in conversion.

## 5.10. Decimal → một hệ cơ số khác (mở rộng)

Chuyển sang base `base` (2–36):

```java
String digits = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ";

String convertBase(int n, int base) {
    if (n == 0) return "0";

    String result = "";

    while (n > 0) {
        int remainder = n % base;
        result = digits.charAt(remainder) + result;
        n /= base;
    }

    return result;
}
```

Chỉ sử dụng nếu đề yêu cầu đổi hệ cơ số tổng quát.

## 5.11. Kiểm tra số nguyên tố (prime number) – mở rộng

```java
boolean isPrime(int n) {
    if (n < 2) return false;

    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) {
            return false;
        }
    }

    return true;
}
```

Keyword: `prime`, `divisible only by 1 and itself`.

## 5.12. Ước chung lớn nhất (GCD) – mở rộng

```java
int gcd(int a, int b) {
    a = Math.abs(a);
    b = Math.abs(b);

    while (b != 0) {
        int temp = a % b;
        a = b;
        b = temp;
    }

    return a;
}
```

## 5.13. Bội chung nhỏ nhất (LCM) – mở rộng

```java
int lcm(int a, int b) {
    if (a == 0 || b == 0) return 0;
    return Math.abs(a / gcd(a, b) * b);
}
```

---

# 6. CONDITION – ĐIỀU KIỆN VÀ CÔNG THỨC

## 6.1. If / else

```java
if (condition) {
    // true
} else {
    // false
}
```

Nhiều điều kiện:

```java
if (condition1) {
    // ...
} else if (condition2) {
    // ...
} else {
    // ...
}
```

Kết hợp điều kiện:

```java
if (a > 0 && b > 0) {
    // both true
}

if (a > 0 || b > 0) {
    // at least one true
}
```

## 6.2. Công thức theo điều kiện

```java
double result = baseValue;

if (condition) {
    result = specialValue;
} else {
    result = normalValue;
}

return result;
```

Cộng thêm tiền/phí/hệ số:

```java
if (quantity >= limit) {
    total *= factor;
}
```

Cập nhật theo giới hạn tối thiểu:

```java
if (value < 0) {
    value = 0;
}
```

Cập nhật theo giới hạn trên/dưới:

```java
if (value < min) {
    value = min;
} else if (value > max) {
    value = max;
}
```

## 6.3. Tính tổng/tích/trung bình

Sum:

```java
int sum = 0;

for (int x : arr) {
    sum += x;
}
```

Count:

```java
int count = 0;

for (int x : arr) {
    if (x > 0) count++;
}
```

Average:

```java
double average = (double) sum / count;
```

Tránh chia cho 0:

```java
if (count == 0) {
    return 0;
}
```

## 6.4. Tìm min/max trong một dãy

```java
int min = arr[0];
int max = arr[0];

for (int i = 1; i < arr.length; i++) {
    if (arr[i] < min) min = arr[i];
    if (arr[i] > max) max = arr[i];
}
```

Range:

```java
int range = max - min;
```

## 6.5. Ternary operator (if ngắn)

```java
String status = (quantity > 5) ? "discount" : "no discount";
```

Có thể thay bằng if/else. Khi đề phức tạp, dùng if/else dễ đọc hơn.

---

# 7. LIST/ARRAYLIST – THƯ VIỆN XỬ LÝ DANH SÁCH

> Phần này rất quan trọng vì nhiều đề yêu cầu class implements interface với các method f1/f2/f3 thao tác trên `List<ClassName>`.

## 7.1. Khai báo và import

```java
import java.util.List;
import java.util.ArrayList;
import java.util.Iterator;
import java.util.Collections;
import java.util.Comparator;
```

Khai báo:

```java
List<Product> list = new ArrayList<>();
```

Method nhận List:

```java
public void f1(List<Product> t) {
    // ...
}
```

Đừng tự đổi `List<Product>` thành `ArrayList<Product>` nếu interface yêu cầu List.

## 7.2. List methods

| Method | Công dụng |
|---|---|
| `list.size()` | số phần tử |
| `list.isEmpty()` | rỗng? |
| `list.get(i)` | lấy phần tử index i |
| `list.set(i, x)` | thay phần tử index i |
| `list.add(x)` | thêm cuối |
| `list.add(i, x)` | thêm vào index i |
| `list.remove(i)` | xóa theo index |
| `list.remove(obj)` | xóa object |
| `list.contains(x)` | có object không? |
| `list.indexOf(x)` | index đầu tiên, không có → -1 |
| `list.clear()` | xóa tất cả |
| `list.toArray()` | chuyển sang array |

## 7.3. Duyệt List

For index:

```java
for (int i = 0; i < t.size(); i++) {
    Product x = t.get(i);
}
```

For-each:

```java
for (Product x : t) {
    // process x
}
```

Iterator:

```java
Iterator<Product> it = t.iterator();

while (it.hasNext()) {
    Product x = it.next();
}
```

## 7.4. Sum field theo điều kiện

Keyword:
- `sum the price`
- `total price`
- `sum of all items whose ...`
- `add the values for every object that ...`

```java
int sum = 0;

for (Product x : t) {
    if (condition) {
        sum += x.getPrice();
    }
}

return sum;
```

Ví dụ type có uppercase > lowercase:

```java
int sum = 0;

for (Product x : t) {
    String s = x.getType();
    int upper = 0;
    int lower = 0;

    for (int i = 0; i < s.length(); i++) {
        char c = s.charAt(i);

        if (Character.isUpperCase(c)) upper++;
        if (Character.isLowerCase(c)) lower++;
    }

    if (upper > lower) {
        sum += x.getPrice();
    }
}

return sum;
```

## 7.5. Count objects theo điều kiện

```java
int count = 0;

for (Product x : t) {
    if (condition) {
        count++;
    }
}

return count;
```

Ví dụ đếm item có price >= 100:

```java
if (x.getPrice() >= 100) {
    count++;
}
```

## 7.6. Tìm object min/max

Minimum:

```java
if (t == null || t.isEmpty()) {
    return null;
}

Product min = t.get(0);

for (Product x : t) {
    if (x.getPrice() < min.getPrice()) {
        min = x;
    }
}

return min;
```

Maximum:

```java
if (t == null || t.isEmpty()) {
    return null;
}

Product max = t.get(0);

for (Product x : t) {
    if (x.getPrice() > max.getPrice()) {
        max = x;
    }
}

return max;
```

Nếu method return `int`, hãy return `min.getPrice()`/`max.getPrice()`, không return object.

## 7.7. Tìm max/min rồi cập nhật TẤT CẢ phần tử đồng hạng

Keyword:
- `all items with the maximum ...`
- `whose type has the longest length`
- `set the price of all ... to 0`
- `for every item that has the highest ...`

Ví dụ tìm type có độ dài lớn nhất, sau đó đặt price của tất cả phần tử đó thành 0:

```java
int maxLength = -1;

for (Product x : t) {
    if (x.getType().length() > maxLength) {
        maxLength = x.getType().length();
    }
}

for (Product x : t) {
    if (x.getType().length() == maxLength) {
        x.setPrice(0);
    }
}
```

**Vì sao hai vòng lặp?** Vòng đầu tìm max. Vòng hai cập nhật tất cả phần tử bằng max. Không nên chỉ lưu một object nếu đề nói `all`.

## 7.8. Tìm phần tử đầu tiên khớp điều kiện

```java
Product found = null;

for (Product x : t) {
    if (condition) {
        found = x;
        break;
    }
}

return found;
```

Keyword: `first item that satisfies`, `first matching object`.

## 7.9. Kiểm tra có tồn tại phần tử khớp

```java
boolean found = false;

for (Product x : t) {
    if (condition) {
        found = true;
        break;
    }
}

return found;
```

Keyword: `there is at least one`, `check whether any item`.

## 7.10. Sắp xếp tăng dần (ascending)

Theo price – Java 8:

```java
t.sort(new Comparator<Product>() {
    @Override
    public int compare(Product a, Product b) {
        return Integer.compare(a.getPrice(), b.getPrice());
    }
});
```

Ngắn:

```java
t.sort(Comparator.comparingInt(Product::getPrice));
```

Theo name:

```java
t.sort(new Comparator<Product>() {
    @Override
    public int compare(Product a, Product b) {
        return a.getName().compareTo(b.getName());
    }
});
```

## 7.11. Sắp xếp giảm dần (descending)

Theo price:

```java
t.sort(new Comparator<Product>() {
    @Override
    public int compare(Product a, Product b) {
        return Integer.compare(b.getPrice(), a.getPrice());
    }
});
```

Ngắn:

```java
t.sort(Comparator.comparingInt(Product::getPrice).reversed());
```

Theo name:

```java
t.sort((a, b) -> b.getName().compareTo(a.getName()));
```

**Nhớ:** đừng dùng `a.getPrice() - b.getPrice()` khi có nguy cơ tràn int; `Integer.compare()` an toàn hơn.

## 7.12. Sort theo nhiều tiêu chí (mở rộng)

Price tăng dần, nếu bằng nhau thì name tăng dần:

```java
t.sort(Comparator.comparingInt(Product::getPrice)
                 .thenComparing(Product::getName));
```

## 7.13. Xóa tất cả phần tử thỏa điều kiện – duyệt ngược

Keyword:
- `remove all items`
- `delete every object whose ...`
- `remove elements with ...`

```java
for (int i = t.size() - 1; i >= 0; i--) {
    if (condition) {
        t.remove(i);
    }
}
```

Ví dụ name kết thúc bằng `"o"`:

```java
for (int i = t.size() - 1; i >= 0; i--) {
    if (t.get(i).getName().endsWith("o")) {
        t.remove(i);
    }
}
```

Ví dụ type bắt đầu bằng chữ `"s"`:

```java
for (int i = t.size() - 1; i >= 0; i--) {
    if (t.get(i).getType().startsWith("s")) {
        t.remove(i);
    }
}
```

## 7.14. Xóa bằng Iterator

```java
Iterator<Product> it = t.iterator();

while (it.hasNext()) {
    Product x = it.next();

    if (condition) {
        it.remove();
    }
}
```

**Không làm như sau:**

```java
for (Product x : t) {
    if (condition) {
        t.remove(x); // có thể ConcurrentModificationException
    }
}
```

## 7.15. Tìm item có String dài nhất/ngắn nhất

Lưu max length:

```java
int maxLength = -1;

for (Product x : t) {
    if (x.getName().length() > maxLength) {
        maxLength = x.getName().length();
    }
}
```

Lấy tất cả item có độ dài max:

```java
for (Product x : t) {
    if (x.getName().length() == maxLength) {
        // action
    }
}
```

## 7.16. Đếm chữ cái trong field String rồi tìm max

```java
int countLetters(String s) {
    int count = 0;

    for (int i = 0; i < s.length(); i++) {
        if (Character.isLetter(s.charAt(i))) {
            count++;
        }
    }

    return count;
}
```

Dùng trong List:

```java
int maxLetters = -1;

for (Product x : t) {
    int c = countLetters(x.getType());

    if (c > maxLetters) {
        maxLetters = c;
    }
}

for (int i = t.size() - 1; i >= 0; i--) {
    if (countLetters(t.get(i).getType()) == maxLetters) {
        t.remove(i);
    }
}
```

## 7.17. Cập nhật tất cả object theo điều kiện

```java
for (Product x : t) {
    if (condition) {
        x.setPrice(newPrice);
    }
}
```

Keyword: `update all`, `set ... for every item`, `change each object whose ...`.

## 7.18. Đếm số lần xuất hiện của một giá trị trong List<Integer>

```java
int count = 0;

for (Integer x : list) {
    if (x == target) {
        count++;
    }
}
```

## 7.19. Xóa phần tử trùng lặp, giữ thứ tự (mở rộng)

```java
List<String> unique = new ArrayList<>();

for (String x : list) {
    if (!unique.contains(x)) {
        unique.add(x);
    }
}
```

Chỉ dùng nếu đề yêu cầu remove duplicates/unique values và giữ thứ tự.

---

# 8. INHERITANCE – KẾ THỪA VÀ OVERRIDE

## 8.1. Keyword

| Đề ghi | Ý nghĩa | Code |
|---|---|---|
| superclass / parent | lớp cha | `class A` |
| subclass / child | lớp con | `class B extends A` |
| extends | kế thừa | `extends` |
| inherited method | method kế thừa | gọi trực tiếp nếu truy cập được |
| override | ghi đè | `@Override` |
| invoke/call parent constructor | gọi constructor cha | `super(args)` |
| call superclass method | gọi method cha | `super.method()` |

## 8.2. Mẫu superclass/subclass

```java
public class Product {
    private String type;
    private int price;

    public Product() {
        type = "";
        price = 0;
    }

    public Product(String type, int price) {
        this.type = type;
        this.price = price;
    }

    public String getType() {
        return type;
    }

    public int getPrice() {
        return price;
    }

    public void setType(String type) {
        this.type = type;
    }

    public void setPrice(int price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return type + "," + price;
    }
}
```

```java
public class SpecialProduct extends Product {
    private int quantity;

    public SpecialProduct() {
        super();
        quantity = 0;
    }

    public SpecialProduct(String type, int price, int quantity) {
        super(type, price);
        this.quantity = quantity;
    }

    public int getQuantity() {
        return quantity;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }

    @Override
    public String toString() {
        return super.toString() + "," + quantity;
    }
}
```

## 8.3. `private` field của cha

Không hợp lệ:

```java
this.type = "new"; // nếu type là private trong Parent
```

Hợp lệ:

```java
setType("new");
String s = getType();
```

## 8.4. Override toString

Nối kết quả cha:

```java
@Override
public String toString() {
    return super.toString() + "," + quantity;
}
```

Tự định dạng lại hoàn toàn:

```java
@Override
public String toString() {
    return getType() + "," + getPrice() + "," + quantity;
}
```

## 8.5. Overloading vs overriding

| Overloading | Overriding |
|---|---|
| cùng tên, khác parameter list | lớp con định nghĩa lại method cha |
| có thể ở cùng một class | cần quan hệ kế thừa |
| chọn method dựa trên tham số | method được quyết định theo object runtime |
| ví dụ `print(int)` và `print(String)` | ví dụ subclass override `toString()` |

---

# 9. INTERFACE – IMPLEMENT VÀ XỬ LÝ METHOD

## 9.1. Keyword

- `interface`
- `implements`
- `implement all methods`
- `method signature`
- `already compiled`
- `provided in bytecode`
- `do not create the interface file`

Nếu interface đã được cung cấp dạng `.class`/bytecode:
- Không tạo file interface mới.
- Tạo đúng class được yêu cầu.
- `implements InterfaceName`.
- Implement đủ method.
- Giữ nguyên tên, kiểu trả về, parameter types và thứ tự tham số.

## 9.2. Ví dụ

Interface đã tồn tại:

```java
import java.util.List;

public interface IProduct {
    int f1(List<Product> t);
    void f2(List<Product> t);
    void f3(List<Product> t);
}
```

Class triển khai:

```java
import java.util.List;

public class MyProduct implements IProduct {

    @Override
    public int f1(List<Product> t) {
        return 0;
    }

    @Override
    public void f2(List<Product> t) {
    }

    @Override
    public void f3(List<Product> t) {
    }
}
```

Chữ ký trên chỉ là ví dụ. Khi thi phải implement đúng interface thật của đề.

## 9.3. Cách đọc đề f1/f2/f3

| Method return type | Kết quả thường phải return |
|---|---|
| `int` | số đếm, tổng, giá trị nguyên |
| `double` | tổng/trung bình/công thức số thực |
| `String` | chuỗi kết quả |
| `boolean` | true/false |
| `Product` | object tìm được |
| `void` | sửa List/object hoặc không trả kết quả |

Không return `null` cho method `int`; không return `0` cho method `void`.

---

# 10. ARRAY – MẢNG MỘT CHIỀU

> Các đề mẫu tập trung nhiều hơn vào List, nhưng mảng là cấu trúc cơ bản có thể dùng trong String splitting, digit counting và bài xử lý dữ liệu.

## 10.1. Khai báo

```java
int[] a = new int[5];
int[] b = {3, 5, 7, 9};
String[] words = {"Java", "OOP"};
```

## 10.2. Duyệt mảng

```java
for (int i = 0; i < a.length; i++) {
    // a[i]
}
```

## 10.3. Sum/count/min/max

```java
int sum = 0;
int min = a[0];
int max = a[0];

for (int x : a) {
    sum += x;
    if (x < min) min = x;
    if (x > max) max = x;
}
```

## 10.4. Sort mảng

```java
import java.util.Arrays;

Arrays.sort(a); // tăng dần
```

Giảm dần với `int[]`: có thể sort tăng rồi duyệt ngược khi in/ghi kết quả. `Collections.reverseOrder()` dùng với wrapper array `Integer[]`, không phải primitive `int[]`.

## 10.5. Tìm kiếm tuyến tính

```java
int index = -1;

for (int i = 0; i < a.length; i++) {
    if (a[i] == target) {
        index = i;
        break;
    }
}
```

---

# 11. INPUT, OUTPUT, FORMATTING, UTILITY METHODS

## 11.1. Scanner

```java
import java.util.Scanner;

Scanner sc = new Scanner(System.in);

int n = sc.nextInt();
double d = sc.nextDouble();
String word = sc.next();
String line = sc.nextLine();
```

Sau `nextInt()`/`nextDouble()`, ký tự newline có thể còn trong buffer. Nếu muốn đọc nguyên dòng tiếp theo:

```java
int n = sc.nextInt();
sc.nextLine(); // consume newline
String line = sc.nextLine();
```

## 11.2. Print

```java
System.out.print("Hello");       // không xuống dòng
System.out.println("Hello");     // có xuống dòng
System.out.printf("%.2f", value);
```

## 11.3. String format

| Format | Ý nghĩa |
|---|---|
| `%.2f` | số thực 2 chữ số thập phân |
| `%.1f` | 1 chữ số thập phân |
| `%d` | integer |
| `%s` | String |
| `%c` | char |
| `%n` | xuống dòng |

Ví dụ:

```java
String s = String.format("%.2f", 7.5); // "7.50"
```

Nếu đề ghi `Do not format the result`, không dùng formatting trừ khi một field riêng được yêu cầu format.

## 11.4. Math

```java
Math.abs(x);       // trị tuyệt đối
Math.max(a, b);    // max
Math.min(a, b);    // min
Math.pow(a, b);    // a mũ b, trả double
Math.sqrt(x);      // căn bậc hai
Math.round(x);     // làm tròn
Math.floor(x);     // làm tròn xuống
Math.ceil(x);      // làm tròn lên
```

## 11.5. Chuyển kiểu String ↔ số

```java
int n = Integer.parseInt("123");
double d = Double.parseDouble("12.5");

String s1 = String.valueOf(123);
String s2 = Integer.toString(123);
```

Nếu đề cấm dùng `Integer.toString()` cho binary conversion, không dùng nó để giải bài đó; `String.valueOf(n)` vẫn có thể hữu ích ở bài chỉ cần đếm số chữ số, trừ khi đề cấm rõ hơn.

## 11.6. StringBuilder – thư viện thao tác chuỗi có thể thay đổi

> Đây là phần mở rộng đầy đủ: hãy tra keyword tiếng Anh rồi chọn pattern A–K tương ứng.

<badge>Quan trọng khi xử lý String trong loop</badge>

### Khi nào đề có thể cần StringBuilder?

| Keyword trong đề | Ý nghĩa / cách nghĩ |
|---|---|
| `build a new string` | Tạo chuỗi kết quả mới |
| `construct a string` | Ghép các phần tử thành chuỗi |
| `append each character` | Nối từng ký tự vào cuối |
| `append the word` | Nối một từ vào cuối |
| `insert at position/index` | Chèn vào vị trí |
| `delete/remove characters` | Xóa ký tự/đoạn |
| `replace characters` | Thay đoạn/ký tự |
| `reverse the string` | Đảo chuỗi |
| `modify the character at index` | Sửa ký tự tại index |
| `build result in a loop` | Dùng `StringBuilder` để tích lũy kết quả |
| `without leading/trailing spaces` | Chỉ thêm delimiter khi builder đã có nội dung |

**Ý tưởng:** `String` là immutable (không sửa trực tiếp nội dung). `StringBuilder` là mutable (có thể append/insert/delete/replace trên cùng một object). Khi phải ghép nhiều lần trong loop, `StringBuilder` thường tiện và hiệu quả hơn `result += ...`.

### Khai báo và chuyển đổi

```java
StringBuilder sb = new StringBuilder();
StringBuilder sb2 = new StringBuilder("Java");
StringBuilder sb3 = new StringBuilder(100); // capacity ban đầu
```

Chuyển StringBuilder thành String:

```java
String result = sb.toString();
```

Chuyển String thành StringBuilder:

```java
StringBuilder sb = new StringBuilder(s);
```

### Các method quan trọng

| Method | Tác dụng | Ví dụ |
|---|---|---|
| `append(x)` | nối x vào cuối | `sb.append("Java")` |
| `insert(i, x)` | chèn x tại index i | `sb.insert(0, "Hi ")` |
| `delete(start, end)` | xóa từ start đến trước end | `sb.delete(1, 3)` |
| `deleteCharAt(i)` | xóa ký tự ở index i | `sb.deleteCharAt(0)` |
| `replace(start, end, str)` | thay đoạn start..end-1 | `sb.replace(0, 2, "OK")` |
| `setCharAt(i, c)` | thay ký tự tại i | `sb.setCharAt(0, 'A')` |
| `charAt(i)` | đọc ký tự tại i | `sb.charAt(0)` |
| `length()` | số ký tự hiện có | `sb.length()` |
| `reverse()` | đảo ngược nội dung | `sb.reverse()` |
| `substring(start)` | lấy phần từ start (trả String) | `sb.substring(1)` |
| `substring(start, end)` | lấy đoạn start..end-1 (trả String) | `sb.substring(0, 2)` |
| `toString()` | chuyển sang String | `sb.toString()` |
| `capacity()` | sức chứa hiện tại | `sb.capacity()` |
| `ensureCapacity(n)` | đảm bảo capacity tối thiểu | `sb.ensureCapacity(50)` |
| `setLength(n)` | đổi độ dài; có thể cắt hoặc thêm `\\u0000` | `sb.setLength(3)` |

**Nhớ quy tắc index:** `delete(start, end)` và `replace(start, end, ...)` lấy từ `start` đến trước `end`, giống `substring(start, end)`.

### A. Nối nhiều chuỗi trong loop (append)

Keyword: `append`, `concatenate`, `build a result`, `construct a new string`.

```java
StringBuilder result = new StringBuilder();

for (String word : words) {
    result.append(word);
}

return result.toString();
```

Nối thêm dấu phẩy:

```java
StringBuilder result = new StringBuilder();

for (Product x : list) {
    result.append(x.getName()).append(",");
}

return result.toString();
```

Nếu không muốn dấu phẩy thừa cuối chuỗi, xem pattern delimiter ở mục C.

### B. Nối ký tự thỏa điều kiện (filter characters)

Keyword: `keep only`, `extract all`, `build a new string consisting of`, `exclude/remove characters`.

Ví dụ: chỉ giữ chữ cái:

```java
public String keepLetters(String s) {
    StringBuilder result = new StringBuilder();

    for (int i = 0; i < s.length(); i++) {
        char c = s.charAt(i);

        if (Character.isLetter(c)) {
            result.append(c);
        }
    }

    return result.toString();
}
```

Chỉ giữ chữ số:

```java
StringBuilder result = new StringBuilder();

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (Character.isDigit(c)) {
        result.append(c);
    }
}

String answer = result.toString();
```

Loại bỏ space:

```java
StringBuilder result = new StringBuilder();

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (c != ' ') {
        result.append(c);
    }
}
```

### C. Ghép các từ bằng đúng một space, không có space đầu/cuối

Keyword:
- `separated by a single space`
- `no leading or trailing spaces`
- `keep the original order`
- `return an empty string if no word satisfies`

Cách dùng `StringBuilder`:

```java
StringBuilder result = new StringBuilder();

for (String word : words) {
    if (condition) {
        if (result.length() > 0) {
            result.append(" ");
        }

        result.append(word);
    }
}

return result.toString();
```

Ví dụ giữ từ có length > 3:

```java
public String filterWords(String s) {
    String[] words = s.split(" ");
    StringBuilder result = new StringBuilder();

    for (String word : words) {
        if (word.length() > 3) {
            if (result.length() > 0) {
                result.append(" ");
            }

            result.append(word);
        }
    }

    return result.toString();
}
```

Nếu không có từ nào thỏa, builder vẫn rỗng và `toString()` trả `""`.

### D. Chèn ký tự/chuỗi tại vị trí (insert)

Keyword: `insert`, `add a character at index/position`, `insert a separator`.

```java
StringBuilder sb = new StringBuilder("Jvaa");
sb.insert(1, "a");
// "Javaa"
```

Chèn dấu `-` ở giữa:

```java
StringBuilder sb = new StringBuilder("1234");
sb.insert(2, "-");
// "12-34"
```

Chèn vào đầu/cuối:

```java
sb.insert(0, "prefix");
sb.append("suffix");
```

### E. Xóa ký tự/đoạn (delete/remove)

Keyword: `delete`, `remove character at index`, `remove substring from index i to j`.

Xóa ký tự tại index:

```java
StringBuilder sb = new StringBuilder("banana");
sb.deleteCharAt(2);
// "baana"
```

Xóa đoạn từ index 1 đến trước index 4:

```java
StringBuilder sb = new StringBuilder("abcdef");
sb.delete(1, 4);
// "aef"
```

Xóa tất cả dấu cách:

```java
StringBuilder result = new StringBuilder();

for (int i = 0; i < s.length(); i++) {
    if (s.charAt(i) != ' ') {
        result.append(s.charAt(i));
    }
}
```

### F. Thay ký tự/đoạn (replace)

Keyword: `replace`, `replace character at index`, `replace a range`.

Thay ký tự tại index:

```java
StringBuilder sb = new StringBuilder("java");
sb.setCharAt(0, 'J');
// "Java"
```

Thay đoạn:

```java
StringBuilder sb = new StringBuilder("I like C");
sb.replace(7, 8, "Java");
// "I like Java"
```

Thay mọi chữ số bằng `*`:

```java
StringBuilder result = new StringBuilder();

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (Character.isDigit(c)) {
        result.append('*');
    } else {
        result.append(c);
    }
}
```

### G. Đảo ngược chuỗi (reverse)

Keyword: `reverse`, `reverse the order of characters`.

Cách ngắn:

```java
String reversed = new StringBuilder(s).reverse().toString();
```

Dùng trực tiếp trong method:

```java
public String reverseString(String s) {
    return new StringBuilder(s).reverse().toString();
}
```

### H. Tạo acronym bằng StringBuilder

Keyword: `build acronym`, `append the first letter of each word`.

```java
public String buildAcronym(String s) {
    if (s == null || s.isEmpty()) {
        return "";
    }

    String[] words = s.split(" ");
    StringBuilder result = new StringBuilder();

    for (String word : words) {
        if (!word.isEmpty()) {
            char c = word.charAt(0);

            if (Character.isLetter(c)) {
                result.append(Character.toUpperCase(c));
            }
        }
    }

    return result.toString();
}
```

### I. Chuyển Decimal sang Binary bằng StringBuilder

**[ĐÃ XUẤT HIỆN TRONG ĐỀ MẪU – có thể dùng pattern nối đầu]**

```java
public String decimalToBinary(int n) {
    if (n == 0) {
        return "0";
    }

    StringBuilder result = new StringBuilder();

    while (n > 0) {
        int remainder = n % 2;
        result.insert(0, remainder);
        n /= 2;
    }

    return result.toString();
}
```

Cách dùng `String` trong mục 5.9 trước đó cũng đúng. Nếu muốn thao tác builder, `insert(0, remainder)` chèn phần dư vào đầu vì các phần dư được tạo theo thứ tự ngược.

### J. Xây dựng chuỗi từ các object trong List

Keyword: `return a string containing all names`, `join all values`, `display the list`.

```java
public String getNames(List<Product> list) {
    StringBuilder result = new StringBuilder();

    for (Product x : list) {
        if (result.length() > 0) {
            result.append(", ");
        }

        result.append(x.getName());
    }

    return result.toString();
}
```

### K. Sửa nhiều ký tự ngay trên builder

Duyệt và thay mọi ký tự `a` thành `A`:

```java
StringBuilder sb = new StringBuilder(s);

for (int i = 0; i < sb.length(); i++) {
    if (sb.charAt(i) == 'a') {
        sb.setCharAt(i, 'A');
    }
}

String result = sb.toString();
```

### Những điều StringBuilder KHÔNG có như String

Không gọi trực tiếp các method sau trên StringBuilder:

```java
sb.split(" ");           // không có split
sb.toUpperCase();        // không có toUpperCase
sb.toLowerCase();        // không có toLowerCase
sb.trim();               // không có trim
sb.contains("abc");      // không có contains
```

Cách xử lý: chuyển về String bằng `sb.toString()` rồi gọi method phù hợp.

```java
String s = sb.toString();
String upper = s.toUpperCase();
boolean found = s.contains("abc");
String[] words = s.split(" ");
```

### String vs StringBuilder – chọn cái nào?

| Tình huống | Nên dùng |
|---|---|
| Chỉ lấy substring/uppercase/lowercase | `String` |
| Nối 1–2 giá trị đơn giản | `String` + `+` |
| Nối nhiều lần trong loop | `StringBuilder` |
| Append/insert/delete/replace nhiều lần | `StringBuilder` |
| Đảo ngược | `StringBuilder.reverse()` |
| Cần gọi `split`, `contains`, `trim` | `String` |
| Cần trả về String từ method | `builder.toString()` |

**Lỗi thường gặp:**
- Quên `toString()` khi method yêu cầu return `String`.
- Nhầm `delete(start, end)` lấy cả end (thực tế end không được xóa).
- Nhầm `deleteCharAt(i)` với `delete(i, i+1)`.
- Dùng `==` để so sánh hai StringBuilder; nếu cần so nội dung, dùng `sb1.toString().equals(sb2.toString())`.
- Nghĩ `StringBuilder` có `split()`/`toUpperCase()`; các method đó thuộc String.


---

# 12. NETBEANS – THAO TÁC IDE VÀ WORKFLOW PHÒNG THI

## 12.1. Generate Code

| Thao tác | Ghi nhớ |
|---|---|
| Generate Code | thường `Alt + Insert` |
| Insert Code qua menu | `Source → Insert Code` |
| Fix/import hints | thường `Alt + Enter` theo ngữ cảnh |
| Organize Imports | `Ctrl + Shift + I` |
| Format code | `Alt + Shift + F` (có thể khác theo keymap) |
| Clean and Build | `Shift + F11` theo PE instructions |

Phím tắt có thể khác theo phiên bản/keymap; menu Source là cách kiểm tra đáng tin cậy.

## 12.2. Dùng IDE sinh phần nào?

| Thành phần | Có thể Generate? | Có cần sửa tay? |
|---|---|---|
| Constructor thường | Có | kiểm tra default values / super |
| Getter thường | Có | thường không |
| Setter thường | Có | có, nếu có logic riêng |
| `toString()` | Có | thường phải kiểm tra format |
| Implement interface methods | Có | phải viết logic |
| Override method | Có | phải viết logic |
| Algorithm methods | Không thay thế được | phải tự code |

## 12.3. Những quy định PE từng xuất hiện trong file đề

Một số PE instructions trong PDF bạn gửi nhấn mạnh:
- Dùng project được cung cấp; không tạo project mới.
- Không xóa/đổi tên file được cung cấp.
- Không tự tạo file có tên trùng với file đã có/được yêu cầu.
- Không dùng `package` trong một số đề.
- Không dùng package ngoài yêu cầu.
- Sử dụng NetBeans/JDK theo hướng dẫn đề.
- Clean and Build trước khi nộp nếu project lỗi.
- Đổi đúng tên thư mục RUN/submit theo hướng dẫn.
- Nộp đúng project, không nộp project chưa chỉnh sửa.

**Đọc instructions của chính đề đang thi. Không mặc định tất cả các phiên bản đều có quy định hoàn toàn giống nhau.**

---

# 13. LỖI COMPILE/RUNTIME VÀ CÁCH SỬA

| Lỗi | Nguyên nhân phổ biến | Kiểm tra |
|---|---|---|
| `cannot find symbol` | sai tên class/field/method hoặc chưa import | chính tả, import |
| `method does not override` | signature không trùng method cha/interface | tên, tham số, return type |
| `incompatible types` | return/assignment sai kiểu | kiểu dữ liệu |
| `missing return statement` | method cần trả giá trị nhưng có nhánh không return | tất cả nhánh |
| `constructor ... cannot be applied` | gọi constructor sai tham số | `super(...)`, `new Class(...)` |
| `non-static ... cannot be referenced` | gọi instance field/method từ static context | tạo object hoặc bỏ static đúng yêu cầu |
| `StringIndexOutOfBoundsException` | substring/charAt vượt index | kiểm tra length |
| `IndexOutOfBoundsException` | index List/Array sai | kiểm tra size/length |
| `NullPointerException` | object/String đang null | kiểm tra null |
| `ConcurrentModificationException` | sửa List trong for-each | Iterator hoặc duyệt ngược |
| `ClassNotFoundException` | cấu trúc/classpath/tên class | project và package |
| `duplicate class` | có hai class cùng tên trong cùng package | không tạo file trùng |
| `';' expected` | thiếu dấu chấm phẩy | dòng ngay trước vị trí báo lỗi |
| `reached end of file while parsing` | thiếu dấu `}` | kiểm tra cặp ngoặc |

## 13.1. Lỗi index String

Nguy hiểm:

```java
s.charAt(0);
s.substring(1);
```

Nếu `s` rỗng sẽ lỗi.

An toàn:

```java
if (s != null && !s.isEmpty()) {
    // process
}
```

## 13.2. Lỗi chia nguyên

Sai nếu muốn số thực:

```java
double x = 5 / 2; // 2.0
```

Đúng:

```java
double x = 5.0 / 2; // 2.5
```

## 13.3. Lỗi remove List

Không xóa trực tiếp trong for-each:

```java
for (Product x : t) {
    if (condition) t.remove(x);
}
```

Dùng vòng ngược:

```java
for (int i = t.size() - 1; i >= 0; i--) {
    if (condition) t.remove(i);
}
```

---

# 14. BOUNDARY TESTS – KIỂM TRA TRƯỜNG HỢP BIÊN

Khi sample run có ít test, tự thử:
- Giá trị ngay dưới ngưỡng.
- Giá trị đúng ngưỡng.
- Giá trị ngay trên ngưỡng.
- Chuỗi rỗng/null nếu input có thể xảy ra.
- List rỗng/có một phần tử.
- Nhiều object cùng min/max.
- Số 0 và số nhỏ nhất.

| Dạng | Nên test |
|---|---|
| `>= 100` | 99, 100, 101 |
| `> 5` | 5, 6 |
| `< 0` | -1, 0, 1 |
| String first/last char | `""`, `"A"`, `"AB"` |
| Count digits | 0, 1, 10, 100 |
| Decimal → Binary | 0, 1, 2, 5, 10, 16 |
| List min/max | rỗng, 1 item, 2 item, đồng hạng |
| Remove all | không item nào khớp, một item khớp, nhiều item khớp |
| Sort | đã tăng, đã giảm, có giá bằng nhau |

---

# 15. CÁC PATTERN XÁC NHẬN TỪ 8 ĐỀ ĐÃ GỬI

Đây là danh sách các dạng được nhìn thấy trong các PDF, không phải danh sách dự đoán chắc chắn mọi đề thi.

## 15.1. Nhóm Class / Constructor / Getter / Setter

| Đề mẫu | Yêu cầu đặc biệt |
|---|---|
| CoffeeShop | storeName: chữ đầu hoa, phần còn lại thường |
| CoffeeShop | revenue có ngưỡng numberOfCups >= 100 |
| CoffeeShop | profit = totalRevenue - cost × cups |
| CoffeeShop | toString uppercase store name, colon, revenue 2 decimal |
| Fox | getName nối name với chữ số đầu của age |
| Fox | setAge = newAge + length(name) |
| Coral (một phiên bản) | getter name bỏ ký tự đầu |
| Coral (phiên bản khác) | getter name bỏ ký tự cuối |
| Person | sickLeave cộng upValue |
| Person (biến thể) | setName nối newName sau tên cũ |
| Person (biến thể) | getName viết hoa |
| Employee | 4 fields, default values, getters/setters, toString |

## 15.2. Nhóm Inheritance

| Đề mẫu | Yêu cầu đặc biệt |
|---|---|
| Screen/OLEDScreen | quality index, price, burn-in risk, refresh < 0 → 0 |
| Chair/SpecChair | quantity vượt ngưỡng thì đổi type/status |
| SpecChair (biến thể) | getType bỏ ký tự cuối |
| Ladder/SpecLadder | thay alphabetic character đầu bằng chữ số đầu price |
| SpecLadder | đếm digit chẵn hoặc lẻ trong weight, nối type với số đếm |
| Lemon/SpecLemon | thay ký tự cuối từng từ bằng ký tự đầu price |
| SpecLemon | quantity có ít nhất 3 digits thì nối số digit quantity, nếu không nối số digit price |

**Không gộp nhầm các biến thể:** một đề dùng odd digits, đề khác dùng even digits; một đề dùng ký tự đầu từ, đề khác dùng ký tự cuối từ.

## 15.3. Nhóm Interface / List

| Đề mẫu | Yêu cầu đặc biệt |
|---|---|
| ILadder – f1 | Sum price khi type có uppercase > lowercase |
| ILadder – f2 | Set price = 0 cho mọi type có length lớn nhất |
| ILadder – f3 | Remove mọi item có số chữ cái trong type lớn nhất |
| IShoes – f1 | Tìm Shoes có min hoặc max price, tùy phiên bản |
| IShoes – f2 | Sort price ascending hoặc descending, tùy phiên bản |
| IShoes – f3 | Remove tên bắt đầu/kết thúc bằng ký tự được chỉ định |
| MyShoes | Có thêm display(List) trong một đề |

## 15.4. Nhóm String / Number

| Đề mẫu | Yêu cầu đặc biệt |
|---|---|
| IStringNumberTool – buildAcronym | Lấy chữ đầu từ, nếu alphabetic thì uppercase; null/empty → empty |
| IStringNumberTool – decimalToBinary | tự chuyển binary; không dùng built-in `Integer.toString()` |
| IString – f1 | Đếm từ chứa đúng 2 different digits và ít nhất 1 lowercase letter |
| IString – f2 | Lọc từ theo số chữ cái khác số non-alphabetic; giữ thứ tự, một space, không leading/trailing space |

---

# 16. CHECKLIST 90 PHÚT

## Trước khi code
- [ ] Đọc toàn bộ PE instructions.
- [ ] Kiểm tra project được cấp, tên file và class.
- [ ] Không tạo project mới nếu đề yêu cầu project có sẵn.
- [ ] Xác định signature từng method.
- [ ] Gạch chân keyword tiếng Anh: `first`, `last`, `each`, `all`, `at least`, `exactly`, `ascending`, `descending`, `remove`, `replace`.
- [ ] Phân biệt phần nào IDE generate được và phần nào phải sửa logic.

## Khi làm Q1
- [ ] Khai báo fields đúng kiểu.
- [ ] Generate constructor/getter/setter cơ bản.
- [ ] Kiểm tra default values.
- [ ] Tự sửa setter có công thức/điều kiện.
- [ ] Viết method biến đổi String.
- [ ] `toString()` đúng dấu phẩy/space/format.

## Khi làm Q2
- [ ] Làm lớp cha trước.
- [ ] `extends` đúng tên.
- [ ] Gọi `super(...)` đúng tham số và ở dòng đầu.
- [ ] Không truy cập trực tiếp field private của cha.
- [ ] `@Override` đúng signature.
- [ ] Đọc kỹ `first character` vs `first alphabetic character`.
- [ ] Kiểm tra điều kiện ngưỡng `>` hay `>=`.

## Khi làm Q3
- [ ] Không tạo lại interface nếu đã có sẵn.
- [ ] `implements` đúng interface.
- [ ] Implement đủ method.
- [ ] Sum/count/min/max đúng kiểu return.
- [ ] Nếu đề nói all matching, xử lý tất cả.
- [ ] Sort đúng chiều.
- [ ] Remove an toàn.
- [ ] Xử lý đồng hạng nếu đề yêu cầu all.

## Khi làm Q4
- [ ] Tách words đúng delimiter.
- [ ] Xác định đếm occurrences hay distinct values.
- [ ] Dùng đúng Character method.
- [ ] Xử lý n = 0 khi chuyển binary/đếm digits.
- [ ] Không dùng built-in bị cấm.
- [ ] Kết quả đúng thứ tự và khoảng trắng.

## Trước khi nộp
- [ ] Build/Run project.
- [ ] Kiểm tra hết nhánh điều kiện.
- [ ] Kiểm tra output sample.
- [ ] Kiểm tra folder RUN/SRC theo instructions của đề.
- [ ] Không xóa/đổi tên file gốc trái quy định.
- [ ] Submit đúng project/thư mục.

---

# NGUYÊN TẮC CUỐI CÙNG

Khi đọc bất kỳ yêu cầu nào, hãy tự hỏi theo đúng thứ tự:

1. **Đề muốn thao tác lên cái gì?** String, char, number, object hay List?
2. **Động từ là gì?** count, sum, replace, remove, update, sort, return?
3. **Phạm vi là gì?** first, last, each, all, every, first matching?
4. **Điều kiện là gì?** greater than, at least, exactly, different, contains?
5. **Kết quả phải trả về kiểu gì?** int, double, String, object hay void?
6. **Có quy định format không?** comma, space, two decimals, do not format?
7. **Có built-in nào bị cấm không?** Nếu có, tự viết thuật toán.

**Phao tốt nhất không phải là thuộc lòng hàng trăm dòng code. Đó là tìm được đúng pattern trong vài giây, rồi thay điều kiện và tên field theo đề đang làm.**


---

# PHẦN BỔ SUNG – OPERATION ATLAS (MỞ RỘNG THAO TÁC THEO TỪNG NHÓM)

> Phần này bổ sung những thao tác còn thiếu ở các chương trước. Đây là **sổ tra cứu cú pháp Java thực hành**, không phải khẳng định các API đều đã xuất hiện trong 8 đề. Các mục bám sát đề được đánh dấu **[ĐÃ THẤY TRONG ĐỀ MẪU]**; các mục còn lại là **[MỞ RỘNG JAVA 8]**.
>
> Quy ước ví dụ: `s` là String, `sb` là StringBuilder, `list` là List, `a` là array. Đổi tên biến/class/field theo đề thi.

# 17. STRING – CÁC THAO TÁC BỔ SUNG

## 17.1. Kiểm tra chuỗi rỗng, null, khoảng trắng

| Keyword | Java | Ghi chú |
|---|---|---|
| null string | `s == null` | Kiểm tra reference null |
| empty string | `s.isEmpty()` | Độ dài bằng 0 |
| blank / only spaces | `s.trim().isEmpty()` | Java 8; bỏ space đầu/cuối |
| not empty | `!s.isEmpty()` | Không tương đương not null |
| null or empty | `s == null || s.isEmpty()` | Short-circuit nên an toàn |
| non-null and non-empty | `s != null && !s.isEmpty()` | Kiểm tra theo thứ tự |

```java
if (s == null || s.isEmpty()) {
    return "";
}
```

```java
if (s != null && !s.trim().isEmpty()) {
    // có ít nhất một ký tự không phải space thường
}
```

`trim()` xử lý các ký tự có mã không lớn hơn U+0020; Java 8 không có `String.isBlank()` (method này thuộc Java 11 trở lên).

## 17.2. Tìm vị trí chuỗi/ký tự

| Keyword | Method | Kết quả khi không tìm thấy |
|---|---|---|
| first occurrence / first position | `s.indexOf('a')` | `-1` |
| last occurrence | `s.lastIndexOf('a')` | `-1` |
| position of substring | `s.indexOf("abc")` | `-1` |
| search from index | `s.indexOf("a", fromIndex)` | `-1` |
| last position before index | `s.lastIndexOf("a", fromIndex)` | `-1` |

```java
int pos = s.indexOf("java");

if (pos != -1) {
    // found
}
```

Tìm tất cả vị trí xuất hiện của ký tự:

```java
char target = 'a';

for (int i = 0; i < s.length(); i++) {
    if (s.charAt(i) == target) {
        System.out.println(i);
    }
}
```

## 17.3. So sánh thứ tự từ điển (lexicographical order)

Keyword:
- `alphabetically`
- `lexicographical order`
- `comes before`
- `comes after`
- `compare two strings`

```java
int result = a.compareTo(b);
```

| Kết quả | Ý nghĩa |
|---|---|
| `< 0` | a đứng trước b |
| `= 0` | hai chuỗi bằng nhau theo thứ tự từ điển |
| `> 0` | a đứng sau b |

```java
if (a.compareTo(b) < 0) {
    // a before b
}
```

Không nên giả định `compareTo()` trả chính xác `-1`, `0`, `1`; chỉ kiểm tra dấu.

Không phân biệt hoa thường:

```java
a.compareToIgnoreCase(b);
```

## 17.4. Kiểm tra chuỗi theo regex (pattern matching)

Keyword:
- `matches the pattern`
- `contains only digits`
- `consists of letters`
- `valid format`

Chỉ chứa chữ số:

```java
boolean onlyDigits = s.matches("[0-9]+");
```

Chỉ chứa chữ cái tiếng Anh:

```java
boolean onlyLetters = s.matches("[A-Za-z]+");
```

Chứa ít nhất một chữ số:

```java
boolean hasDigit = s.matches(".*[0-9].*");
```

Định dạng gồm 1 chữ hoa đầu, theo sau là chữ thường:

```java
boolean ok = s.matches("[A-Z][a-z]*");
```

**Nhớ:** `matches()` yêu cầu toàn bộ chuỗi khớp pattern, không chỉ một phần.

Regex thường gặp:

| Pattern | Ý nghĩa |
|---|---|
| `[0-9]` | một chữ số |
| `[A-Z]` | một chữ hoa ASCII |
| `[a-z]` | một chữ thường ASCII |
| `[A-Za-z]` | một chữ cái ASCII |
| `[A-Za-z0-9]` | chữ hoặc số ASCII |
| `\\d` | chữ số |
| `\\D` | không phải chữ số |
| `\\s` | whitespace |
| `\\S` | không phải whitespace |
| `+` | một hoặc nhiều |
| `*` | không hoặc nhiều |
| `?` | không hoặc một |
| `{3}` | đúng 3 lần |
| `{2,5}` | từ 2 đến 5 lần |
| `^` | đầu chuỗi (trong regex) |
| `$` | cuối chuỗi (trong regex) |
| `.` | một ký tự bất kỳ |

## 17.5. Chuyển String thành char array

Keyword: `convert to character array`, `process each character`.

```java
char[] chars = s.toCharArray();

for (int i = 0; i < chars.length; i++) {
    // chars[i]
}
```

Thay ký tự trong mảng rồi tạo String mới:

```java
chars[0] = Character.toUpperCase(chars[0]);
String result = new String(chars);
```

Khác biệt:
- `s.charAt(i)` trả `char`, không sửa được String tại chỗ.
- `toCharArray()` tạo mảng có thể thay đổi.
- `new String(chars)` tạo String từ mảng char.

## 17.6. Cắt chuỗi theo delimiter khác nhau

| Đề ghi | Code |
|---|---|
| separated by comma | `s.split(",")` |
| separated by comma and space | `s.split(", ")` |
| separated by semicolon | `s.split(";")` |
| separated by one or more spaces | `s.trim().split("\\s+")` |
| split at every hyphen | `s.split("-")` |
| split by dot | `s.split("\\.")` |

Một số ký tự là ký tự đặc biệt trong regex:
- Dấu chấm: `"\\."`
- Dấu `|`: `"\\|"`
- Dấu `+`: `"\\+"`
- Dấu `*`: `"\\*"`
- Dấu `?`: `"\\?"`

Lấy phần trước/sau delimiter đầu tiên:

```java
int pos = s.indexOf(",");

if (pos >= 0) {
    String left = s.substring(0, pos);
    String right = s.substring(pos + 1);
}
```

## 17.7. Đổi chữ số char thành int và ngược lại

```java
char c = '7';
int digit = c - '0';       // 7
```

Ngược lại:

```java
int digit = 7;
char c = (char) ('0' + digit);
```

Chỉ dùng phép trừ `'0'` khi đã xác nhận `c` là digit.

## 17.8. Đếm số lần xuất hiện bằng vòng lặp

```java
int countOccurrences(String s, String target) {
    int count = 0;
    int pos = 0;

    while ((pos = s.indexOf(target, pos)) != -1) {
        count++;
        pos += target.length();
    }

    return count;
}
```

Mẫu trên đếm các lần xuất hiện **không chồng lấn**. Nếu đề yêu cầu cho phép overlap, tăng `pos` thêm 1 thay vì `target.length()`.

---

# 18. STRINGBUILDER – CÁC THAO TÁC BỔ SUNG

## 18.1. Overloads của append

```java
StringBuilder sb = new StringBuilder();

sb.append("Java");       // String
sb.append('A');          // char
sb.append(123);          // int
sb.append(3.14);         // double
sb.append(true);         // boolean
sb.append(new char[]{'O', 'O', 'P'});
```

Keyword: `append a value`, `append each item`, `build result`.

## 18.2. Overloads của insert

```java
sb.insert(0, "Start");
sb.insert(2, 'X');
sb.insert(1, 100);
sb.insert(3, 2.5);
```

Index hợp lệ từ `0` đến `sb.length()`.

## 18.3. Xóa / thay / sửa

```java
sb.delete(2, 5);         // xóa index 2,3,4
sb.deleteCharAt(0);      // xóa ký tự index 0
sb.replace(0, 2, "Hi");  // thay đoạn [0,2)
sb.setCharAt(0, 'J');    // sửa một char
```

## 18.4. Xóa space đầu/cuối bằng builder

```java
StringBuilder sb = new StringBuilder(s);

while (sb.length() > 0 && sb.charAt(0) == ' ') {
    sb.deleteCharAt(0);
}

while (sb.length() > 0
        && sb.charAt(sb.length() - 1) == ' ') {
    sb.deleteCharAt(sb.length() - 1);
}

String result = sb.toString();
```

Nếu chỉ cần bỏ khoảng trắng đầu/cuối thông thường, `s.trim()` ngắn hơn.

## 18.5. Tìm vị trí trong StringBuilder

```java
int first = sb.indexOf("ab");
int last = sb.lastIndexOf("ab");
```

## 18.6. Cắt lấy chuỗi

```java
String x = sb.substring(1);
String y = sb.substring(1, 4);
CharSequence z = sb.subSequence(1, 4);
```

`substring()` trả `String`, còn `subSequence()` trả `CharSequence`.

## 18.7. Đổi độ dài

```java
sb.setLength(3); // cắt còn 3 ký tự
```

Nếu tăng length, các vị trí mới được điền bằng ký tự null `\\u0000`. Không dùng để nối thêm khoảng trắng.

## 18.8. Capacity

```java
int cap = sb.capacity();
sb.ensureCapacity(100);
sb.trimToSize();
```

`capacity()` không phải số ký tự đang chứa; số ký tự hiện tại là `length()`.

## 18.9. So sánh nội dung StringBuilder

Không dùng `==` để so nội dung. Chuyển sang String:

```java
boolean same = sb1.toString().equals(sb2.toString());
```

---

# 19. CHARACTER – CÁC THAO TÁC BỔ SUNG

## 19.1. Bảng kiểm tra ký tự

| Keyword | Code |
|---|---|
| letter | `Character.isLetter(c)` |
| digit | `Character.isDigit(c)` |
| letter or digit | `Character.isLetterOrDigit(c)` |
| uppercase | `Character.isUpperCase(c)` |
| lowercase | `Character.isLowerCase(c)` |
| whitespace | `Character.isWhitespace(c)` |
| space character | `Character.isSpaceChar(c)` |
| convert to uppercase | `Character.toUpperCase(c)` |
| convert to lowercase | `Character.toLowerCase(c)` |
| numeric value | `Character.getNumericValue(c)` |

## 19.2. Chỉ giữ chữ và số

```java
StringBuilder result = new StringBuilder();

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (Character.isLetterOrDigit(c)) {
        result.append(c);
    }
}
```

## 19.3. Chỉ giữ nguyên chữ hoa

```java
StringBuilder result = new StringBuilder();

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (Character.isUpperCase(c)) {
        result.append(c);
    }
}
```

## 19.4. Đếm ký tự không phải chữ và không phải số

```java
int count = 0;

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if (!Character.isLetterOrDigit(c)) {
        count++;
    }
}
```

## 19.5. ASCII check

Nếu đề giới hạn alphabet A-Z/a-z:

```java
boolean isEnglishLetter =
        (c >= 'A' && c <= 'Z')
        || (c >= 'a' && c <= 'z');
```

Nếu đề nói chữ cái nói chung, dùng `Character.isLetter(c)`; không tự đồng nhất hai điều kiện trong mọi trường hợp.

---

# 20. NUMBER – CÁC THAO TÁC BỔ SUNG

## 20.1. Parse và convert

| Keyword | Code |
|---|---|
| String to int | `Integer.parseInt(s)` |
| String to double | `Double.parseDouble(s)` |
| String to long | `Long.parseLong(s)` |
| int to String | `String.valueOf(n)` |
| double to String | `String.valueOf(d)` |
| round to nearest int | `Math.round(d)` |
| absolute value | `Math.abs(n)` |

Ví dụ:

```java
int n = Integer.parseInt("123");
double d = Double.parseDouble("12.5");
String s = String.valueOf(100);
```

## 20.2. Chia nguyên và chia thực

```java
int a = 5 / 2;          // 2
double b = 5 / 2.0;     // 2.5
double c = (double) 5 / 2; // 2.5
```

## 20.3. Lấy phần nguyên/phần thập phân của double

```java
double x = 12.75;
int integerPart = (int) x;       // 12
double decimalPart = x - integerPart; // 0.75
```

## 20.4. Tính lũy thừa

```java
double result = Math.pow(base, exponent);
```

`Math.pow()` trả `double`.

## 20.5. Factorial (n!)

```java
long factorial(int n) {
    long result = 1;

    for (int i = 2; i <= n; i++) {
        result *= i;
    }

    return result;
}
```

## 20.6. Fibonacci

```java
void printFibonacci(int n) {
    int a = 0;
    int b = 1;

    for (int i = 0; i < n; i++) {
        System.out.print(a + " ");

        int next = a + b;
        a = b;
        b = next;
    }
}
```

## 20.7. Palindrome number

```java
boolean isPalindromeNumber(int n) {
    if (n < 0) return false;

    int original = n;
    int reverse = 0;

    while (n > 0) {
        int digit = n % 10;
        reverse = reverse * 10 + digit;
        n /= 10;
    }

    return original == reverse;
}
```

## 20.8. Armstrong number (mở rộng)

Với số có k chữ số, tổng mỗi chữ số mũ k bằng chính số đó:

```java
boolean isArmstrong(int n) {
    int original = n;
    int temp = n;
    int digits = String.valueOf(n).length();
    int sum = 0;

    while (temp > 0) {
        int digit = temp % 10;
        sum += (int) Math.pow(digit, digits);
        temp /= 10;
    }

    return sum == original;
}
```

Trường hợp `n == 0` trả true theo định nghĩa thông thường.

---

# 21. ARRAY – CÁC THAO TÁC BỔ SUNG

## 21.1. Khai báo / khởi tạo

```java
int[] a = new int[5];
int[] b = {1, 2, 3, 4};
String[] names = new String[3];
```

## 21.2. Truy cập / cập nhật

```java
int x = a[0];
a[0] = 100;
int n = a.length;
```

Array index từ 0 đến `length - 1`.

## 21.3. Copy array

```java
int[] copy1 = a.clone();
int[] copy2 = Arrays.copyOf(a, a.length);
int[] part = Arrays.copyOfRange(a, 1, 4);
```

Import:

```java
import java.util.Arrays;
```

## 21.4. Arrays utility

| Method | Tác dụng |
|---|---|
| `Arrays.sort(a)` | sort tăng dần |
| `Arrays.binarySearch(a, x)` | tìm nhị phân; array phải được sort |
| `Arrays.equals(a, b)` | so sánh nội dung array |
| `Arrays.fill(a, value)` | điền cùng giá trị |
| `Arrays.copyOf(a, n)` | copy với độ dài n |
| `Arrays.copyOfRange(a, from, to)` | copy đoạn `[from,to)` |
| `Arrays.toString(a)` | in array 1 chiều |
| `Arrays.deepToString(a)` | in nested array |
| `Arrays.asList(...)` | tạo List fixed-size từ phần tử tham chiếu |

## 21.5. Sort và tìm kiếm

```java
Arrays.sort(a);

int index = Arrays.binarySearch(a, target);
```

Binary search chỉ dùng sau khi array đã sắp xếp theo thứ tự phù hợp.

## 21.6. Insert một phần tử vào array

Array có kích thước cố định. Cách đơn giản là tạo array mới:

```java
int[] insert(int[] a, int index, int value) {
    int[] b = new int[a.length + 1];

    for (int i = 0; i < index; i++) {
        b[i] = a[i];
    }

    b[index] = value;

    for (int i = index; i < a.length; i++) {
        b[i + 1] = a[i];
    }

    return b;
}
```

## 21.7. Remove một phần tử khỏi array

```java
int[] removeAt(int[] a, int index) {
    int[] b = new int[a.length - 1];

    for (int i = 0, j = 0; i < a.length; i++) {
        if (i != index) {
            b[j++] = a[i];
        }
    }

    return b;
}
```

---

# 22. LIST / ARRAYLIST – CÁC THAO TÁC BỔ SUNG

## 22.1. Import

```java
import java.util.List;
import java.util.ArrayList;
import java.util.Iterator;
import java.util.Collections;
import java.util.Comparator;
```

## 22.2. ArrayList operations đầy đủ hơn

| Keyword | Method | Tác dụng |
|---|---|---|
| create list | `new ArrayList<>()` | tạo list |
| add at end | `add(x)` | thêm cuối |
| insert at index | `add(i, x)` | chèn tại index |
| get element | `get(i)` | lấy phần tử |
| update at index | `set(i, x)` | thay phần tử |
| remove by index | `remove(i)` | xóa vị trí |
| remove object | `remove(obj)` | xóa object đầu tiên khớp |
| contains | `contains(x)` | kiểm tra có |
| first index | `indexOf(x)` | index đầu |
| last index | `lastIndexOf(x)` | index cuối |
| size | `size()` | số phần tử |
| empty | `isEmpty()` | kiểm tra rỗng |
| clear | `clear()` | xóa hết |
| add all | `addAll(other)` | thêm toàn bộ collection |
| contains all | `containsAll(other)` | có chứa tất cả |
| remove all | `removeAll(other)` | xóa các phần tử thuộc other |
| retain all | `retainAll(other)` | chỉ giữ phần tử thuộc other |
| sub list | `subList(from,to)` | view của đoạn `[from,to)` |
| iterator | `iterator()` | iterator |
| convert to array | `toArray()` | chuyển thành Object[] |

## 22.3. Insert at index

```java
list.add(0, value); // chèn đầu
list.add(list.size(), value); // chèn cuối
list.add(2, value); // chèn index 2
```

Index phải nằm trong phạm vi `0..size()`.

## 22.4. Update an element

```java
list.set(1, newValue);
```

Nếu muốn sửa một field của object trong List:

```java
list.get(1).setPrice(100);
```

Khác nhau:
- `set(index, object)` thay object tại vị trí.
- `get(index).setField(value)` thay field của object đang có.

## 22.5. Remove – phân biệt hai overload

```java
list.remove(2); // xóa index 2
list.remove("Java"); // xóa object "Java"
```

Với `List<Integer>`:

```java
List<Integer> nums = new ArrayList<>();

nums.add(10);
nums.add(20);
nums.add(30);

nums.remove(1); // xóa phần tử index 1 (giá trị 20)
nums.remove(Integer.valueOf(10)); // xóa object giá trị 10
```

Đây là bẫy rất thường gặp vì `remove(int)` và `remove(Object)` cùng tên.

## 22.6. addAll / removeAll / retainAll

```java
list.addAll(other);       // thêm tất cả phần tử other
list.removeAll(other);    // xóa các phần tử có trong other
list.retainAll(other);    // chỉ giữ phần tử cũng có trong other
```

Keyword:
- `merge lists` → `addAll`.
- `remove all elements contained in another list` → `removeAll`.
- `keep only common elements` → `retainAll`.

## 22.7. Collections utility

| Method | Tác dụng |
|---|---|
| `Collections.sort(list)` | sort natural ascending |
| `Collections.sort(list, comparator)` | sort theo comparator |
| `Collections.reverse(list)` | đảo thứ tự hiện tại |
| `Collections.swap(list, i, j)` | đổi chỗ hai phần tử |
| `Collections.shuffle(list)` | xáo trộn |
| `Collections.max(list)` | phần tử lớn nhất |
| `Collections.min(list)` | phần tử nhỏ nhất |
| `Collections.frequency(list, x)` | số lần x xuất hiện |
| `Collections.fill(list, x)` | gán tất cả phần tử thành x |
| `Collections.copy(dest, src)` | copy vào list đích có `size()` ít nhất bằng `src.size()` |
| `Collections.binarySearch(list, x)` | tìm nhị phân trong list đã sort |

Ví dụ:

```java
Collections.sort(list);
Collections.reverse(list);
Collections.swap(list, 0, 1);
int max = Collections.max(numbers);
int count = Collections.frequency(numbers, 5);
```

**Cẩn thận:** `Collections.reverse(list)` đảo thứ tự hiện tại; nó không tương đương sort giảm dần.

## 22.8. Remove duplicates – giữ thứ tự

```java
List<String> unique = new ArrayList<>();

for (String x : list) {
    if (!unique.contains(x)) {
        unique.add(x);
    }
}
```

Nếu yêu cầu không cần giữ thứ tự, có thể dùng Set; nhưng đề nói `keep original order` thì dùng pattern trên hoặc LinkedHashSet.

## 22.9. Tìm phần tử thứ hai lớn nhất

```java
int largest = Integer.MIN_VALUE;
int second = Integer.MIN_VALUE;

for (int x : numbers) {
    if (x > largest) {
        second = largest;
        largest = x;
    } else if (x > second && x < largest) {
        second = x;
    }
}
```

Mẫu trên tìm **giá trị lớn thứ hai phân biệt**. Nếu đề coi hai giá trị lớn nhất bằng nhau là vị trí thứ hai, phải dùng logic khác.

## 22.10. Tạo List kết quả bằng filter

```java
List<Product> result = new ArrayList<>();

for (Product x : list) {
    if (condition) {
        result.add(x);
    }
}
```

Keyword:
- `return a new list containing ...`
- `keep only elements ...`
- `filter the list`
- `preserve the original list` (tạo list mới, không xóa list gốc).

---

# 23. LOOP / SEARCH / SORT – CÁC PATTERN CHUNG

## 23.1. for, while, do-while

```java
for (int i = 0; i < n; i++) {
    // known number/range of iterations
}
```

```java
while (condition) {
    // repeat while condition is true
}
```

```java
do {
    // executes at least once
} while (condition);
```

Keyword:
- `for each index` → for.
- `while the number is greater than 0` → while.
- `repeat until` → thường while với điều kiện phủ định.
- `at least once` → do-while có thể phù hợp.

## 23.2. break và continue

```java
if (conditionToStop) {
    break; // thoát loop hiện tại
}
```

```java
if (conditionToSkip) {
    continue; // bỏ phần còn lại của vòng hiện tại
}
```

Keyword:
- `stop searching after finding`
- `first matching item` → `break`.
- `skip invalid item` → `continue`.

## 23.3. Tìm kiếm tuyến tính (linear search)

```java
int index = -1;

for (int i = 0; i < a.length; i++) {
    if (a[i] == target) {
        index = i;
        break;
    }
}
```

## 23.4. Đếm các phần tử khớp (count matches)

```java
int count = 0;

for (int x : a) {
    if (condition) {
        count++;
    }
}
```

## 23.5. Sum conditional

```java
int sum = 0;

for (int x : a) {
    if (condition) {
        sum += x;
    }
}
```

## 23.6. Tạo chuỗi kết quả theo điều kiện

```java
StringBuilder result = new StringBuilder();

for (String x : words) {
    if (condition) {
        if (result.length() > 0) result.append(" ");
        result.append(x);
    }
}
```

## 23.7. Nested loop – so sánh mọi cặp

Keyword: `compare every pair`, `find duplicate pairs`.

```java
for (int i = 0; i < a.length; i++) {
    for (int j = i + 1; j < a.length; j++) {
        if (a[i] == a[j]) {
            // duplicate pair
        }
    }
}
```

## 23.8. Bubble sort – tự viết nếu đề không cho dùng sort

```java
for (int i = 0; i < a.length - 1; i++) {
    for (int j = 0; j < a.length - 1 - i; j++) {
        if (a[j] > a[j + 1]) {
            int temp = a[j];
            a[j] = a[j + 1];
            a[j + 1] = temp;
        }
    }
}
```

Giảm dần: đổi điều kiện `>` thành `<`.

---

# 24. JAVA OPERATORS / TYPE / OBJECT – BẢNG BỔ SUNG

## 24.1. Primitive types

| Type | Giá trị ví dụ |
|---|---|
| `byte` | `byte x = 10;` |
| `short` | `short x = 100;` |
| `int` | `int x = 1000;` |
| `long` | `long x = 100000L;` |
| `float` | `float x = 1.5f;` |
| `double` | `double x = 1.5;` |
| `char` | `char c = 'A';` |
| `boolean` | `boolean ok = true;` |

## 24.2. Increment / decrement

```java
i++;
++i;
i--;
--i;
```

- `i++`: dùng giá trị cũ rồi tăng.
- `++i`: tăng trước rồi dùng giá trị mới.

Trong câu lệnh riêng `i++;` và `++i;` đều tăng 1, nhưng trong biểu thức chúng có khác biệt.

## 24.3. Compound assignment

```java
x += y; // x = x + y
x -= y; // x = x - y
x *= y; // x = x * y
x /= y; // x = x / y
x %= y; // x = x % y
```

## 24.4. Casting

```java
double d = 10;       // widening
int n = (int) 3.9;   // narrowing, n = 3
```

## 24.5. `static` và `final`

```java
static int count;           // class-level field
final double PI = 3.14159;  // không gán lại
static final int MAX = 100;
```

Keyword:
- `shared by all objects` → static field.
- `constant`, `cannot be changed` → final.
- `class method` → static method (không truy cập trực tiếp instance field).

## 24.6. `instanceof`

```java
if (obj instanceof Product) {
    Product p = (Product) obj;
}
```

Dùng kiểm tra object có thuộc kiểu class/interface nhất định hay không.

---

# 25. INTERFACE / ABSTRACT / POLYMORPHISM – MỞ RỘNG

## 25.1. Interface

```java
public interface IProduct {
    int f1(List<Product> list);
    void f2(List<Product> list);
}
```

```java
public class MyProduct implements IProduct {
    @Override
    public int f1(List<Product> list) {
        return 0;
    }

    @Override
    public void f2(List<Product> list) {
    }
}
```

## 25.2. Abstract class

```java
public abstract class Animal {
    public abstract void sound();

    public void eat() {
        System.out.println("Eating");
    }
}
```

```java
public class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Bark");
    }
}
```

Keyword:
- `abstract class`
- `abstract method`
- `must implement all abstract methods`.

## 25.3. Polymorphism

```java
Animal a = new Dog();
a.sound(); // gọi phiên bản Dog nếu override
```

Keyword:
- `polymorphism`
- `dynamic binding`
- `parent reference, child object`.

## 25.4. Overloading

```java
int sum(int a, int b) {
    return a + b;
}

double sum(double a, double b) {
    return a + b;
}

int sum(int a, int b, int c) {
    return a + b + c;
}
```

Cùng tên, khác parameter list.

---

# 26. EXCEPTION – MỞ RỘNG NẾU ĐỀ YÊU CẦU

```java
try {
    int n = Integer.parseInt(s);
} catch (NumberFormatException e) {
    System.out.println("Invalid number");
} finally {
    // executes whether exception occurs or not
}
```

Ném exception:

```java
throw new IllegalArgumentException("Invalid value");
```

Khai báo method có thể ném exception:

```java
public void read() throws IOException {
    // ...
}
```

Keyword:
- `try`
- `catch`
- `finally`
- `throw`
- `throws`
- `handle exception`
- `invalid input`.

Không tự thêm catch/throw nếu skeleton/đề không yêu cầu.

---

# 27. ENGLISH → JAVA – BẢNG KEYWORD MỞ RỘNG

| English phrase | Nghĩa | Cách triển khai |
|---|---|---|
| starts with a vowel | bắt đầu bằng nguyên âm | `charAt(0)` + kiểm tra `a,e,i,o,u` |
| ends with a digit | kết thúc bằng số | `Character.isDigit(s.charAt(s.length()-1))` |
| contains at least one digit | có ít nhất 1 digit | loop + boolean |
| contains only letters | chỉ có chữ cái | `matches("[A-Za-z]+")` hoặc loop |
| remove all spaces | xóa mọi space | loop hoặc `replace(" ", "")` |
| remove leading/trailing spaces | bỏ space đầu/cuối | `trim()` |
| remove duplicate characters | bỏ ký tự trùng | boolean array/Set |
| keep distinct characters | chỉ giữ ký tự duy nhất | Set hoặc mảng đánh dấu |
| count occurrences | đếm số lần xuất hiện | counter trong loop |
| first occurrence | lần đầu | `indexOf()` |
| last occurrence | lần cuối | `lastIndexOf()` |
| lexicographically smaller | nhỏ hơn theo từ điển | `compareTo() < 0` |
| alphabetically sorted | sort theo alphabet | `compareTo()` comparator |
| sort by price | sort theo price | Comparator |
| sort by name then price | nhiều tiêu chí | `thenComparing()` |
| swap two elements | đổi chỗ | temp hoặc `Collections.swap()` |
| reverse the list | đảo list | `Collections.reverse()` |
| reverse the array | đảo array | hai con trỏ |
| merge two lists | gộp list | `addAll()` |
| common elements | phần tử chung | `retainAll()` |
| remove duplicates | bỏ trùng | contains/Set |
| second largest | lớn thứ hai | largest + second |
| update every matching object | cập nhật mọi object khớp | for-each + setter |
| first matching object | object đầu tiên khớp | loop + break |
| all matching objects | tất cả object khớp | loop hết |
| preserve original order | giữ thứ tự ban đầu | filter + append |
| without changing original list | không thay list gốc | tạo List mới |
| return empty string | trả chuỗi rỗng | `return "";` |
| return zero if no match | không có thì trả 0 | kiểm tra count/found |
| round to two decimal places | làm tròn/format 2 số | `String.format("%.2f", x)` nếu yêu cầu String format |
| truncate decimal | cắt phần thập phân | ép kiểu hoặc phép toán; không đồng nghĩa round |
| absolute difference | độ chênh tuyệt đối | `Math.abs(a-b)` |

---

# 28. NHỮNG BẪY CẦN GHI NHỚ

## 28.1. `String` vs `StringBuilder`

| Việc cần làm | String | StringBuilder |
|---|---|---|
| lấy length | `s.length()` | `sb.length()` |
| lấy char | `s.charAt(i)` | `sb.charAt(i)` |
| substring | có | có |
| uppercase/lowercase | có | không |
| split | có | không |
| contains | có | không |
| append | `s += x` | `sb.append(x)` |
| insert | không sửa tại chỗ | `sb.insert(i,x)` |
| delete | substring/tạo String mới | `sb.delete()` |
| replace | `s.replace()` tạo String mới | `sb.replace()` sửa tại chỗ |
| reverse | không có method trực tiếp | `sb.reverse()` |
| set char | không sửa tại chỗ | `sb.setCharAt()` |

## 28.2. Array vs String vs List

| Cấu trúc | Độ dài/số phần tử |
|---|---|
| Array | `a.length` |
| String | `s.length()` |
| List | `list.size()` |
| StringBuilder | `sb.length()` |

## 28.3. `remove` của List

```java
List<Integer> x = new ArrayList<>();
x.add(10);
x.add(20);
x.add(30);

x.remove(1);                  // remove index 1 => value 20
x.remove(Integer.valueOf(10)); // remove value 10
```

## 28.4. `sort` và `reverse` khác nhau

```java
Collections.sort(list);    // sắp xếp theo natural order
Collections.reverse(list); // đảo thứ tự đang có
```

Reverse một list chưa sort không đảm bảo tạo thứ tự descending.

## 28.5. `binarySearch` cần dữ liệu đã sort

```java
Collections.sort(list);
int pos = Collections.binarySearch(list, target);
```

Nếu chưa sort theo cùng comparator, kết quả không đáng tin cậy.

## 28.6. `substring` end-exclusive

```java
"ABCDE".substring(1, 4); // "BCD", không lấy index 4
```

## 28.7. `split` dùng regex

```java
s.split(".");    // sai ý định nếu muốn dấu chấm literal
s.split("\\.");  // đúng: tách theo dấu chấm
```

---

# 29. DANH SÁCH ƯU TIÊN ÔN THEO 8 ĐỀ MẪU

**Nhóm đã xuất hiện trực tiếp và nên nắm chắc:**
1. Class, attributes, constructors, getter/setter, `toString()`.
2. String: `substring`, `charAt`, `length`, `toUpperCase`, `toLowerCase`, `split`.
3. Điều kiện `if/else`, công thức số học, ngưỡng `>`/`>=`.
4. Inheritance: `extends`, `super`, constructor cha, override.
5. Interface: `implements`, đúng method signature.
6. List: duyệt, sum, tìm min/max, sort, remove, update theo điều kiện.
7. Character: `isLetter`, `isDigit`, `isUpperCase`, `isLowerCase`.
8. Number: `%`, `/`, đếm số chữ số chẵn/lẻ.
9. Acronym và Decimal → Binary.
10. Format output chính xác, không tự thêm space/format.

**Nhóm mở rộng nên tra nếu đề có keyword tương ứng:**
- StringBuilder thao tác insert/delete/replace/reverse.
- String regex, compareTo, indexOf/lastIndexOf.
- Arrays utility và array insert/remove.
- Collections utility, duplicate removal, second largest.
- Prime, factorial, Fibonacci, GCD/LCM.
- Abstract class, polymorphism, exception handling.

---

# 30. NGUYÊN TẮC TRA CỨU NHANH

1. Tìm **động từ**: count, sum, replace, remove, update, sort, return, convert.
2. Tìm **đối tượng**: character, word, String, number, object, List.
3. Tìm **phạm vi**: first, last, each, all, every, first matching.
4. Tìm **điều kiện**: at least, exactly, greater than, different, contains.
5. Tìm **output**: int, double, String, object, void; comma/space/two decimals.
6. Tra bảng tương ứng rồi chép pattern.
7. Thay đúng tên biến và điều kiện trong đề, không giữ nguyên ví dụ nếu ngưỡng khác.

**Mục tiêu:** không cần nhớ tên từng method. Nhìn keyword tiếng Anh là xác định được nhóm thao tác và mở đúng code mẫu.


---

# PRO192 V5 – DECLARATION & CODE-BUILDING ATLAS
## Bổ sung khai báo đầy đủ và các thao tác thường phải tự viết

> **Vì sao có chương này?** Một snippet chỉ có `x += 1` chưa đủ để tra khi bạn không nhớ phải khai báo `x` là kiểu gì, đặt ở đâu, cần import gì và method phải có return type nào. Chương này đi từ **khai báo → khởi tạo → sử dụng → trả kết quả**.
>
> Các ví dụ ưu tiên Java 8. Những cú pháp ít có khả năng xuất hiện trong đề được ghi là **MỞ RỘNG**, không xem là nội dung chắc chắn thi.

# 31. DECLARATION – KHAI BÁO MỌI THỨ TỪ ĐẦU

## 31.1. Keyword nhận diện yêu cầu khai báo

| Keyword đề bài | Nghĩa | Bạn cần viết |
|---|---|---|
| declare a variable | khai báo biến | `type name;` |
| initialize a variable | khai báo và gán giá trị ban đầu | `type name = value;` |
| assign a value | gán giá trị | `name = value;` |
| declare a constant | khai báo hằng | `final type NAME = value;` |
| declare an array | khai báo mảng | `type[] arr;` |
| create an array of size n | tạo mảng n phần tử | `new type[n]` |
| initialize an array | khởi tạo mảng | `{...}` hoặc `new type[]{...}` |
| declare a two-dimensional array | khai báo mảng 2 chiều | `type[][] matrix;` |
| create an object / instantiate | tạo object | `ClassName obj = new ClassName(...);` |
| declare a method | khai báo method | `returnType name(parameters)` |
| define a class | khai báo class | `public class ClassName` |
| define an interface | khai báo interface | `public interface IName` |
| implement an interface | triển khai interface | `class X implements IName` |
| extend a class | kế thừa class | `class B extends A` |
| import a class/package | import | `import ...;` |
| declare a generic type | khai báo generic | `List<Type>`, `class Box<T>` |

## 31.2. Khai báo biến primitive

| Type | Declaration | Ví dụ |
|---|---|---|
| byte | `byte x;` | `byte age = 20;` |
| short | `short x;` | `short year = 2026;` |
| int | `int x;` | `int quantity = 10;` |
| long | `long x;` | `long population = 1000000L;` |
| float | `float x;` | `float rate = 1.5f;` |
| double | `double x;` | `double price = 12.5;` |
| char | `char x;` | `char grade = 'A';` |
| boolean | `boolean x;` | `boolean found = false;` |

```java
int id;
double price;
String name;

id = 1;
price = 19.5;
name = "Java";
```

Khai báo và khởi tạo cùng lúc:

```java
int id = 1;
double price = 19.5;
String name = "Java";
boolean active = true;
```

Khai báo nhiều biến cùng kiểu:

```java
int a = 1, b = 2, c = 3;
```

Không khai báo một nhóm nhiều kiểu khác nhau trong cùng một câu lệnh.

## 31.3. Giá trị mặc định của field

Khi field không được gán trong constructor, Java tự khởi tạo mặc định:

| Field type | Default |
|---|---|
| `byte`, `short`, `int`, `long` | `0` |
| `float` | `0.0f` |
| `double` | `0.0` |
| `char` | `'\u0000'` |
| `boolean` | `false` |
| object / `String` / array | `null` |

**Quan trọng:** biến local bên trong method không tự có giá trị mặc định. Phải khởi tạo trước khi đọc:

```java
public void test() {
    int x;
    // System.out.println(x); // compile error
}
```

Đúng:

```java
public void test() {
    int x = 0;
    System.out.println(x);
}
```

Nếu đề yêu cầu String mặc định là `""`, phải gán `""`; mặc định Java của String field là `null`.

## 31.4. Khai báo hằng (constant)

Keyword: `constant`, `fixed value`, `cannot be changed`.

```java
final double PI = 3.14159;
final int MAX_SIZE = 100;
```

Hằng cấp class:

```java
public static final double TAX_RATE = 0.1;
```

- `final`: không thể gán lại sau khi đã khởi tạo.
- `static`: thuộc class, không cần tạo object để truy cập.
- Quy ước tên hằng: chữ hoa và dấu `_`.

## 31.5. Khai báo String và char

```java
String name = "Coffee Shop"; // double quotes
char grade = 'A';            // single quotes
char space = ' ';
String empty = "";
String value = null;
```

`'A'` là `char`; `"A"` là `String`. Hai kiểu này không thể thay thế nhau tùy ý.

## 31.6. Khai báo array

Keyword:
- `declare an array`
- `create an array`
- `array of integers`
- `array of String`
- `initialize the array`

Khai báo:

```java
int[] numbers;
String[] names;
Product[] products;
```

Tạo array có kích thước:

```java
numbers = new int[5];
names = new String[10];
```

Khai báo và tạo:

```java
int[] numbers = new int[5];
String[] names = new String[3];
```

Khai báo và khởi tạo giá trị trực tiếp:

```java
int[] a = {2, 4, 6, 8};
String[] words = {"Java", "OOP", "PRO192"};
```

Dạng `new` tường minh:

```java
int[] a = new int[]{2, 4, 6};
```

Lấy số phần tử:

```java
int n = a.length;
```

Lấy/sửa phần tử:

```java
int first = a[0];
a[0] = 100;
```

## 31.7. Khai báo mảng 2 chiều

Keyword: `two-dimensional array`, `matrix`, `rows and columns`.

```java
int[][] matrix = new int[3][4];
```

Khởi tạo trực tiếp:

```java
int[][] a = {
    {1, 2, 3},
    {4, 5, 6}
};
```

Truy cập:

```java
int value = a[0][1];
a[1][2] = 99;
```

Duyệt:

```java
for (int i = 0; i < a.length; i++) {
    for (int j = 0; j < a[i].length; j++) {
        System.out.print(a[i][j] + " ");
    }
}
```

Số hàng: `a.length`; số cột của hàng i: `a[i].length`.

Mảng 2 chiều không đều (jagged array):

```java
int[][] a = new int[3][];
a[0] = new int[2];
a[1] = new int[4];
a[2] = new int[1];
```

## 31.8. Khai báo object và gọi method

Keyword: `create an object`, `instantiate`, `create an instance`.

```java
Product p;                 // declaration only
p = new Product();         // instantiate
```

Kết hợp:

```java
Product p = new Product();
Product p2 = new Product("Coffee", 20);
```

Gọi method:

```java
String name = p.getName();
p.setPrice(100);
System.out.println(p.toString());
```

Có thể truyền object làm tham số:

```java
public void display(Product p) {
    System.out.println(p.getName());
}
```

Trả về object:

```java
public Product createProduct() {
    return new Product("Book", 10);
}
```

**Phân biệt:**
- `Product p;`: mới khai báo biến reference, chưa tạo object.
- `new Product()`: tạo object.
- `p = new Product()`: gán reference tới object vừa tạo.

## 31.9. Khai báo method – đầy đủ cấu trúc

Cú pháp tổng quát:

```java
[accessModifier] [static] returnType methodName(parameterList) {
    // statements
    return value; // nếu returnType khác void
}
```

Ví dụ không tham số, trả int:

```java
public int getAge() {
    return age;
}
```

Có tham số, trả double:

```java
public double calculatePrice(int quantity, double unitPrice) {
    return quantity * unitPrice;
}
```

Không trả về:

```java
public void display() {
    System.out.println("Hello");
}
```

Trả String:

```java
public String getFullName() {
    return firstName + " " + lastName;
}
```

Trả boolean:

```java
public boolean isAdult() {
    return age >= 18;
}
```

Method static:

```java
public static int square(int n) {
    return n * n;
}
```

Method nhận array:

```java
public int sum(int[] numbers) {
    int total = 0;

    for (int x : numbers) {
        total += x;
    }

    return total;
}
```

Method nhận List:

```java
public int sum(List<Integer> numbers) {
    int total = 0;

    for (int x : numbers) {
        total += x;
    }

    return total;
}
```

## 31.10. Method return type – phải khai báo đúng

| Muốn trả về | Header |
|---|---|
| số nguyên | `public int f()` |
| số thực | `public double f()` |
| chuỗi | `public String f()` |
| ký tự | `public char f()` |
| đúng/sai | `public boolean f()` |
| object Product | `public Product f()` |
| List Product | `public List<Product> f()` |
| không trả về | `public void f()` |

Ví dụ:

```java
public int getCount() {
    return count;
}
```

```java
public void setCount(int count) {
    this.count = count;
}
```

**Không viết `return` có giá trị trong method `void`; không quên return ở method có kiểu trả về.**

## 31.11. Khai báo class

```java
public class Product {
    // fields
    // constructors
    // methods
}
```

Một file public class thường có tên file trùng tên class:

```text
Product.java → public class Product
```

## 31.12. Khai báo interface

```java
public interface IProduct {
    int calculate();
    void display();
}
```

Implement:

```java
public class MyProduct implements IProduct {
    @Override
    public int calculate() {
        return 0;
    }

    @Override
    public void display() {
        System.out.println("Product");
    }
}
```

Trong interface thông thường, method không có body mặc định là `public abstract`. Field trong interface là `public static final`.

Java 8 còn hỗ trợ `default` và `static` method trong interface, nhưng không tự thêm nếu đề không yêu cầu.

## 31.13. Khai báo abstract class

```java
public abstract class Animal {
    public abstract void sound();

    public void eat() {
        System.out.println("Eating");
    }
}
```

Subclass:

```java
public class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Bark");
    }
}
```

Không thể `new Animal()` nếu Animal là abstract.

## 31.14. Khai báo generic type

Keyword: `generic`, `type parameter`, `List of Product`.

```java
List<Product> products = new ArrayList<>();
List<String> names = new ArrayList<>();
List<Integer> numbers = new ArrayList<>();
```

Generic class đơn giản:

```java
public class Box<T> {
    private T value;

    public Box(T value) {
        this.value = value;
    }

    public T getValue() {
        return value;
    }
}
```

Dùng:

```java
Box<String> b = new Box<>("Java");
String s = b.getValue();
```

## 31.15. Package và import

```java
package myapp;
```

Import một class:

```java
import java.util.Scanner;
```

Import một nhóm class:

```java
import java.util.*;
```

Trong các PE mẫu có instruction yêu cầu không dùng package/default package. Nếu đề ghi như vậy thì **không thêm dòng `package ...;`**.

---

# 32. KHAI BÁO COLLECTIONS – CÁC KIỂU DỮ LIỆU DANH SÁCH

## 32.1. List / ArrayList

```java
List<Integer> numbers = new ArrayList<>();
List<String> names = new ArrayList<>();
List<Product> products = new ArrayList<>();
```

Hoặc khai báo theo implementation:

```java
ArrayList<Product> products = new ArrayList<>();
```

Trong method implement interface, giữ nguyên parameter type của interface, ví dụ `List<Product>`.

Thêm dữ liệu mẫu:

```java
List<String> names = new ArrayList<>();

names.add("An");
names.add("Binh");
names.add("Chi");
```

## 32.2. Set – dữ liệu không trùng

```java
import java.util.Set;
import java.util.HashSet;
import java.util.LinkedHashSet;
import java.util.TreeSet;

Set<String> names = new HashSet<>();
Set<String> ordered = new LinkedHashSet<>();
Set<Integer> sorted = new TreeSet<>();
```

| Loại | Đặc điểm |
|---|---|
| `HashSet` | không đảm bảo thứ tự |
| `LinkedHashSet` | giữ insertion order |
| `TreeSet` | sort theo natural order/comparator |

Methods:

```java
set.add("Java");
set.remove("Java");
set.contains("Java");
set.size();
set.isEmpty();
set.clear();
```

Keyword: `unique`, `distinct`, `no duplicates`, `set of values`.

## 32.3. Map – key/value

```java
import java.util.Map;
import java.util.HashMap;
import java.util.TreeMap;
import java.util.LinkedHashMap;

Map<String, Integer> scores = new HashMap<>();
```

Thêm/cập nhật:

```java
scores.put("An", 90);
scores.put("Binh", 85);
```

Lấy:

```java
int score = scores.get("An");
```

Lấy có default nếu key không tồn tại:

```java
int score = scores.getOrDefault("Chi", 0);
```

Kiểm tra:

```java
scores.containsKey("An");
scores.containsValue(90);
```

Xóa:

```java
scores.remove("An");
```

Duyệt key/value:

```java
for (Map.Entry<String, Integer> entry : scores.entrySet()) {
    String key = entry.getKey();
    int value = entry.getValue();
}
```

Keyword: `key-value pairs`, `mapping`, `frequency table`, `count occurrences`.

Đếm frequency bằng Map:

```java
Map<Character, Integer> freq = new HashMap<>();

for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);
    freq.put(c, freq.getOrDefault(c, 0) + 1);
}
```

## 32.4. Wrapper classes

| Primitive | Wrapper |
|---|---|
| `int` | `Integer` |
| `double` | `Double` |
| `long` | `Long` |
| `float` | `Float` |
| `char` | `Character` |
| `boolean` | `Boolean` |

Autoboxing/unboxing:

```java
Integer x = 10; // int -> Integer
int y = x;      // Integer -> int
```

`List<int>` không hợp lệ; phải dùng `List<Integer>`.

---

# 33. DECLARATION + ALGORITHM – MẪU METHOD HOÀN CHỈNH

Chương này minh họa cách không để sót khai báo khi lấy pattern áp dụng.

## 33.1. Đếm chữ hoa trong String

```java
public int countUppercase(String s) {
    int count = 0;

    for (int i = 0; i < s.length(); i++) {
        char c = s.charAt(i);

        if (Character.isUpperCase(c)) {
            count++;
        }
    }

    return count;
}
```

## 33.2. Đếm chữ số khác nhau

```java
public int countDifferentDigits(String s) {
    boolean[] seen = new boolean[10];
    int count = 0;

    for (int i = 0; i < s.length(); i++) {
        char c = s.charAt(i);

        if (Character.isDigit(c)) {
            int digit = c - '0';

            if (!seen[digit]) {
                seen[digit] = true;
                count++;
            }
        }
    }

    return count;
}
```

## 33.3. Tìm Product có giá thấp nhất trong List

```java
public Product findMinPrice(List<Product> list) {
    if (list == null || list.isEmpty()) {
        return null;
    }

    Product min = list.get(0);

    for (Product p : list) {
        if (p.getPrice() < min.getPrice()) {
            min = p;
        }
    }

    return min;
}
```

## 33.4. Remove tất cả Product price âm

```java
public void removeNegativePrice(List<Product> list) {
    for (int i = list.size() - 1; i >= 0; i--) {
        if (list.get(i).getPrice() < 0) {
            list.remove(i);
        }
    }
}
```

## 33.5. Tạo List mới chỉ chứa Product price > 100

```java
public List<Product> filterExpensive(List<Product> list) {
    List<Product> result = new ArrayList<>();

    for (Product p : list) {
        if (p.getPrice() > 100) {
            result.add(p);
        }
    }

    return result;
}
```

Cần import `List` và `ArrayList`.

## 33.6. Chèn phần tử vào array

```java
public int[] insert(int[] a, int index, int value) {
    int[] result = new int[a.length + 1];

    for (int i = 0; i < index; i++) {
        result[i] = a[i];
    }

    result[index] = value;

    for (int i = index; i < a.length; i++) {
        result[i + 1] = a[i];
    }

    return result;
}
```

## 33.7. Xóa phần tử khỏi array

```java
public int[] removeAt(int[] a, int index) {
    int[] result = new int[a.length - 1];

    for (int i = 0, j = 0; i < a.length; i++) {
        if (i != index) {
            result[j] = a[i];
            j++;
        }
    }

    return result;
}
```

## 33.8. Method có tham số object

```java
public boolean isExpensive(Product p) {
    return p.getPrice() > 100;
}
```

## 33.9. Method nhận nhiều tham số

```java
public double calculateTotal(double unitPrice, int quantity) {
    return unitPrice * quantity;
}
```

## 33.10. Method trả về mảng

```java
public int[] getEvenNumbers(int[] a) {
    int count = 0;

    for (int x : a) {
        if (x % 2 == 0) {
            count++;
        }
    }

    int[] result = new int[count];
    int index = 0;

    for (int x : a) {
        if (x % 2 == 0) {
            result[index++] = x;
        }
    }

    return result;
}
```

---

# 34. IMPORT CHEAT SHEET – NHỚ IMPORT GÌ?

| Dùng | Import |
|---|---|
| `Scanner` | `import java.util.Scanner;` |
| `ArrayList` | `import java.util.ArrayList;` |
| `List` | `import java.util.List;` |
| `Iterator` | `import java.util.Iterator;` |
| `Collections` | `import java.util.Collections;` |
| `Comparator` | `import java.util.Comparator;` |
| `Arrays` | `import java.util.Arrays;` |
| `Set` | `import java.util.Set;` |
| `HashSet` | `import java.util.HashSet;` |
| `LinkedHashSet` | `import java.util.LinkedHashSet;` |
| `TreeSet` | `import java.util.TreeSet;` |
| `Map` | `import java.util.Map;` |
| `HashMap` | `import java.util.HashMap;` |
| `TreeMap` | `import java.util.TreeMap;` |
| `StringBuilder` | Không cần import (`java.lang`) |
| `Math` | Không cần import (`java.lang`) |
| `String` | Không cần import (`java.lang`) |
| `Character` | Không cần import (`java.lang`) |
| `Integer` | Không cần import (`java.lang`) |

`java.lang` được import tự động. Các class trong `java.util` không được import tự động.

---

# 35. BẢNG CHẨN ĐOÁN KHI KHÔNG BIẾT KHAI BÁO GÌ

| Bạn cần lưu gì? | Khai báo |
|---|---|
| một số nguyên | `int count = 0;` |
| một số thực | `double total = 0.0;` |
| một ký tự | `char c = ' ';` |
| một chuỗi | `String result = "";` |
| trạng thái đúng/sai | `boolean found = false;` |
| mảng số nguyên | `int[] a = new int[n];` |
| mảng chuỗi | `String[] words = s.split(" ");` |
| mảng đánh dấu digit | `boolean[] seen = new boolean[10];` |
| danh sách số nguyên | `List<Integer> a = new ArrayList<>();` |
| danh sách String | `List<String> a = new ArrayList<>();` |
| danh sách object | `List<Product> a = new ArrayList<>();` |
| chuỗi tích lũy mutable | `StringBuilder sb = new StringBuilder();` |
| object mới | `Product p = new Product();` |
| map đếm tần suất | `Map<Character, Integer> freq = new HashMap<>();` |
| vị trí chưa tìm thấy | `int index = -1;` |
| giá trị min ban đầu | `int min = Integer.MAX_VALUE;` |
| giá trị max ban đầu | `int max = Integer.MIN_VALUE;` |
| số lượng đếm | `int count = 0;` |
| tổng cộng dồn | `int sum = 0;` |
| tích cộng dồn | `long product = 1;` |

---

# 36. KẾT LUẬN: CÁCH DÙNG PHẦN BỔ SUNG

Khi gặp đề mới, không chỉ tìm tên method. Hãy kiểm tra đủ 4 tầng:

1. **Declaration:** biến/array/List/StringBuilder/object nào cần khai báo? Kiểu gì? Khởi tạo bằng gì?
2. **Operation:** cần gọi method nào (`split`, `append`, `remove`, `sort`, `charAt`...)?
3. **Control flow:** dùng `if`, `for`, `while`, nested loop hay `break`?
4. **Return/output:** method trả kiểu gì? Có cần `toString()`/format/space không?

Ví dụ yêu cầu “count the number of different digits in each word”:
- Declaration: `boolean[] seen = new boolean[10]`, `int count = 0`.
- Operation: `split(" ")`, `charAt(i)`, `Character.isDigit(c)`.
- Control flow: loop từng word, loop từng character.
- Return: tăng tổng số word thỏa điều kiện hoặc trả count theo signature.

**Đó là mức tra cứu cần đạt: không chỉ nhớ một câu lệnh, mà biết khai báo đầy đủ để viết được method chạy được.**


---

# PRO192 V6 – EXAM TASK RECIPES & DECLARATION TEMPLATES
## Bổ sung theo audit 8 đề gốc: khai báo hoàn chỉnh + bài mẫu đúng câu chữ đề

> Bản này tập trung vào khoảng trống của các phiên bản trước: code scaffolding, khai báo biến/return type, và các **task recipe hoàn chỉnh** rút trực tiếp từ đề mẫu.
>
> **Quy ước nguồn:**
> - **[ĐỀ GỐC]**: yêu cầu được nhìn thấy trong các PDF đã gửi.
> - **[BIẾN THỂ ĐỀ]**: cùng một dạng nhưng các PDF khác nhau đổi điều kiện/chiều sort/ký tự.
> - **[MỞ RỘNG]**: kỹ thuật Java hữu ích nhưng không khẳng định là đề đã hỏi.

# 37. TẠO MỘT METHOD TỪ ZERO – KHUNG KHAI BÁO BẮT BUỘC

Đây là thứ phải xác định trước khi viết phần xử lý.

## 37.1. Method declaration – chọn đúng return type

| Đề yêu cầu method trả về | Khai báo |
|---|---|
| return an integer / number of items | `public int f(...)` |
| return a decimal number / price | `public double f(...)` |
| return a String / new string | `public String f(...)` |
| return a character | `public char f(...)` |
| return true or false / whether | `public boolean f(...)` |
| return a Product object | `public Product f(...)` |
| return a list of Product objects | `public List<Product> f(...)` |
| perform an action / update / remove, no result | `public void f(...)` |

Ví dụ nhận một String và trả về số lượng chữ số:

```java
public int countDigits(String s) {
    int count = 0;

    for (int i = 0; i < s.length(); i++) {
        if (Character.isDigit(s.charAt(i))) {
            count++;
        }
    }

    return count;
}
```

Ví dụ nhận List và trả về object:

```java
public Product findMax(List<Product> t) {
    if (t == null || t.isEmpty()) {
        return null;
    }

    Product max = t.get(0);

    for (Product x : t) {
        if (x.getPrice() > max.getPrice()) {
            max = x;
        }
    }

    return max;
}
```

Ví dụ nhận List và thay đổi dữ liệu:

```java
public void updateAll(List<Product> t) {
    for (Product x : t) {
        if (x.getPrice() < 0) {
            x.setPrice(0);
        }
    }
}
```

## 37.2. Khai báo tham số – nhìn vào loại dữ liệu đề đưa vào

| Đề nói method nhận | Parameter |
|---|---|
| a string | `String str` |
| an integer | `int n` |
| a decimal/double | `double value` |
| a character | `char c` |
| a Product object | `Product p` |
| a list of Products | `List<Product> t` |
| an array of integers | `int[] a` |
| an array of Strings | `String[] words` |
| two integers | `int a, int b` |
| a String and an integer | `String s, int n` |

## 37.3. Khai báo biến theo chức năng

| Bạn cần lưu | Khai báo |
|---|---|
| tổng | `int sum = 0;` |
| tổng số thực | `double sum = 0.0;` |
| bộ đếm | `int count = 0;` |
| max của số | `int max = Integer.MIN_VALUE;` |
| min của số | `int min = Integer.MAX_VALUE;` |
| max length | `int maxLength = -1;` |
| trạng thái đã tìm thấy | `boolean found = false;` |
| kết quả String | `String result = "";` |
| kết quả nối nhiều lần | `StringBuilder result = new StringBuilder();` |
| vị trí chưa tìm thấy | `int index = -1;` |
| object tốt nhất hiện tại | `Product best = t.get(0);` |
| số chữ hoa | `int upper = 0;` |
| số chữ thường | `int lower = 0;` |
| số chữ số | `int digits = 0;` |
| đánh dấu 10 chữ số đã thấy | `boolean[] seen = new boolean[10];` |
| danh sách kết quả | `List<Product> result = new ArrayList<>();` |

## 37.4. Full method skeleton có khai báo đầy đủ

```java
public ReturnType methodName(ParameterType parameterName) {

    // 1. Declare local variables
    int count = 0;
    String result = "";

    // 2. Process input
    for (int i = 0; i < parameterName.length(); i++) {
        // 3. Condition
        if (condition) {
            count++;
        }
    }

    // 4. Return value if required
    return result;
}
```

Không copy nguyên `ReturnType`, `ParameterType`, `condition`; đó là placeholder. Thay theo method signature trong đề.

---

# 38. FULL CLASS SKELETON – TỪ FILE JAVA TRỐNG ĐẾN CLASS HOÀN CHỈNH

## 38.1. Class thông thường trong default package

```java
import java.util.List;
import java.util.ArrayList;
import java.util.Comparator;
import java.util.Iterator;

public class MyClass {

    // Fields
    private String name;
    private int price;

    // Default constructor
    public MyClass() {
        name = "";
        price = 0;
    }

    // Parameterized constructor
    public MyClass(String name, int price) {
        this.name = name;
        this.price = price;
    }

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String name) {
        this.name = name;
    }

    // Custom method
    public int calculate() {
        return price * 2;
    }

    // toString
    @Override
    public String toString() {
        return name + "," + price;
    }
}
```

Nếu đề yêu cầu default package, **không thêm `package ...;`**. Chỉ import thư viện cần dùng.

## 38.2. Class implements interface skeleton

```java
import java.util.List;

public class MyClass implements IMyInterface {

    @Override
    public int f1(List<Product> t) {
        int result = 0;

        // processing

        return result;
    }

    @Override
    public void f2(List<Product> t) {
        // update/remove/sort
    }

    @Override
    public String f3(List<Product> t) {
        StringBuilder result = new StringBuilder();

        // processing

        return result.toString();
    }
}
```

**Quan trọng:** Nếu interface đã compiled/given in bytecode, không tự tạo lại file interface. Tạo đúng class implement và đảm bảo signature chính xác.

## 38.3. Subclass skeleton

```java
public class SpecialProduct extends Product {

    private int quantity;

    public SpecialProduct() {
        super();
        quantity = 0;
    }

    public SpecialProduct(String name, int price, int quantity) {
        super(name, price);
        this.quantity = quantity;
    }

    public int getQuantity() {
        return quantity;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }

    @Override
    public String toString() {
        return super.toString() + "," + quantity;
    }
}
```

---

# 39. STRING TASK RECIPES – NHỮNG BÀI CỤ THỂ TỪ ĐỀ

## 39.1. MyLink – thay tất cả dấu chấm bằng dấu hai chấm

**[ĐỀ GỐC – một phiên bản ILink]**

Keyword:
- `replace all "." with ":"`
- `replace every occurrence`
- `return the string`

Method signature:

```java
public String f1(String str)
```

Code:

```java
@Override
public String f1(String str) {
    return str.replace(".", ":");
}
```

Ví dụ:

```text
https://fap.fpt.edu.vn
```

Output:

```text
https://fap:fpt:edu:vn
```

`String.replace(".", ":")` thay literal dấu chấm, không phải regex. Nếu dùng `replaceAll`, dấu `.` trong regex có nghĩa ký tự bất kỳ và phải escape `"\\."`.

## 39.2. MyLink – lấy phần sau dấu chấm đầu tiên và uppercase

**[ĐỀ GỐC – cùng phiên bản ILink trên]**

Keyword:
- `substring after the first "."`
- `first occurrence`
- `in uppercase`

```java
@Override
public String f2(String str) {
    int pos = str.indexOf(".");

    if (pos == -1) {
        return "";
    }

    return str.substring(pos + 1).toUpperCase();
}
```

Ví dụ:

```text
https://fap.fpt.edu.vn
```

Vị trí dấu chấm đầu tiên nằm sau `fap`; phần còn lại là:

```text
fpt.edu.vn
```

Sau uppercase:

```text
FPT.EDU.VN
```

**Phân biệt:** `indexOf(".")` tìm dấu chấm đầu tiên; `lastIndexOf(".")` tìm dấu chấm cuối cùng.

## 39.3. MyLink – thay tất cả dấu slash `/` bằng backslash `\`

**[ĐỀ GỐC – một phiên bản ILink khác]**

Keyword:
- `replace all "/" with "\"`
- `replace every slash`
- `backslash`

```java
@Override
public String f1(String str) {
    return str.replace("/", "\\");
}
```

Trong Java, backslash trong String literal phải escape:
- `"\\"` biểu diễn một ký tự backslash.
- `"/"` là dấu slash thường.

Ví dụ:

```text
https://drive.google.com/drive/folder
```

Output:

```text
https:\\drive.google.com\\drive\\folder
```

Đây là phép thay literal bằng `String.replace`, không dùng regex.

## 39.4. MyLink – lấy phần sau dấu slash cuối cùng và uppercase

**[ĐỀ GỐC – phiên bản ILink khác]**

Keyword:
- `substring after the last "/"`,
- `last occurrence`,
- `uppercase`.

```java
@Override
public String f2(String str) {
    int pos = str.lastIndexOf("/");

    if (pos == -1) {
        return "";
    }

    return str.substring(pos + 1).toUpperCase();
}
```

Ví dụ:

```text
https://drive.google.com/drive/folder
```

Phần sau dấu `/` cuối cùng:

```text
folder
```

Output:

```text
FOLDER
```

## 39.5. MyLink – bảng đối chiếu các biến thể

| Câu tiếng Anh | Method cần nghĩ đến |
|---|---|
| after the first `.` | `indexOf(".")` + `substring(pos+1)` |
| after the last `.` | `lastIndexOf(".")` + `substring(pos+1)` |
| after the first `/` | `indexOf("/")` + `substring(pos+1)` |
| after the last `/` | `lastIndexOf("/")` + `substring(pos+1)` |
| before the first `.` | `substring(0, indexOf("."))` |
| before the last `/` | `substring(0, lastIndexOf("/"))` |
| replace all `.` with `:` | `replace(".", ":")` |
| replace all `/` with `\\` | `replace("/", "\\\\")` trong source Markdown/Java literal biểu diễn backslash |
| uppercase the result | `.toUpperCase()` |
| lowercase the result | `.toLowerCase()` |

Ví dụ lấy trước dấu chấm đầu:

```java
int pos = str.indexOf(".");

if (pos == -1) {
    return str;
}

return str.substring(0, pos);
```

Ví dụ lấy trước dấu slash cuối:

```java
int pos = str.lastIndexOf("/");

if (pos == -1) {
    return str;
}

return str.substring(0, pos);
```

---

# 40. MYSTRING – CÁC BIẾN THỂ f1/f2 THỰC TẾ

## 40.1. f1 – đếm từ có đúng hai chữ số khác nhau và có ít nhất một chữ thường

**[ĐỀ GỐC – một số phiên bản]**

Keywords:
- `number of words`
- `exactly two different digits`
- `at least one lowercase letter`
- `(word = a string without spaces)`

**Khai báo cần có:**
- `String[] words` để tách từ.
- `int result` để đếm số từ đạt.
- `boolean[] seen = new boolean[10]` để nhớ digit nào đã xuất hiện trong từng từ.
- `int differentDigits` đếm digit khác nhau.
- `boolean hasLower` đánh dấu có lowercase.

```java
@Override
public int f1(String str) {
    if (str == null || str.isEmpty()) {
        return 0;
    }

    String[] words = str.split(" ");
    int result = 0;

    for (String word : words) {
        boolean[] seen = new boolean[10];
        int differentDigits = 0;
        boolean hasLower = false;

        for (int i = 0; i < word.length(); i++) {
            char c = word.charAt(i);

            if (Character.isDigit(c)) {
                int digit = c - '0';

                if (!seen[digit]) {
                    seen[digit] = true;
                    differentDigits++;
                }
            }

            if (Character.isLowerCase(c)) {
                hasLower = true;
            }
        }

        if (differentDigits == 2 && hasLower) {
            result++;
        }
    }

    return result;
}
```

Ví dụ:
- `"ab12"`: 2 digit khác nhau, có lowercase → đạt.
- `"A12"`: 2 digit khác nhau nhưng không có lowercase → không đạt.
- `"a112"`: digit khác nhau là 1 và 2 → đạt.
- `"a111"`: chỉ có 1 digit khác nhau → không đạt.

## 40.2. f1 – biến thể có ít nhất một chữ hoa

**[BIẾN THỂ ĐỀ]** Một bản scan ghi `at least one uppercase letter` thay vì lowercase.

Chỉ đổi khai báo và điều kiện:

```java
boolean hasUpper = false;

// inside character loop
if (Character.isUpperCase(c)) {
    hasUpper = true;
}

// final condition
if (differentDigits == 2 && hasUpper) {
    result++;
}
```

**Không dùng nhầm** `hasLower` khi đề hiện tại ghi `uppercase`, hoặc ngược lại.

## 40.3. f1 – biến thể đếm số lần xuất hiện digit, không phải digit phân biệt

**[MỞ RỘNG – dùng khi đề chỉ ghi number of digits]**

```java
int digitCount = 0;

for (int i = 0; i < word.length(); i++) {
    if (Character.isDigit(word.charAt(i))) {
        digitCount++;
    }
}
```

Khác nhau:
- `different digits`: dùng `boolean[10]`.
- `number of digits`: mỗi lần thấy digit đều `count++`.

## 40.4. f2 – số alphabetic characters BẰNG non-alphabetic characters

**[ĐỀ GỐC – một biến thể]**

Keyword:
- `number of alphabetic characters is equal to`
- `number of non-alphabetic characters`
- `keep the original order`
- `separated by a single space`
- `no leading or trailing spaces`
- `empty string if no word satisfies`

```java
@Override
public String f2(String str) {
    if (str == null || str.isEmpty()) {
        return "";
    }

    String[] words = str.split(" ");
    StringBuilder result = new StringBuilder();

    for (String word : words) {
        int letters = 0;
        int nonLetters = 0;

        for (int i = 0; i < word.length(); i++) {
            char c = word.charAt(i);

            if (Character.isLetter(c)) {
                letters++;
            } else {
                nonLetters++;
            }
        }

        if (letters == nonLetters) {
            if (result.length() > 0) {
                result.append(" ");
            }

            result.append(word);
        }
    }

    return result.toString();
}
```

## 40.5. f2 – biến thể số alphabetic characters KHÔNG BẰNG non-alphabetic characters

**[ĐỀ GỐC – biến thể khác]**

Chỉ đổi điều kiện:

```java
if (letters != nonLetters) {
    if (result.length() > 0) {
        result.append(" ");
    }

    result.append(word);
}
```

Còn lại giữ nguyên method của mục 40.4.

## 40.6. Phân biệt alphabetic và non-alphabetic

Một word:

```text
A12b#
```

| Character | Loại |
|---|---|
| `A` | alphabetic |
| `1` | non-alphabetic |
| `2` | non-alphabetic |
| `b` | alphabetic |
| `#` | non-alphabetic |

Kết quả:
- alphabetic = 2.
- non-alphabetic = 3.

Nếu điều kiện `equal`, từ này không được chọn.
Nếu điều kiện `not equal`, từ này được chọn.

**Lưu ý:** space không nằm trong word theo định nghĩa trong đề; sau `split(" ")` không đếm delimiter space vào letters/non-letters.

---

# 41. MYSHOES – ĐỦ CẢ KHAI BÁO VÀ CODE Q3

**[ĐỀ GỐC – các biến thể IShoes]**

Interface được cho sẵn:

```java
import java.util.List;

public interface IShoes {
    public Shoes f1(List<Shoes> t);
    public void f2(List<Shoes> t);
    public void f3(List<Shoes> t);
}
```

Không tạo lại file interface nếu đề nói interface đã compiled.

## 41.1. Khai báo class và imports

```java
import java.util.List;
import java.util.Comparator;

public class MyShoes implements IShoes {
}
```

## 41.2. f1 – tìm Shoes có minimum price

Keyword:
- `minimum price`
- `lowest price`
- `cheapest shoe`

Return type trong interface là `Shoes`, không phải `int`.

```java
@Override
public Shoes f1(List<Shoes> t) {
    if (t == null || t.isEmpty()) {
        return null;
    }

    Shoes min = t.get(0);

    for (Shoes x : t) {
        if (x.getPrice() < min.getPrice()) {
            min = x;
        }
    }

    return min;
}
```

## 41.3. f1 – biến thể maximum price

Keyword:
- `maximum price`
- `highest price`
- `most expensive shoe`

```java
@Override
public Shoes f1(List<Shoes> t) {
    if (t == null || t.isEmpty()) {
        return null;
    }

    Shoes max = t.get(0);

    for (Shoes x : t) {
        if (x.getPrice() > max.getPrice()) {
            max = x;
        }
    }

    return max;
}
```

Đề thường đảm bảo list có phần tử nếu test case yêu cầu min/max. Kiểm tra empty là biện pháp phòng lỗi; giá trị trả về khi empty vẫn phải theo contract/đặc tả nếu đề có nêu.

## 41.4. f2 – sort price ascending

Keyword:
- `sort by price in ascending order`
- `from lowest to highest`
- `increasing order`

```java
@Override
public void f2(List<Shoes> t) {
    t.sort(new Comparator<Shoes>() {
        @Override
        public int compare(Shoes a, Shoes b) {
            return Integer.compare(a.getPrice(), b.getPrice());
        }
    });
}
```

## 41.5. f2 – sort price descending

Keyword:
- `sort by price in descending order`
- `from highest to lowest`
- `decreasing order`

```java
@Override
public void f2(List<Shoes> t) {
    t.sort(new Comparator<Shoes>() {
        @Override
        public int compare(Shoes a, Shoes b) {
            return Integer.compare(b.getPrice(), a.getPrice());
        }
    });
}
```

## 41.6. f3 – remove shoes whose name ENDS WITH "o"

**[ĐỀ GỐC – một phiên bản]**

Keyword: `remove the elements ... that end with "o"`.

```java
@Override
public void f3(List<Shoes> t) {
    for (int i = t.size() - 1; i >= 0; i--) {
        if (t.get(i).getName().endsWith("o")) {
            t.remove(i);
        }
    }
}
```

## 41.7. f3 – remove shoes whose name STARTS WITH "s"

**[ĐỀ GỐC – biến thể]**

Keyword: `remove the elements ... that start with "s"`.

```java
@Override
public void f3(List<Shoes> t) {
    for (int i = t.size() - 1; i >= 0; i--) {
        if (t.get(i).getName().startsWith("s")) {
            t.remove(i);
        }
    }
}
```

Nếu đề ghi chữ hoa/thường cụ thể, `startsWith` và `endsWith` phân biệt case. Không tự chuyển lowercase nếu đề không nói ignore case.

## 41.8. display(List<Shoes> t) – method phụ không có trong interface

**[ĐỀ GỐC – được yêu cầu thêm ngoài f1/f2/f3]**

Keyword:
- `write a display(List t): void function`
- `display the list`
- `print all shoes`

```java
public void display(List<Shoes> t) {
    for (Shoes x : t) {
        System.out.println(x);
    }
}
```

`println(x)` tự gọi `x.toString()` nếu x là object.

Nếu đề yêu cầu format trực tiếp:

```java
public void display(List<Shoes> t) {
    for (Shoes x : t) {
        System.out.println("(" + x.getName()
                + ", " + x.getPrice() + ")");
    }
}
```

Chỉ chọn format đúng với `toString()`/sample output. Ở đề Shoes, sample hiển thị dạng:

```text
(sandal, 20)
(tre em, 50)
(the thao, 15)
```

Do đó `toString()` tương ứng có thể là:

```java
@Override
public String toString() {
    return "(" + name + ", " + price + ")";
}
```

## 41.9. Full MyShoes – phiên bản min/ascending/remove-end

```java
import java.util.List;
import java.util.Comparator;

public class MyShoes implements IShoes {

    @Override
    public Shoes f1(List<Shoes> t) {
        if (t == null || t.isEmpty()) {
            return null;
        }

        Shoes min = t.get(0);

        for (Shoes x : t) {
            if (x.getPrice() < min.getPrice()) {
                min = x;
            }
        }

        return min;
    }

    @Override
    public void f2(List<Shoes> t) {
        t.sort(new Comparator<Shoes>() {
            @Override
            public int compare(Shoes a, Shoes b) {
                return Integer.compare(a.getPrice(), b.getPrice());
            }
        });
    }

    @Override
    public void f3(List<Shoes> t) {
        for (int i = t.size() - 1; i >= 0; i--) {
            if (t.get(i).getName().endsWith("o")) {
                t.remove(i);
            }
        }
    }

    public void display(List<Shoes> t) {
        for (Shoes x : t) {
            System.out.println(x);
        }
    }
}
```

Nếu đề khác yêu cầu max/descending/startsWith, thay đúng phần f1/f2/f3; không đổi interface signature.

---

# 42. MYLADDER – CODE THEO TỪNG f1/f2/f3

**[ĐỀ GỐC – ILadder]**

Interface dạng:

```java
import java.util.List;

public interface ILadder {
    public int f1(List<Ladder> t);
    public void f2(List<Ladder> t);
    public void f3(List<Ladder> t);
}
```

## 42.1. f1 – sum price khi uppercase count > lowercase count

```java
@Override
public int f1(List<Ladder> t) {
    int sum = 0;

    for (Ladder x : t) {
        String s = x.getType();
        int upper = 0;
        int lower = 0;

        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);

            if (Character.isUpperCase(c)) {
                upper++;
            }

            if (Character.isLowerCase(c)) {
                lower++;
            }
        }

        if (upper > lower) {
            sum += x.getPrice();
        }
    }

    return sum;
}
```

Keyword: `sum the price ... whose type contains more uppercase letters than lowercase letters`.

## 42.2. f2 – set price = 0 cho tất cả type dài nhất

```java
@Override
public void f2(List<Ladder> t) {
    if (t == null || t.isEmpty()) {
        return;
    }

    int maxLength = -1;

    for (Ladder x : t) {
        if (x.getType().length() > maxLength) {
            maxLength = x.getType().length();
        }
    }

    for (Ladder x : t) {
        if (x.getType().length() == maxLength) {
            x.setPrice(0);
        }
    }
}
```

Keyword: `set the price of all ladders whose type has the longest length in the list to 0`.

## 42.3. f3 – remove tất cả type chứa số chữ cái nhiều nhất

```java
@Override
public void f3(List<Ladder> t) {
    if (t == null || t.isEmpty()) {
        return;
    }

    int maxLetters = -1;

    for (Ladder x : t) {
        int letters = 0;
        String s = x.getType();

        for (int i = 0; i < s.length(); i++) {
            if (Character.isLetter(s.charAt(i))) {
                letters++;
            }
        }

        if (letters > maxLetters) {
            maxLetters = letters;
        }
    }

    for (int i = t.size() - 1; i >= 0; i--) {
        String s = t.get(i).getType();
        int letters = 0;

        for (int j = 0; j < s.length(); j++) {
            if (Character.isLetter(s.charAt(j))) {
                letters++;
            }
        }

        if (letters == maxLetters) {
            t.remove(i);
        }
    }
}
```

Phân biệt:
- `type.length()` đếm mọi ký tự.
- `Character.isLetter()` chỉ đếm alphabetic character.

---

# 43. CÁC PATTERN CÒN PHẢI CHỌN ĐÚNG THEO ĐỀ

## 43.1. First vs last

| Từ đề | Java |
|---|---|
| first occurrence | `indexOf()` |
| last occurrence | `lastIndexOf()` |
| first character | `charAt(0)` |
| last character | `charAt(length()-1)` |
| substring after first delimiter | `substring(indexOf(delimiter)+1)` |
| substring after last delimiter | `substring(lastIndexOf(delimiter)+1)` |
| remove first character | `substring(1)` |
| remove last character | `substring(0,length()-1)` |

## 43.2. Equal vs not equal

| Đề | Điều kiện |
|---|---|
| equal to | `==` |
| not equal to | `!=` |
| greater than | `>` |
| at least | `>=` |
| less than | `<` |
| at most | `<=` |

## 43.3. Uppercase vs lowercase

```java
Character.isUpperCase(c);
Character.isLowerCase(c);
```

Không chỉ dùng `isLetter()`: một chữ cái có thể là hoa hoặc thường, còn đề có thể hỏi cụ thể một loại.

## 43.4. All vs first

Tìm phần tử đầu tiên:

```java
for (Product x : t) {
    if (condition) {
        return x;
    }
}
return null;
```

Xử lý tất cả phần tử:

```java
for (Product x : t) {
    if (condition) {
        // action
    }
}
```

Nếu đề có chữ `all`, `every`, `each`, không return/break ngay sau phần tử đầu tiên.

## 43.5. Min/max một object vs tất cả object đồng hạng

Một object tốt nhất:

```java
Product best = t.get(0);

for (Product x : t) {
    if (x.getPrice() > best.getPrice()) {
        best = x;
    }
}

return best;
```

Tất cả object cùng giá max:

```java
int maxPrice = Integer.MIN_VALUE;

for (Product x : t) {
    if (x.getPrice() > maxPrice) {
        maxPrice = x.getPrice();
    }
}

for (Product x : t) {
    if (x.getPrice() == maxPrice) {
        // action for every tied object
    }
}
```

---

# 44. CHECKLIST KHI CHÉP MỘT PATTERN VÀO BÀI THI

Trước khi hoàn thành method, kiểm tra 8 câu:

1. Đã viết đúng method header chưa? (access modifier, return type, name, parameter type/order).
2. Đã khai báo đủ local variables chưa? (`int count`, `String result`, `boolean[] seen`, `String[] words`...).
3. Đã khởi tạo giá trị ban đầu phù hợp chưa? (`0`, `""`, `false`, first list item, `MAX_VALUE/MIN_VALUE`).
4. Đã import đúng class chưa? (`List`, `ArrayList`, `Comparator`, `Iterator`...).
5. Đã xử lý đúng phạm vi chưa? (first/last/each/all).
6. Đã dùng đúng operator chưa? (`>`, `>=`, `==`, `!=`).
7. Đã xử lý đúng format chưa? (space/comma/uppercase/two decimals).
8. Đã trả đúng kiểu chưa? (int/double/String/object/void).

---

# 45. PHÂN BIỆT “ĐỀ ĐÃ HỎI” VÀ “JAVA MỞ RỘNG”

**Các pattern có bằng chứng trực tiếp trong bộ PDF:**
- Khai báo class theo UML; default/parameterized constructor; getter/setter; toString.
- Getter/setter có xử lý chuỗi, cộng dồn, tính toán, điều kiện.
- `extends`, `super`, override.
- `implements` interface đã compiled.
- `List<T>`: sum, min/max, sort, remove, update all matching.
- Đếm uppercase/lowercase, alphabetic/non-alphabetic, distinct digits.
- Split words, acronym, biến đổi ký tự đầu/cuối mỗi word.
- URL/link: replace delimiter, lấy substring sau first/last delimiter, uppercase.
- Decimal to binary.
- Method `display(List)` phụ ngoài interface.
- Test case/menu trong project có sẵn; không cần tự tạo lại chương trình test nếu đề đã cấp.

**Các phần mở rộng không thấy trực tiếp trong các trang đề đã đọc, nhưng có thể hữu ích nếu đề khác yêu cầu:**
- Map/Set, regex tổng quát, prime/factorial/Fibonacci/GCD/LCM.
- Mảng 2 chiều, matrix, sorting tự cài.
- Abstract class, polymorphism, exception.
- Generic class.

Không nên dành thời gian học sâu tất cả phần mở rộng trước khi thuộc những pattern có bằng chứng trong đề.



---

# CASE COOKBOOK – MỖI KEYWORD MỘT ĐOẠN CODE HOÀN CHỈNH
## Cách trình bày chính để sử dụng khi thi

> Đây là phần quan trọng nhất khi tra bài. Mỗi case được viết theo cùng cấu trúc:
> 1. **English keywords** – câu chữ có thể xuất hiện trong đề.
> 2. **Ý nghĩa** – đề đang yêu cầu thao tác gì.
> 3. **Khai báo cần có** – field/local variables/imports.
> 4. **Full code** – method hoàn chỉnh để thay tên và điều kiện.
> 5. **Biến thể** – cách đổi khi đề chuyển first/last, upper/lower, equal/not equal, ascending/descending.
>
> Những ví dụ dùng `Product` là mẫu đại diện. Khi thi, thay bằng class thực tế (`Shoes`, `Ladder`, `Chair`, ...) và dùng đúng method signature interface cho sẵn.

# 46. CLASS – FULL CODE CHO TỪNG CASE

## Case 46.1 – Create a class with fields

**English keywords:** `create a class`, `class named`, `attributes`, `fields`, `private variables`.

**Ý nghĩa:** khai báo class và các thuộc tính theo UML.

```java
public class Product {

    private String name;
    private int price;
    private int quantity;

}
```

Nếu đề cho `-name: String`, dấu `-` tương ứng `private`. Nếu đề cho `+name`, tương ứng `public`, nhưng field trong các bài OOP thường là private.

## Case 46.2 – Default constructor

**English keywords:** `default constructor`, `no-argument constructor`, `initialize all fields`.

```java
public Product() {
    name = "";
    price = 0;
    quantity = 0;
}
```

Nếu đề không chỉ định default value, Java tự gán mặc định cho field. Nếu đề nêu rõ `name = ""`, phải gán đúng chuỗi rỗng.

## Case 46.3 – Parameterized constructor

**English keywords:** `parameterized constructor`, `constructor which sets values`, `initialize all attributes`.

```java
public Product(String name, int price, int quantity) {
    this.name = name;
    this.price = price;
    this.quantity = quantity;
}
```

## Case 46.4 – Getter

**English keywords:** `get`, `return the value of`, `accessor`.

```java
public int getPrice() {
    return price;
}
```

Getter trả String:

```java
public String getName() {
    return name;
}
```

Nếu đề yêu cầu biến đổi trước khi trả về, xem các case 46.8–46.12, không dùng getter auto-generated nguyên trạng.

## Case 46.5 – Setter thông thường

**English keywords:** `set`, `update`, `change the value of`.

```java
public void setPrice(int price) {
    this.price = price;
}
```

Setter thông thường trả `void`. Nếu đề nói `price = newPrice`, không cộng dồn.

## Case 46.6 – toString không có spaces sau dấu phẩy

**English keywords:** `string of format`, `return a string in the format`, `return a String in the format`, `without spaces`, `separated by comma`.

`string of format` thường có nghĩa là **trả về một `String` theo đúng format được mô tả trong đề hoặc sample output**. Không hiểu đây là tên một Java method; hãy ghép các field theo đúng thứ tự, dấu phẩy, khoảng trắng, ngoặc hoặc ký tự phân cách mà đề yêu cầu.

```java
@Override
public String toString() {
    return name + "," + price + "," + quantity;
}
```

Nếu sample hiển thị `name, price, quantity`, phải thêm space:

```java
@Override
public String toString() {
    return name + ", " + price + ", " + quantity;
}
```

## Case 46.7 – toString format two decimal places

**English keywords:** `two decimal places`, `formatted to 2 decimal places`, `format the result`.

```java
@Override
public String toString() {
    return name + "," + String.format("%.2f", price);
}
```

Nếu `price` là `double`, output `12.5` sẽ thành `12.50`.

---

# 47. STRING – FULL METHOD CASES

## Case 47.1 – Remove the last character of a String

<badge color="success">ĐÃ XUẤT HIỆN – Coral</badge>

**English keywords:** `remove the last character`, `return the string without the last character`.

Field cần có:

```java
private String name;
```

Full method:

```java
public String getName() {
    return name.substring(0, name.length() - 1);
}
```

Ví dụ: `"vietnam"` → `"vietna"`.

Nếu input có thể null/rỗng và đề cho phép, dùng bản an toàn:

```java
public String getName() {
    if (name == null || name.isEmpty()) {
        return "";
    }

    return name.substring(0, name.length() - 1);
}
```

## Case 47.2 – Remove the first character of a String

**English keywords:** `remove the first character`, `return without the first character`.

```java
public String getName() {
    if (name == null || name.isEmpty()) {
        return "";
    }

    return name.substring(1);
}
```

Ví dụ `"vietnam"` → `"ietnam"`.

## Case 47.3 – Return uppercase String

**English keywords:** `uppercase`, `capital letters`, `convert to uppercase`.

```java
public String getName() {
    return name.toUpperCase();
}
```

## Case 47.4 – Return lowercase String

**English keywords:** `lowercase`, `convert to lowercase`.

```java
public String getName() {
    return name.toLowerCase();
}
```

## Case 47.5 – First character uppercase, rest lowercase

**English keywords:** `first letter capitalized`, `rest lowercase`.

```java
public String getStoreName() {
    if (storeName == null || storeName.isEmpty()) {
        return "";
    }

    return storeName.substring(0, 1).toUpperCase()
         + storeName.substring(1).toLowerCase();
}
```

## Case 47.6 – Append new String to the old field

**English keywords:** `concatenate the new name after the previous name`, `append`, `add to the existing String`.

```java
public void setName(String newName) {
    name = name + newName;
}
```

Đây không phải setter gán thông thường. Không viết `this.name = newName` nếu đề bảo nối vào tên cũ.

## Case 47.7 – Return String + first digit of an integer field

**English keywords:** `concatenate with the first digit`, `append the first digit of age`.

```java
public String getName() {
    String number = String.valueOf(age);

    if (number.isEmpty()) {
        return name;
    }

    return name + number.charAt(0);
}
```

## Case 47.8 – Replace all occurrences of a character/string

**English keywords:** `replace all`, `replace every occurrence of`, `change each X to Y`.

Ví dụ thay toàn bộ dấu chấm thành dấu hai chấm:

```java
public String f1(String str) {
    return str.replace(".", ":");
}
```

Ví dụ thay slash bằng backslash:

```java
public String f1(String str) {
    return str.replace("/", "\\");
}
```

Dùng `replace()` khi muốn thay literal. Nếu dùng `replaceAll()`, pattern là regex và dấu chấm phải escape.

## Case 47.9 – Take substring after the FIRST delimiter

<badge color="success">ĐÃ XUẤT HIỆN – MyLink</badge>

**English keywords:** `substring after the first dot`, `after the first occurrence`, `take the remaining string`.

```java
public String f2(String str) {
    int pos = str.indexOf(".");

    if (pos == -1) {
        return "";
    }

    return str.substring(pos + 1);
}
```

Nếu đề yêu cầu uppercase:

```java
public String f2(String str) {
    int pos = str.indexOf(".");

    if (pos == -1) {
        return "";
    }

    return str.substring(pos + 1).toUpperCase();
}
```

## Case 47.10 – Take substring after the LAST delimiter

**English keywords:** `after the last slash`, `after the last occurrence`, `last delimiter`.

```java
public String f2(String str) {
    int pos = str.lastIndexOf("/");

    if (pos == -1) {
        return "";
    }

    return str.substring(pos + 1).toUpperCase();
}
```

## Case 47.11 – Take substring BEFORE the FIRST delimiter

**English keywords:** `before the first dot`, `part before the first separator`.

```java
public String getPrefix(String str) {
    int pos = str.indexOf(".");

    if (pos == -1) {
        return str;
    }

    return str.substring(0, pos);
}
```

## Case 47.12 – Take substring BEFORE the LAST delimiter

**English keywords:** `before the last slash`, `part before the last separator`.

```java
public String getPath(String str) {
    int pos = str.lastIndexOf("/");

    if (pos == -1) {
        return str;
    }

    return str.substring(0, pos);
}
```

## Case 47.13 – Replace the first alphabetic character

**English keywords:** `first alphabetic character`, `first letter in the string`.

```java
public void replaceFirstLetter(char newChar) {
    for (int i = 0; i < type.length(); i++) {
        char c = type.charAt(i);

        if (Character.isLetter(c)) {
            type = type.substring(0, i)
                 + newChar
                 + type.substring(i + 1);
            break;
        }
    }
}
```

Khác với `replace first character`: case này bỏ qua chữ số/ký hiệu đứng trước.

## Case 47.14 – Replace the first character

**English keywords:** `replace the first character`, `change character at index 0`.

```java
public void replaceFirstCharacter(char newChar) {
    if (type != null && !type.isEmpty()) {
        type = newChar + type.substring(1);
    }
}
```

## Case 47.15 – Replace the last character

**English keywords:** `replace the last character`, `change the final character`.

```java
public void replaceLastCharacter(char newChar) {
    if (type != null && !type.isEmpty()) {
        type = type.substring(0, type.length() - 1) + newChar;
    }
}
```

## Case 47.16 – Replace first character of EVERY word

**English keywords:** `first character of each word`, `replace the first character in every word`.

```java
public String replaceFirstOfEachWord(String str, char newChar) {
    String[] words = str.split(" ");

    for (int i = 0; i < words.length; i++) {
        String word = words[i];

        if (!word.isEmpty()) {
            words[i] = newChar + word.substring(1);
        }
    }

    return String.join(" ", words);
}
```

## Case 47.17 – Replace last character of EVERY word

<badge color="success">ĐÃ XUẤT HIỆN – Lemon/SpecLemon</badge>

**English keywords:** `last character of each word`, `replace the final character in every word`.

```java
public String replaceLastOfEachWord(String str, char newChar) {
    String[] words = str.split(" ");

    for (int i = 0; i < words.length; i++) {
        String word = words[i];

        if (!word.isEmpty()) {
            words[i] = word.substring(0, word.length() - 1)
                       + newChar;
        }
    }

    return String.join(" ", words);
}
```

## Case 47.18 – Replace first/last of each word using first digit of price

**English keywords:** `replace ... with the first character of price`, `first digit of price`.

```java
public void setData() {
    String[] words = type.split(" ");
    char replacement = String.valueOf(price).charAt(0);

    for (int i = 0; i < words.length; i++) {
        String word = words[i];

        if (!word.isEmpty()) {
            words[i] = word.substring(0, word.length() - 1)
                       + replacement;
        }
    }

    type = String.join(" ", words);
}
```

Nếu đề bảo thay ký tự đầu, dùng:

```java
words[i] = replacement + word.substring(1);
```

## Case 47.19 – Build acronym

<badge color="success">ĐÃ XUẤT HIỆN – IStringNumberTool</badge>

**English keywords:** `build an acronym`, `first character of each word`, `uppercase`.

```java
public String buildAcronym(String str) {
    if (str == null || str.isEmpty()) {
        return "";
    }

    String[] words = str.split(" ");
    StringBuilder result = new StringBuilder();

    for (String word : words) {
        if (!word.isEmpty()) {
            char c = word.charAt(0);

            if ((c >= 'A' && c <= 'Z')
                    || (c >= 'a' && c <= 'z')) {
                result.append(Character.toUpperCase(c));
            }
        }
    }

    return result.toString();
}
```

## Case 47.20 – Count words

**English keywords:** `number of words`, `count the words`, `how many words`.

```java
public int countWords(String str) {
    if (str == null || str.trim().isEmpty()) {
        return 0;
    }

    String[] words = str.trim().split("\\s+");
    return words.length;
}
```

## Case 47.21 – Filter words and preserve original order

**English keywords:** `return a new String consisting of`, `keep original order`, `separated by a single space`, `no leading/trailing spaces`.

```java
public String filterWords(String str) {
    if (str == null || str.isEmpty()) {
        return "";
    }

    String[] words = str.split(" ");
    StringBuilder result = new StringBuilder();

    for (String word : words) {
        if (condition) {
            if (result.length() > 0) {
                result.append(" ");
            }

            result.append(word);
        }
    }

    return result.toString();
}
```

Thay `condition` bằng điều kiện đếm/so sánh của đề. Ví dụ `letters != nonLetters`.

## Case 47.22 – Count letters equal / not equal non-letters in EACH word

**English keywords:** `alphabetic characters`, `non-alphabetic characters`, `equal to`, `not equal to`.

Bản `equal`:

```java
public String f2(String str) {
    String[] words = str.split(" ");
    StringBuilder result = new StringBuilder();

    for (String word : words) {
        int letters = 0;
        int nonLetters = 0;

        for (int i = 0; i < word.length(); i++) {
            char c = word.charAt(i);

            if (Character.isLetter(c)) {
                letters++;
            } else {
                nonLetters++;
            }
        }

        if (letters == nonLetters) {
            if (result.length() > 0) {
                result.append(" ");
            }
            result.append(word);
        }
    }

    return result.toString();
}
```

Bản `not equal` chỉ đổi:

```java
if (letters != nonLetters) {
    // append word as above
}
```

## Case 47.23 – Count words with exactly two DISTINCT digits and at least one lowercase

<badge color="success">ĐÃ XUẤT HIỆN – IString</badge>

```java
public int f1(String str) {
    String[] words = str.split(" ");
    int result = 0;

    for (String word : words) {
        boolean[] seen = new boolean[10];
        int differentDigits = 0;
        boolean hasLower = false;

        for (int i = 0; i < word.length(); i++) {
            char c = word.charAt(i);

            if (Character.isDigit(c)) {
                int digit = c - '0';

                if (!seen[digit]) {
                    seen[digit] = true;
                    differentDigits++;
                }
            }

            if (Character.isLowerCase(c)) {
                hasLower = true;
            }
        }

        if (differentDigits == 2 && hasLower) {
            result++;
        }
    }

    return result;
}
```

Nếu đề nói uppercase, đổi `hasLower` thành `hasUpper` và dùng `Character.isUpperCase(c)`.

---

# 48. NUMBER – FULL METHOD CASES

## Case 48.1 – Count number of digits

**English keywords:** `number of digits`, `count digits`.

```java
public int countDigits(int n) {
    if (n == 0) {
        return 1;
    }

    n = Math.abs(n);
    int count = 0;

    while (n > 0) {
        count++;
        n /= 10;
    }

    return count;
}
```

## Case 48.2 – Count even digits

**English keywords:** `number of even digits`, `count even digits`.

```java
public int countEvenDigits(int n) {
    if (n == 0) {
        return 1;
    }

    n = Math.abs(n);
    int count = 0;

    while (n > 0) {
        int digit = n % 10;

        if (digit % 2 == 0) {
            count++;
        }

        n /= 10;
    }

    return count;
}
```

## Case 48.3 – Count odd digits

**English keywords:** `number of odd digits`, `count odd digits`.

```java
public int countOddDigits(int n) {
    n = Math.abs(n);
    int count = 0;

    while (n > 0) {
        int digit = n % 10;

        if (digit % 2 != 0) {
            count++;
        }

        n /= 10;
    }

    return count;
}
```

For `n == 0`, odd digit count is 0.

## Case 48.4 – Sum of digits

**English keywords:** `sum of digits`, `add all digits`.

```java
public int sumDigits(int n) {
    n = Math.abs(n);
    int sum = 0;

    while (n > 0) {
        int digit = n % 10;
        sum += digit;
        n /= 10;
    }

    return sum;
}
```

## Case 48.5 – Reverse an integer

**English keywords:** `reverse the number`, `digits in reverse order`.

```java
public int reverseNumber(int n) {
    int sign = (n < 0) ? -1 : 1;
    int temp = Math.abs(n);
    int reverse = 0;

    while (temp > 0) {
        int digit = temp % 10;
        reverse = reverse * 10 + digit;
        temp /= 10;
    }

    return reverse * sign;
}
```

## Case 48.6 – Decimal to binary

<badge color="success">ĐÃ XUẤT HIỆN – IStringNumberTool</badge>

```java
public String decimalToBinary(int n) {
    if (n == 0) {
        return "0";
    }

    StringBuilder result = new StringBuilder();

    while (n > 0) {
        int remainder = n % 2;
        result.insert(0, remainder);
        n /= 2;
    }

    return result.toString();
}
```

## Case 48.7 – Check even / odd number

**English keywords:** `check whether the number is even`, `odd number`.

```java
public boolean isEven(int n) {
    return n % 2 == 0;
}
```

```java
public boolean isOdd(int n) {
    return n % 2 != 0;
}
```

## Case 48.8 – Prime number

**English keywords:** `prime number`, `divisible only by 1 and itself`.

```java
public boolean isPrime(int n) {
    if (n < 2) {
        return false;
    }

    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) {
            return false;
        }
    }

    return true;
}
```

---

# 49. CONDITION / CALCULATION – FULL METHOD CASES

## Case 49.1 – Calculate total with a threshold

**English keywords:** `if quantity is at least`, `otherwise`, `multiply by`, `extra charge`.

```java
public double getTotalRevenue() {
    double total = pricePerCup * numberOfCups;

    if (numberOfCups >= 100) {
        total = total * 1.2;
    }

    return total;
}
```

Thay threshold/operator/factor đúng theo đề. `at least 100` là `>= 100`; `more than 100` là `> 100`.

## Case 49.2 – Calculate profit from revenue minus cost

**English keywords:** `profit`, `revenue minus cost`, `subtract the total cost`.

```java
public double getProfit(double costPerUnit) {
    double revenue = getTotalRevenue();
    double cost = costPerUnit * quantity;

    return revenue - cost;
}
```

## Case 49.3 – Clamp negative value to zero

**English keywords:** `if the value is negative, set it to zero`, `minimum value is zero`.

```java
public void setRefresh(double refresh) {
    if (refresh < 0) {
        this.refresh = 0;
    } else {
        this.refresh = refresh;
    }
}
```

## Case 49.4 – Choose one of two String values

**English keywords:** `if quantity is greater than ... set status to ... otherwise ...`.

```java
public void updateStatus() {
    if (quantity > 5) {
        status = "discount";
    } else {
        status = "no discount";
    }
}
```

## Case 49.5 – Compute quality index using floating-point division

**English keywords:** `calculate index`, `percentage`, `divide by 100`.

```java
public double getQualityIndex() {
    return diagonal * (brightness / 100.0);
}
```

Dùng `100.0` để tránh integer division.

---

# 50. LIST – FULL METHOD CASES

## Case 50.1 – Display all objects

**English keywords:** `display the list`, `print all items`, `show each object`.

```java
public void display(List<Product> t) {
    for (Product x : t) {
        System.out.println(x);
    }
}
```

Nếu object có `toString()`, `println(x)` tự gọi `toString()`.

## Case 50.2 – Sum field for all objects satisfying condition

**English keywords:** `sum the price of all items whose ...`.

```java
public int f1(List<Product> t) {
    int sum = 0;

    for (Product x : t) {
        if (x.getPrice() > 100) {
            sum += x.getPrice();
        }
    }

    return sum;
}
```

Thay điều kiện `x.getPrice() > 100` bằng đúng điều kiện đề.

## Case 50.3 – Count objects satisfying condition

**English keywords:** `count the number of items whose ...`.

```java
public int countExpensive(List<Product> t) {
    int count = 0;

    for (Product x : t) {
        if (x.getPrice() > 100) {
            count++;
        }
    }

    return count;
}
```

## Case 50.4 – Find minimum object

**English keywords:** `minimum price`, `lowest value`, `cheapest object`.

```java
public Product findMin(List<Product> t) {
    if (t == null || t.isEmpty()) {
        return null;
    }

    Product min = t.get(0);

    for (Product x : t) {
        if (x.getPrice() < min.getPrice()) {
            min = x;
        }
    }

    return min;
}
```

## Case 50.5 – Find maximum object

**English keywords:** `maximum price`, `highest value`, `most expensive`.

```java
public Product findMax(List<Product> t) {
    if (t == null || t.isEmpty()) {
        return null;
    }

    Product max = t.get(0);

    for (Product x : t) {
        if (x.getPrice() > max.getPrice()) {
            max = x;
        }
    }

    return max;
}
```

## Case 50.6 – Sort ascending by price

**English keywords:** `ascending order`, `increasing order`, `lowest to highest`.

```java
public void sortAscending(List<Product> t) {
    t.sort(new Comparator<Product>() {
        @Override
        public int compare(Product a, Product b) {
            return Integer.compare(a.getPrice(), b.getPrice());
        }
    });
}
```

Import:

```java
import java.util.Comparator;
import java.util.List;
```

## Case 50.7 – Sort descending by price

**English keywords:** `descending order`, `decreasing order`, `highest to lowest`.

```java
public void sortDescending(List<Product> t) {
    t.sort(new Comparator<Product>() {
        @Override
        public int compare(Product a, Product b) {
            return Integer.compare(b.getPrice(), a.getPrice());
        }
    });
}
```

## Case 50.8 – Remove all items whose name starts with a character

**English keywords:** `remove all items whose name starts with "s"`.

```java
public void removeStartsWith(List<Product> t) {
    for (int i = t.size() - 1; i >= 0; i--) {
        if (t.get(i).getName().startsWith("s")) {
            t.remove(i);
        }
    }
}
```

## Case 50.9 – Remove all items whose name ends with a character

**English keywords:** `remove all items whose name ends with "o"`.

```java
public void removeEndsWith(List<Product> t) {
    for (int i = t.size() - 1; i >= 0; i--) {
        if (t.get(i).getName().endsWith("o")) {
            t.remove(i);
        }
    }
}
```

## Case 50.10 – Remove all items satisfying a numeric condition

**English keywords:** `remove every item whose price is less than ...`.

```java
public void removeCheap(List<Product> t) {
    for (int i = t.size() - 1; i >= 0; i--) {
        if (t.get(i).getPrice() < 10) {
            t.remove(i);
        }
    }
}
```

## Case 50.11 – Update all items with the longest String

**English keywords:** `all items whose type has the longest length`, `set the price of all ... to zero`.

```java
public void updateLongest(List<Product> t) {
    if (t == null || t.isEmpty()) {
        return;
    }

    int maxLength = -1;

    for (Product x : t) {
        if (x.getName().length() > maxLength) {
            maxLength = x.getName().length();
        }
    }

    for (Product x : t) {
        if (x.getName().length() == maxLength) {
            x.setPrice(0);
        }
    }
}
```

## Case 50.12 – Remove all items with the greatest number of letters

**English keywords:** `remove all items whose type contains the greatest number of letters`.

```java
public void removeMostLetters(List<Product> t) {
    if (t == null || t.isEmpty()) {
        return;
    }

    int maxLetters = -1;

    for (Product x : t) {
        int count = 0;
        String s = x.getName();

        for (int i = 0; i < s.length(); i++) {
            if (Character.isLetter(s.charAt(i))) {
                count++;
            }
        }

        if (count > maxLetters) {
            maxLetters = count;
        }
    }

    for (int i = t.size() - 1; i >= 0; i--) {
        String s = t.get(i).getName();
        int count = 0;

        for (int j = 0; j < s.length(); j++) {
            if (Character.isLetter(s.charAt(j))) {
                count++;
            }
        }

        if (count == maxLetters) {
            t.remove(i);
        }
    }
}
```

## Case 50.13 – Filter into a new List without changing original List

**English keywords:** `return a new list`, `keep only elements satisfying`, `do not modify the original list`.

```java
public List<Product> filter(List<Product> t) {
    List<Product> result = new ArrayList<>();

    for (Product x : t) {
        if (x.getPrice() >= 100) {
            result.add(x);
        }
    }

    return result;
}
```

Imports:

```java
import java.util.List;
import java.util.ArrayList;
```

## Case 50.14 – Find the first matching object

**English keywords:** `first item whose`, `first matching object`.

```java
public Product findFirst(List<Product> t) {
    for (Product x : t) {
        if (x.getPrice() > 100) {
            return x;
        }
    }

    return null;
}
```

## Case 50.15 – Check whether any item matches

**English keywords:** `whether any item`, `at least one item satisfies`.

```java
public boolean containsExpensive(List<Product> t) {
    for (Product x : t) {
        if (x.getPrice() > 100) {
            return true;
        }
    }

    return false;
}
```

## Case 50.16 – Check whether all items match

**English keywords:** `all items must`, `every item satisfies`.

```java
public boolean allPositive(List<Integer> t) {
    for (int x : t) {
        if (x <= 0) {
            return false;
        }
    }

    return true;
}
```

## Case 50.17 – Swap two List elements

**English keywords:** `swap`, `exchange positions`.

```java
public void swap(List<Product> t, int i, int j) {
    Product temp = t.get(i);
    t.set(i, t.get(j));
    t.set(j, temp);
}
```

Or:

```java
Collections.swap(t, i, j);
```

## Case 50.18 – Count a value in List

**English keywords:** `frequency`, `number of occurrences in the list`.

```java
public int countValue(List<Integer> t, int target) {
    int count = 0;

    for (int x : t) {
        if (x == target) {
            count++;
        }
    }

    return count;
}
```

## Case 50.19 – Remove duplicates but keep original order

**English keywords:** `remove duplicates`, `distinct elements`, `preserve insertion order`.

```java
public List<String> removeDuplicates(List<String> t) {
    List<String> result = new ArrayList<>();

    for (String x : t) {
        if (!result.contains(x)) {
            result.add(x);
        }
    }

    return result;
}
```

---

# 51. INHERITANCE – FULL CODE CASES

## Case 51.1 – Create superclass

```java
public class Screen {
    private double diagonal;
    private int brightness;

    public Screen() {
        diagonal = 0;
        brightness = 0;
    }

    public Screen(double diagonal, int brightness) {
        this.diagonal = diagonal;
        this.brightness = brightness;
    }

    public double getDiagonal() {
        return diagonal;
    }

    public int getBrightness() {
        return brightness;
    }

    public void setDiagonal(double diagonal) {
        this.diagonal = diagonal;
    }

    public void setBrightness(int brightness) {
        this.brightness = brightness;
    }

    @Override
    public String toString() {
        return diagonal + "," + brightness;
    }
}
```

## Case 51.2 – Create subclass and call parent constructor

```java
public class OLEDScreen extends Screen {
    private double refresh;

    public OLEDScreen() {
        super();
        refresh = 0;
    }

    public OLEDScreen(double diagonal, int brightness, double refresh) {
        super(diagonal, brightness);
        this.refresh = refresh;
    }
}
```

## Case 51.3 – Access a private superclass field through getter/setter

```java
public class Child extends Parent {

    public void updateParentName(String value) {
        setName(value);
    }

    public String readParentName() {
        return getName();
    }
}
```

## Case 51.4 – Override toString using parent output

```java
@Override
public String toString() {
    return super.toString() + "," + quantity;
}
```

## Case 51.5 – Override toString with a new exact format

```java
@Override
public String toString() {
    return getType() + "," + getPrice() + "," + quantity;
}
```

## Case 51.6 – Conditional setter in subclass updates parent field

```java
public void setType() {
    if (getQuantity() > 15) {
        super.setType("flash sale");
    } else {
        super.setType("no sale");
    }
}
```

Thay threshold/text đúng theo phiên bản đề.

## Case 51.7 – Method calculation using inherited getters

```java
public double calculatePrice() {
    double result = getQualityIndex() * 20;

    if (getRefresh() >= 120) {
        result += 120;
    } else {
        result += 60;
    }

    return result;
}
```

---

# 52. INTERFACE – FULL IMPLEMENTATION CASES

## Case 52.1 – Implement all methods from interface

```java
import java.util.List;

public class MyLadder implements ILadder {

    @Override
    public int f1(List<Ladder> t) {
        int sum = 0;

        // implement condition and calculation

        return sum;
    }

    @Override
    public void f2(List<Ladder> t) {
        // update list/object
    }

    @Override
    public void f3(List<Ladder> t) {
        // remove or modify list
    }
}
```

**Không copy placeholder vào bài thi.** IDE có thể generate method signatures nhưng phần thân vẫn phải viết theo đề.

## Case 52.2 – Add an extra method not declared in interface

**English keywords:** `in addition to the implemented functions`, `also write a display(List): void function`.

```java
public void display(List<Shoes> t) {
    for (Shoes x : t) {
        System.out.println(x);
    }
}
```

Method phụ vẫn nằm trong class implement, không cần thêm vào interface nếu đề không yêu cầu.

---

# 53. ARRAY – FULL CODE CASES

## Case 53.1 – Sum all array elements

```java
public int sum(int[] a) {
    int total = 0;

    for (int i = 0; i < a.length; i++) {
        total += a[i];
    }

    return total;
}
```

## Case 53.2 – Find max array element

```java
public int findMax(int[] a) {
    if (a == null || a.length == 0) {
        return Integer.MIN_VALUE;
    }

    int max = a[0];

    for (int i = 1; i < a.length; i++) {
        if (a[i] > max) {
            max = a[i];
        }
    }

    return max;
}
```

## Case 53.3 – Find min array element

```java
public int findMin(int[] a) {
    if (a == null || a.length == 0) {
        return Integer.MAX_VALUE;
    }

    int min = a[0];

    for (int i = 1; i < a.length; i++) {
        if (a[i] < min) {
            min = a[i];
        }
    }

    return min;
}
```

## Case 53.4 – Linear search in array

```java
public int search(int[] a, int target) {
    for (int i = 0; i < a.length; i++) {
        if (a[i] == target) {
            return i;
        }
    }

    return -1;
}
```

## Case 53.5 – Sort array ascending

```java
public void sortAscending(int[] a) {
    Arrays.sort(a);
}
```

Import:

```java
import java.util.Arrays;
```

---

# 54. SCANNER – FULL INPUT CASES

> Nhiều project đề thi có sẵn menu/test harness nên không cần tự viết Scanner. Dùng những mẫu này khi đề thực sự yêu cầu nhập dữ liệu.

## Case 54.1 – Read int, double, one word

```java
Scanner sc = new Scanner(System.in);

int id = sc.nextInt();
double price = sc.nextDouble();
String name = sc.next();
```

Import:

```java
import java.util.Scanner;
```

## Case 54.2 – Read an entire line after nextInt

```java
Scanner sc = new Scanner(System.in);

int n = sc.nextInt();
sc.nextLine(); // consume remaining newline

String line = sc.nextLine();
```

## Case 54.3 – Read n integers into array

```java
Scanner sc = new Scanner(System.in);

int n = sc.nextInt();
int[] a = new int[n];

for (int i = 0; i < n; i++) {
    a[i] = sc.nextInt();
}
```

## Case 54.4 – Read n Strings into List

```java
Scanner sc = new Scanner(System.in);

int n = sc.nextInt();
List<String> names = new ArrayList<>();

for (int i = 0; i < n; i++) {
    names.add(sc.next());
}
```

---

# 55. FORMAT OUTPUT – FULL CODE CASES

## Case 55.1 – Format double to two decimal places

```java
public String formatPrice(double price) {
    return String.format("%.2f", price);
}
```

## Case 55.2 – Print aligned/simple output

```java
public void display(double price, int quantity) {
    System.out.printf("Price: %.2f, Quantity: %d%n", price, quantity);
}
```

## Case 55.3 – Exact string with comma and no spaces

```java
@Override
public String toString() {
    return color + "," + quantity + "," + type;
}
```

## Case 55.4 – Exact string with comma and spaces

```java
@Override
public String toString() {
    return color + ", " + quantity + ", " + type;
}
```

---

# 56. HOW TO USE THIS COOKBOOK DURING THE EXAM

Ví dụ đọc đề:

> Create a class called Coral. Fields: name:String, price:int. getName():String returns the string by removing the last character of the name.

Cách tra:
1. `Create a class` → case 46.1.
2. `Fields` → khai báo `private String name; private int price;`.
3. `default constructor` → case 46.2.
4. `parameterized constructor` → case 46.3.
5. `getPrice()` → case 46.4.
6. `setPrice()` → case 46.5.
7. `removing the last character` → case 47.1.

**Full method đúng theo Coral:**

```java
public String getName() {
    return name.substring(0, name.length() - 1);
}
```

**Full class Coral:**

```java
public class Coral {

    private String name;
    private int price;

    public Coral() {
        name = "";
        price = 0;
    }

    public Coral(String name, int price) {
        this.name = name;
        this.price = price;
    }

    public String getName() {
        return name.substring(0, name.length() - 1);
    }

    public int getPrice() {
        return price;
    }

    public void setPrice(int price) {
        this.price = price;
    }
}
```

Đây là format cần áp dụng cho toàn bộ case: **đề nói gì → có code method đầy đủ → có thể đặt trực tiếp vào class**.

---

# 57. QUY TẮC CHỐT KHI DÙNG CODE CASE

- Luôn giữ đúng method signature của đề/interface.
- Đặt method bên trong đúng class, không đặt method lồng trong method.
- Field khai báo ở cấp class; local variable khai báo trong method.
- Import cần thiết đặt ở đầu file, trước class.
- Constructor không có return type.
- Getter có return type; setter thông thường là void.
- Các case xử lý List cần dùng đúng generic type, ví dụ `List<Shoes>`, không đổi tùy tiện thành `List<Product>`.
- Nếu đề yêu cầu `all`, duyệt hết; nếu yêu cầu `first`, có thể break/return sớm.
- Nếu đề ghi `Do not format`, không tự format.
- Nếu đề cung cấp interface/project/test harness, không tạo lại hoặc sửa file được bảo vệ trái hướng dẫn.


---

# 58. BỔ SUNG BIẾN THỂ KẾ THỪA VÀ KIỂM TRA CÚ PHÁP

> Phần này bổ sung những đoạn code đầy đủ còn thiếu ở các mục trước. Đây là **mẫu thao tác**, không phải tên method cố định cho mọi đề. Khi làm bài, giữ nguyên method signature, field và getter/setter đúng theo UML/interface/đề hiện tại. Không tự suy ra `first` thành `last`, `even` thành `odd`, hoặc ngược lại.

## 58.1. Phân biệt `length`, `length()` và `size()`

| Kiểu dữ liệu | Cú pháp đúng | Ví dụ |
|---|---|---|
| Array (`int[]`, `char[]`, `String[]`) | `a.length` | `for (int i = 0; i < a.length; i++)` |
| String | `s.length()` | `for (int i = 0; i < s.length(); i++)` |
| StringBuilder | `sb.length()` | `while (sb.length() > 0)` |
| List | `list.size()` | `for (int i = 0; i < list.size(); i++)` |

Nếu nhìn thấy `String[] words = ...split(...)`, vòng lặp đúng là `i < words.length`, không phải `words.length()`.

## 58.2. Replace the FIRST alphabetic character with the FIRST digit of price

**Chỉ dùng khi đề ghi rõ** `first alphabetic character` và `first digit of price`.

```java
public void setData() {
    if (type == null || type.isEmpty()) {
        return;
    }

    String priceText = String.valueOf(getPrice());
    char replacement = priceText.charAt(0);

    for (int i = 0; i < type.length(); i++) {
        char c = type.charAt(i);

        if (Character.isLetter(c)) {
            type = type.substring(0, i)
                 + replacement
                 + type.substring(i + 1);
            break;
        }
    }
}
```

Ví dụ `type = "12standard"`, `price = 450`: chữ cái đầu tiên là `s`, chữ số đầu của price là `4`; kết quả `type = "124tandard"`.

## 58.3. Replace the LAST alphabetic character with the LAST digit of price

**Đây là mẫu đối xứng để tra khi đề thật sự ghi `last alphabetic character` và `last digit of price`. Không được dùng thay cho Case 58.2.**

```java
public void setData() {
    if (type == null || type.isEmpty()) {
        return;
    }

    String priceText = String.valueOf(getPrice());
    char replacement = priceText.charAt(priceText.length() - 1);

    for (int i = type.length() - 1; i >= 0; i--) {
        char c = type.charAt(i);

        if (Character.isLetter(c)) {
            type = type.substring(0, i)
                 + replacement
                 + type.substring(i + 1);
            break;
        }
    }
}
```

Lưu ý: `last alphabetic character` không đồng nghĩa với `last character`. Ví dụ `"12standard!"`: ký tự cuối là `!`, nhưng chữ cái cuối là `d`.

## 58.4. Replace the FIRST character of each word with the FIRST digit of price

**Keyword:** `first character of each word`, `replace ... with the first digit/character of price`.

```java
public void setData() {
    String[] words = getType().split(" ");
    char replacement = String.valueOf(getPrice()).charAt(0);

    for (int i = 0; i < words.length; i++) {
        String word = words[i];

        if (!word.isEmpty()) {
            words[i] = replacement + word.substring(1);
        }
    }

    setType(String.join(" ", words));
}
```

## 58.5. Replace the LAST character of each word with the FIRST digit of price

**Keyword:** `last character of each word`, `replace ... with the first digit/character of price`.

```java
public void setData() {
    String[] words = getType().split(" ");
    char replacement = String.valueOf(getPrice()).charAt(0);

    for (int i = 0; i < words.length; i++) {
        String word = words[i];

        if (!word.isEmpty()) {
            words[i] = word.substring(0, word.length() - 1)
                       + replacement;
        }
    }

    setType(String.join(" ", words));
}
```

Nếu đề ghi `last character of the String` (một ký tự cuối của toàn chuỗi), không split thành words; dùng Case 47.15.

## 58.6. Count total digits / even digits / odd digits – đủ ba bộ đếm

Các method dưới đây đếm chữ số của một số nguyên. `0` có một chữ số; số âm được lấy trị tuyệt đối trước khi đếm.

```java
public int countDigits(int n) {
    n = Math.abs(n);

    if (n == 0) {
        return 1;
    }

    int count = 0;

    while (n > 0) {
        count++;
        n /= 10;
    }

    return count;
}
```

```java
public int countEvenDigits(int n) {
    n = Math.abs(n);

    if (n == 0) {
        return 1;
    }

    int count = 0;

    while (n > 0) {
        int digit = n % 10;

        if (digit % 2 == 0) {
            count++;
        }

        n /= 10;
    }

    return count;
}
```

```java
public int countOddDigits(int n) {
    n = Math.abs(n);
    int count = 0;

    while (n > 0) {
        int digit = n % 10;

        if (digit % 2 != 0) {
            count++;
        }

        n /= 10;
    }

    return count;
}
```

Không đổi điều kiện `digit % 2 == 0` thành `!= 0` trừ khi đề yêu cầu odd digits. Với `n == 0`, count even = 1 và count odd = 0.

## 58.7. SpecLadder – nối type với số lượng even digits hoặc odd digits

> Hai biến thể dưới đây có cùng cấu trúc nhưng khác điều kiện. Chọn đúng một mẫu theo đề. Các ví dụ giả định subclass có field `weight`, superclass có `getType()`, và method cần trả về `String`; nếu đề cho signature khác, giữ signature của đề.

**Biến thể A – nếu có ít nhất 2 even digits thì nối số even digits; nếu không thì nối tổng số digits:**

```java
public String getValue() {
    int n = Math.abs(weight);
    int totalDigits = 0;
    int evenDigits = 0;

    if (n == 0) {
        totalDigits = 1;
        evenDigits = 1;
    } else {
        while (n > 0) {
            int digit = n % 10;
            totalDigits++;

            if (digit % 2 == 0) {
                evenDigits++;
            }

            n /= 10;
        }
    }

    if (evenDigits >= 2) {
        return getType() + evenDigits;
    }

    return getType() + totalDigits;
}
```

**Biến thể B – nếu có ít nhất 2 odd digits thì nối số odd digits; nếu không thì nối tổng số digits:**

```java
public String getValue() {
    int n = Math.abs(weight);
    int totalDigits = 0;
    int oddDigits = 0;

    if (n == 0) {
        totalDigits = 1;
    } else {
        while (n > 0) {
            int digit = n % 10;
            totalDigits++;

            if (digit % 2 != 0) {
                oddDigits++;
            }

            n /= 10;
        }
    }

    if (oddDigits >= 2) {
        return getType() + oddDigits;
    }

    return getType() + totalDigits;
}
```

**Kiểm tra bằng ví dụ:** `weight = 2486` → total = 4, even = 4, odd = 0. `weight = 1357` → total = 4, even = 0, odd = 4. Ví dụ này giúp kiểm tra không bị tráo nhầm even/odd.

## 58.8. SpecLemon – nếu quantity có ít nhất 3 chữ số, nối số chữ số quantity; nếu không, nối số chữ số price

> Mẫu này giả định `quantity` là field của subclass, superclass có `getType()` và `getPrice()`, và method trả về `String`. Giữ đúng tên/signature thật trong đề.

```java
private int countDigits(int n) {
    n = Math.abs(n);

    if (n == 0) {
        return 1;
    }

    int count = 0;

    while (n > 0) {
        count++;
        n /= 10;
    }

    return count;
}

public String getValue() {
    int quantityDigits = countDigits(quantity);

    if (quantityDigits >= 3) {
        return getType() + quantityDigits;
    }

    return getType() + countDigits(getPrice());
}
```

`at least 3 digits` là `>= 3`, không phải `> 3`. Không lấy giá trị quantity làm phần nối; đề mô tả nối **số lượng chữ số** của quantity/price.

## 58.9. Bảng chọn biến thể trước khi dán code

| Cụm từ trong đề | Chọn mẫu |
|---|---|
| first character | Case 47.14 hoặc 58.4 nếu là mỗi word |
| last character | Case 47.15 hoặc 58.5 nếu là mỗi word |
| first alphabetic character | Case 47.13 / 58.2 |
| last alphabetic character | 58.3 |
| first digit of price | `String.valueOf(price).charAt(0)` |
| last digit of price | `String.valueOf(price).charAt(priceText.length() - 1)` |
| even digits | Case 48.2 / biến thể A ở 58.7 |
| odd digits | Case 48.3 / biến thể B ở 58.7 |
| at least 3 digits | `countDigits(value) >= 3` |
| all / every / each | xử lý tất cả phần tử/từ, không dừng ở phần tử đầu tiên |

**Quy tắc an toàn:** nếu đề không nói rõ dùng first hay last, even hay odd, equal hay not equal, hoặc ngưỡng là `>=` hay `>`, không tự chọn theo trí nhớ. Đánh dấu chỗ chưa rõ và quay lại đúng câu chữ của đề trước khi chép code.

---

# 59. ĐỘ DÀI CHUỖI (STRING LENGTH) – TOÀN BỘ THAO TÁC

> Phần này gom mọi thứ liên quan tới **độ dài** của một chuỗi: lấy độ dài, dùng độ dài để duyệt/cắt/thay/thêm/bớt/so sánh/đệm/kiểm tra biên, độ dài của StringBuilder, độ dài mảng sau `split`, độ dài theo byte và theo Unicode. Tất cả dùng cú pháp Java 8.

## 59.0. Quy tắc gốc: `length()` chứ không phải `length`

| Kiểu | Lấy độ dài | Kiểu trả về | Ghi nhớ |
|---|---|---|---|
| `String` | `s.length()` | `int` | **Có ngoặc** – đây là method |
| `StringBuilder` / `StringBuffer` | `sb.length()` | `int` | Có ngoặc |
| Mảng `int[]`, `char[]`, `String[]` | `a.length` | `int` | **Không ngoặc** – đây là field |
| `List`, `Set`, `Map`, `ArrayList` | `list.size()` | `int` | Không phải `length()` |

```java
String s = "Java";
int n = s.length();          // 4

char[] chars = s.toCharArray();
int m = chars.length;        // 4  -> KHÔNG viết chars.length()

String[] words = s.split("a");
int k = words.length;        // 2  -> KHÔNG viết words.length()

List<String> list = new ArrayList<>();
int p = list.size();         // 0
```

Ba lỗi compile hay gặp nhất trong phòng thi:

```java
s.length;          // ✗ String không có field length
words.length();    // ✗ mảng không có method length()
list.length();     // ✗ List dùng size()
```

Độ dài **không bao giờ âm**. `s.length()` trả `0` khi chuỗi rỗng, và luôn tính được với chuỗi `""`. Chỉ khi `s == null` thì gọi `s.length()` sẽ ném `NullPointerException`.

## 59.1. Độ dài cơ bản và các giá trị biên

```java
String a = "";            // a.length() == 0     -> empty
String b = " ";           // b.length() == 1     -> chỉ có space
String c = "  abc  ";     // c.length() == 7
String d = "abc";         // d.length() == 3
String e = null;          // e.length() -> NullPointerException
```

| Câu hỏi trong đề | Code | Kết quả |
|---|---|---|
| empty string? | `s.isEmpty()` | `true` khi `length() == 0` |
| độ dài bằng 0? | `s.length() == 0` | tương đương `isEmpty()` |
| có ít nhất 1 ký tự? | `s.length() > 0` | |
| chỉ toàn space? | `s.trim().isEmpty()` | Java 8; `"   "` → `true` |
| đúng N ký tự? | `s.length() == N` | |
| ít nhất N ký tự? | `s.length() >= N` | "at least N characters" |
| nhiều hơn N ký tự? | `s.length() > N` | "more than N characters" |
| ít hơn N ký tự? | `s.length() < N` | |
| tối đa N ký tự? | `s.length() <= N` | "at most N characters" |
| có ký tự nào không? | `s != null && !s.isEmpty()` | thứ tự kiểm tra quan trọng |

```java
public boolean isNullOrEmpty(String s) {
    return s == null || s.length() == 0;
}
```

Short-circuit của `||` bảo đảm `s.length()` không chạy khi `s == null`. Viết ngược lại `s.length() == 0 || s == null` là lỗi runtime.

`String.isBlank()` là **Java 11**, không dùng trong bài Java 8. Dùng `s.trim().isEmpty()`.

## 59.2. `length()` sau khi biến đổi chuỗi

`String` là immutable: mỗi method trả **chuỗi mới**, nên độ dài phải lấy lại trên kết quả mới.

| Thao tác | Code | Độ dài sau khi làm |
|---|---|---|
| bỏ space đầu/cuối | `s.trim()` | giảm đúng số space bị bỏ |
| bỏ **tất cả** space | `s.replace(" ", "")` | giảm mọi space, kể cả giữa |
| bỏ mọi khoảng trắng (space, tab, xuống dòng) | `s.replaceAll("\\s+", "")` | dùng regex |
| viết hoa | `s.toUpperCase()` | thường bằng, **có ngoại lệ Unicode** |
| viết thường | `s.toLowerCase()` | thường bằng, có ngoại lệ Unicode |
| thay chuỗi dài bằng chuỗi ngắn | `s.replace("abc", "x")` | đổi độ dài |
| nối thêm | `s + "abc"` | tăng |
| cắt bớt | `s.substring(0, k)` | giảm |

```java
String s = "  Hello World  ";
int original = s.length();                    // 15
int afterTrim = s.trim().length();            // 11

String compact = s.trim().replace(" ", "");
int afterRemoveSpaces = compact.length();     // 10
```

Lưu ý thứ tự: `s.trim().length()` khác `s.length()` trừ khi chuỗi không có space ở hai đầu. Đừng viết `s.trim();` rồi kiểm tra `s.length()` – giá trị `trim()` trả về bị bỏ mất, `s` không đổi.

```java
s.trim();               // ✗ kết quả bị bỏ
s = s.trim();           // ✓ gán lại
int n = s.trim().length(); // ✓ dùng trực tiếp
```

Ngoại lệ Unicode cần biết (hiếm khi ra thi nhưng đúng bản chất): `"ß".toUpperCase()` là `"SS"` → độ dài tăng từ 1 lên 2; `"İ".toLowerCase()` cũng đổi độ dài. Nếu đề yêu cầu so sánh "cùng độ dài sau khi đổi hoa/thường", kiểm tra trên kết quả thực tế chứ đừng giả định.

## 59.3. Dùng `length()` để duyệt chuỗi

Duyệt xuôi – mẫu chuẩn:

```java
for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);
    // xử lý c
}
```

Duyệt ngược:

```java
for (int i = s.length() - 1; i >= 0; i--) {
    char c = s.charAt(i);
}
```

Duyệt kiểu khác (Java 8, không cần index):

```java
for (char c : s.toCharArray()) { }

s.chars().forEach(ch -> { });
```

**Sai kinh điển:** dùng `<=` với `length()`.

```java
for (int i = 0; i <= s.length(); i++) {
    s.charAt(i);   // ✗ i == length() -> StringIndexOutOfBoundsException
}
```

Chỉ số hợp lệ của chuỗi là `0 .. s.length() - 1`. Với chuỗi rỗng, không có chỉ số nào hợp lệ; `charAt(0)` ném `StringIndexOutOfBoundsException` (không phải `ArrayIndexOutOfBoundsException`).

Bảng biên của `charAt` / `substring`:

| Gọi | Khi nào hợp lệ |
|---|---|
| `charAt(i)` | `0 <= i < length()` |
| `charAt(length() - 1)` | chỉ khi `length() > 0` |
| `charAt(length())` | **luôn sai** |
| `substring(i)` | `0 <= i <= length()`; `i == length()` → `""` |
| `substring(i, j)` | `0 <= i <= j <= length()`; `i == j` → `""` |
| `substring(0, length() - 1)` | chỉ khi `length() > 0` |

## 59.4. Lấy / bỏ / thay ký tự dựa trên độ dài

| Yêu cầu | Code |
|---|---|
| ký tự đầu | `s.charAt(0)` |
| ký tự cuối | `s.charAt(s.length() - 1)` |
| ký tự cuối dạng String | `s.substring(s.length() - 1)` |
| n ký tự đầu | `s.substring(0, n)` |
| n ký tự cuối | `s.substring(s.length() - n)` |
| bỏ ký tự đầu | `s.substring(1)` |
| bỏ ký tự cuối | `s.substring(0, s.length() - 1)` |
| bỏ n ký tự đầu | `s.substring(n)` |
| bỏ n ký tự cuối | `s.substring(0, s.length() - n)` |
| thay ký tự đầu | `newChar + s.substring(1)` |
| thay ký tự cuối | `s.substring(0, s.length() - 1) + newChar` |
| thay ký tự tại `i` | `s.substring(0, i) + newChar + s.substring(i + 1)` |

Mẫu an toàn cho "bỏ ký tự cuối" – đề rất hay gặp và cũng rất hay lỗi khi chuỗi rỗng:

```java
public String removeLastCharacter(String s) {
    if (s == null || s.length() == 0) {
        return s;
    }
    return s.substring(0, s.length() - 1);
}
```

Chuỗi 1 ký tự: `"a".substring(0, 0)` → `""`. Đó là hành vi đúng, không phải lỗi. Chuỗi rỗng mà không guard: `substring(0, -1)` → `StringIndexOutOfBoundsException`.

Bỏ `n` ký tự cuối cũng phải chặn `n > length()`:

```java
public String dropLast(String s, int n) {
    if (s == null || n <= 0) {
        return s;
    }
    if (n >= s.length()) {
        return "";
    }
    return s.substring(0, s.length() - n);
}
```

## 59.5. Cắt đúng độ dài / đệm cho đủ độ dài

Đề có thể yêu cầu "keep only the first N characters" hoặc "make the string exactly N characters".

```java
// Giữ tối đa n ký tự đầu, không lỗi nếu chuỗi ngắn hơn
public String keepFirst(String s, int n) {
    if (s == null || n <= 0) {
        return "";
    }
    if (s.length() <= n) {
        return s;
    }
    return s.substring(0, n);
}
```

Đệm bên phải bằng space (canh trái) và đệm bên trái (canh phải):

```java
public String padRight(String s, int width) {
    StringBuilder sb = new StringBuilder(s == null ? "" : s);
    while (sb.length() < width) {
        sb.append(' ');
    }
    return sb.toString();
}

public String padLeft(String s, int width) {
    StringBuilder sb = new StringBuilder();
    int need = width - (s == null ? 0 : s.length());
    for (int i = 0; i < need; i++) {
        sb.append(' ');
    }
    sb.append(s == null ? "" : s);
    return sb.toString();
}
```

Cách ngắn hơn bằng `String.format` (không cắt bớt, chỉ đệm khi ngắn hơn):

```java
String left  = String.format("%-10s", "abc");  // "abc       "
String right = String.format("%10s", "abc");   // "       abc"
String zero  = String.format("%05d", 42);      // "00042"
```

`String.format` với `%10s` **không** làm chuỗi dài thành 10 ký tự nếu chuỗi đã dài hơn; nó in đủ, không truncate. Vì vậy nếu đề nói "exactly N characters", phải cắt trước rồi mới đệm.

Cắt theo **từ** (không cắt giữa từ) – dùng khi đề nói "shorten to at most N characters without cutting words":

```java
public String shortenWords(String s, int max) {
    if (s == null || s.length() <= max) {
        return s;
    }
    String cut = s.substring(0, max);
    int lastSpace = cut.lastIndexOf(' ');
    if (lastSpace > 0) {
        cut = cut.substring(0, lastSpace);
    }
    return cut.trim();
}
```

## 59.6. So sánh độ dài

```java
if (a.length() == b.length()) { }
if (a.length() < b.length())  { }
if (a.length() > b.length())  { }
```

Ba điểm dễ sai:

1. `==` trên hai `String` so **reference**, không so nội dung. So nội dung: `a.equals(b)`. Nhưng `a.length() == b.length()` là so `int`, hoàn toàn đúng.
2. "Cùng độ dài" **không** có nghĩa "bằng nội dung". Đề nói "same length" thì dùng `length()`; đề nói "same content" thì dùng `equals`.
3. So sánh không phân biệt hoa/thường vẫn dùng `equalsIgnoreCase`, **không** dựa vào `length()` sau khi đổi hoa (xem ngoại lệ Unicode ở 59.2).

```java
// Đếm số chuỗi có độ dài bằng nhau trong List
public int countSameLength(List<String> list, String target) {
    int count = 0;
    for (String x : list) {
        if (x != null && x.length() == target.length()) {
            count++;
        }
    }
    return count;
}
```

Sắp xếp theo độ dài:

```java
Collections.sort(list, new Comparator<String>() {
    @Override
    public int compare(String a, String b) {
        return Integer.compare(a.length(), b.length());
    }
});
```

Java 8 viết gọn: `list.sort(Comparator.comparingInt(String::length));`

Sắp xếp theo độ dài giảm dần: `Comparator.comparingInt(String::length).reversed()`.

Không dùng `(a, b) -> a.length() - b.length()` nếu chưa chắc giá trị nằm trong phạm vi `int` an toàn; `Integer.compare` luôn đúng và đọc rõ ý.

## 59.7. Tìm chuỗi dài nhất / ngắn nhất

Dạng 1 – chỉ cần độ dài lớn nhất:

```java
public int maxLength(List<String> list) {
    int max = 0;
    for (String s : list) {
        if (s != null && s.length() > max) {
            max = s.length();
        }
    }
    return max;
}
```

Dạng 2 – trả về **tất cả** chuỗi có độ dài lớn nhất (đề hay hỏi "all items with the longest ..."):

```java
public List<String> longestItems(List<String> list) {
    List<String> result = new ArrayList<>();
    int max = -1;

    for (String s : list) {
        if (s == null) {
            continue;
        }
        if (s.length() > max) {
            max = s.length();
        }
    }

    for (String s : list) {
        if (s != null && s.length() == max) {
            result.add(s);
        }
    }

    return result;
}
```

Hai vòng lặp là bắt buộc: vòng 1 tìm `max`, vòng 2 mới lọc. Nếu gộp một vòng và xóa/clear danh sách kết quả trong lúc đang duyệt, code sẽ sai khi gặp chuỗi dài hơn về sau.

Dạng 3 – ngắn nhất: đổi `>` thành `<`, khởi tạo `min = Integer.MAX_VALUE` hoặc gán bằng phần tử đầu tiên khác `null`. Dùng `Integer.MAX_VALUE` an toàn hơn `list.get(0).length()` khi list rỗng hoặc phần tử đầu là `null`.

```java
public int minLength(List<String> list) {
    int min = Integer.MAX_VALUE;
    for (String s : list) {
        if (s != null && s.length() < min) {
            min = s.length();
        }
    }
    return min == Integer.MAX_VALUE ? 0 : min;
}
```

## 59.8. Lọc theo độ dài

| Đề | Code |
|---|---|
| words with more than 3 characters | `s.length() > 3` |
| words with at least 3 characters | `s.length() >= 3` |
| words with exactly 4 letters | `s.length() == 4` |
| words shorter than 5 characters | `s.length() < 5` |
| longest word | mục 59.7 |
| word with length equal to another | `s.length() == other.length()` |

Mẫu lọc giữ nguyên thứ tự gốc, không sửa list đầu vào:

```java
public List<String> filterByLength(List<String> list, int min) {
    List<String> result = new ArrayList<>();
    for (String s : list) {
        if (s != null && s.length() >= min) {
            result.add(s);
        }
    }
    return result;
}
```

Xóa tại chỗ thì duyệt **ngược** để index không bị nhảy:

```java
public void removeShorterThan(List<String> list, int min) {
    for (int i = list.size() - 1; i >= 0; i--) {
        String s = list.get(i);
        if (s == null || s.length() < min) {
            list.remove(i);
        }
    }
}
```

## 59.9. Đếm ký tự bằng `length()` (không đếm bằng mắt)

Đếm số ký tự **không phải** space giữa chuỗi:

```java
public int countNonSpace(String s) {
    if (s == null) {
        return 0;
    }
    return s.replace(" ", "").length();
}
```

Đếm số ký tự thỏa điều kiện (chữ cái, chữ số, hoa, thường) – luôn duyệt tới `s.length()`:

```java
public int countLetters(String s) {
    if (s == null) {
        return 0;
    }
    int count = 0;
    for (int i = 0; i < s.length(); i++) {
        if (Character.isLetter(s.charAt(i))) {
            count++;
        }
    }
    return count;
}
```

Đếm số **từ** dựa trên `split` + `length` của mảng:

```java
public int countWords(String s) {
    if (s == null || s.trim().isEmpty()) {
        return 0;
    }
    return s.trim().split("\\s+").length;
}
```

Cẩn thận: `"".split("\\s+").length` trả `1` (mảng chứa một chuỗi rỗng), nên phải guard trước. Đó là lý do mọi mẫu đếm từ đều kiểm tra `trim().isEmpty()`.

`split` mặc định **bỏ** các phần tử rỗng ở cuối:

```java
"a,b,,".split(",").length        // 2  -> ["a", "b"]
"a,b,,".split(",", -1).length    // 4  -> ["a", "b", "", ""]
",a".split(",").length           // 2  -> ["", "a"]
```

`split` cũng nhận regex, không phải ký tự thường: `split(".")` là regex "mọi ký tự" và trả mảng rỗng; muốn tách theo dấu chấm phải viết `split("\\.")` hoặc `split(Pattern.quote("."))`.

## 59.10. Độ dài của số (số chữ số) – khác `length()` của String

`int`/`double` **không có** `length()`. Ba cách đếm số chữ số:

```java
// Cách 1: chuyển sang String (ngắn, dùng khi không cần tối ưu)
int digits1 = String.valueOf(price).length();

// Cách 2: vòng lặp chia 10 (chuẩn khi đề yêu cầu tự tính)
public int countDigits(int n) {
    if (n == 0) {
        return 1;
    }
    n = Math.abs(n);
    int count = 0;
    while (n > 0) {
        count++;
        n /= 10;
    }
    return count;
}

// Cách 3: logarit (chỉ dùng cho số dương, dễ sai số thực)
int digits3 = n == 0 ? 1 : (int) Math.floor(Math.log10(Math.abs(n))) + 1;
```

| Giá trị | `String.valueOf(v).length()` | Ghi chú |
|---|---|---|
| `0` | `1` | |
| `7` | `1` | |
| `-7` | `2` | dấu `-` cũng là một ký tự |
| `123` | `3` | |
| `45.5` | `4` | dấu `.` cũng tính |
| `1000` | `4` | |

Nếu đề nói "number of digits" và giá trị có thể âm, phải `Math.abs` trước khi đếm bằng cách 2; còn cách 1 sẽ cộng cả dấu trừ. Đây là lỗi biên rất dễ mất điểm.

Lấy chữ số đầu / cuối của một số: chuyển sang String rồi dùng `length()`.

```java
String text = String.valueOf(getPrice());
char firstDigit = text.charAt(0);
char lastDigit  = text.charAt(text.length() - 1);
```

## 59.11. `StringBuilder`: `length()`, `setLength()`, `capacity()`

`StringBuilder` **có** `length()` và **có thể sửa** độ dài tại chỗ — đây là khác biệt cốt lõi so với `String`.

| Thao tác | Code | Ghi chú |
|---|---|---|
| độ dài hiện tại | `sb.length()` | số ký tự đang chứa |
| xóa sạch | `sb.setLength(0)` | nhanh hơn `delete(0, sb.length())` |
| cắt còn n ký tự | `sb.setLength(n)` | `n <= length()` |
| tăng độ dài | `sb.setLength(n)` | phần mới điền `'\u0000'`, **không** phải space |
| xóa ký tự cuối | `sb.deleteCharAt(sb.length() - 1)` | guard `sb.length() > 0` |
| xóa đoạn cuối | `sb.delete(sb.length() - n, sb.length())` | |
| bỏ n ký tự cuối | `sb.setLength(sb.length() - n)` | guard `n <= sb.length()` |
| thêm vào cuối | `sb.append(x)` | length tăng theo `String.valueOf(x).length()` |
| chèn tại vị trí | `sb.insert(i, x)` | `0 <= i <= length()` |
| lấy chuỗi ra | `sb.toString()` hoặc `sb.substring(...)` | |
| dung lượng bộ đệm | `sb.capacity()` | **không** phải độ dài |
| thu gọn bộ đệm | `sb.trimToSize()` | `capacity()` về bằng `length()` |

```java
StringBuilder sb = new StringBuilder("Hello");

sb.append(" World");        // length = 11
sb.deleteCharAt(0);         // length = 10  -> "ello World"
sb.setLength(5);            // length = 5   -> "ello "
sb.setLength(0);            // length = 0   -> ""
```

`capacity()` là sức chứa của mảng nội bộ, mặc định 16 khi khởi tạo rỗng. Sau `new StringBuilder("Hello")`, `length()` là 5 còn `capacity()` là 21 (16 + 5). Đề hỏi "how many characters" thì trả `length()`, không trả `capacity()`.

Mẫu duyệt ngược bằng `StringBuilder` để đảo chuỗi thủ công:

```java
public String reverse(String s) {
    if (s == null) {
        return null;
    }
    StringBuilder sb = new StringBuilder();
    for (int i = s.length() - 1; i >= 0; i--) {
        sb.append(s.charAt(i));
    }
    return sb.toString();
}
```

## 59.12. Độ dài theo byte (UTF-8) – khác độ dài theo ký tự

`s.length()` đếm **UTF-16 code unit**, không đếm byte và không đếm "ký tự" theo nghĩa hiển thị.

```java
import java.nio.charset.StandardCharsets;

int chars = "Hello".length();                              // 5
int bytes = "Hello".getBytes(StandardCharsets.UTF_8).length; // 5

int vnChars = "ế".length();                                 // 1
int vnBytes = "ế".getBytes(StandardCharsets.UTF_8).length;  // 3
```

| Chuỗi | `length()` | byte UTF-8 | Giải thích |
|---|---|---|---|
| `"a"` | 1 | 1 | ASCII |
| `"ế"` | 1 | 3 | ký tự có dấu, 1 code unit |
| `"ế"` (dạng tổ hợp) | 2 | 4 | `e` + dấu mũ + dấu sắc |
| `"😀"` | 2 | 4 | ngoài BMP → cặp surrogate |

Kết luận thực dụng cho bài thi: nếu đề chỉ nói "characters" với dữ liệu ASCII/chữ Latin, `length()` là đủ. Nếu đề nói "bytes", phải dùng `getBytes(...)`. Nếu đề nói "code points" (hiếm), dùng `codePointCount`.

## 59.13. Unicode: `length()` có thể lớn hơn số ký tự bạn thấy

```java
String emoji = "😀";

int units = emoji.length();                                    // 2  (surrogate pair)
int codePoints = emoji.codePointCount(0, emoji.length());       // 1
char high = emoji.charAt(0);                                    // nửa đầu surrogate
```

| API | Đếm cái gì |
|---|---|
| `length()` | UTF-16 code unit |
| `codePointCount(0, s.length())` | code point (ký tự Unicode) |
| `s.getBytes(StandardCharsets.UTF_8).length` | byte |
| `toCharArray().length` | bằng `length()` |

Duyệt theo code point (Java 8):

```java
for (int i = 0; i < s.length(); ) {
    int cp = s.codePointAt(i);
    // xử lý cp
    i += Character.charCount(cp);
}
```

Hệ quả cần nhớ khi làm bài: cắt chuỗi bằng `substring` theo `length()` có thể cắt đôi một cặp surrogate, tạo ra ký tự hỏng. Với đề PRO192 dùng chữ Latin, không gặp; với dữ liệu có emoji thì có. Nếu đề yêu cầu an toàn Unicode, cắt theo `offsetByCodePoints`:

```java
public String firstCodePoints(String s, int n) {
    if (s == null || n <= 0) {
        return "";
    }
    int total = s.codePointCount(0, s.length());
    if (n >= total) {
        return s;
    }
    int end = s.offsetByCodePoints(0, n);
    return s.substring(0, end);
}
```

## 59.14. Mẫu method hoàn chỉnh theo đề thi

### Mẫu A – "return the length of the longest word"

```java
public int longestWordLength(String text) {
    if (text == null || text.trim().isEmpty()) {
        return 0;
    }

    String[] words = text.trim().split("\\s+");
    int max = 0;

    for (int i = 0; i < words.length; i++) {
        if (words[i].length() > max) {
            max = words[i].length();
        }
    }

    return max;
}
```

### Mẫu B – "return all words with more than n characters"

```java
public List<String> wordsLongerThan(String text, int n) {
    List<String> result = new ArrayList<>();

    if (text == null || text.trim().isEmpty()) {
        return result;
    }

    String[] words = text.trim().split("\\s+");

    for (String w : words) {
        if (w.length() > n) {
            result.add(w);
        }
    }

    return result;
}
```

### Mẫu C – "remove the last character of each word"

```java
public String removeLastOfEachWord(String text) {
    if (text == null || text.trim().isEmpty()) {
        return text;
    }

    String[] words = text.trim().split("\\s+");
    StringBuilder sb = new StringBuilder();

    for (String w : words) {
        String cut = w.length() <= 1 ? "" : w.substring(0, w.length() - 1);

        if (sb.length() > 0) {
            sb.append(' ');
        }
        sb.append(cut);
    }

    return sb.toString();
}
```

Từ 1 ký tự → `""`, không lỗi. Từ rỗng không tồn tại vì `split("\\s+")` sau `trim()` đã loại. Điều kiện `sb.length() > 0` là cách chèn space giữa các từ mà **không** có space thừa ở đầu/cuối.

### Mẫu D – "replace the character at index length - 2"

```java
public String replaceSecondLast(String s, char newChar) {
    if (s == null || s.length() < 2) {
        return s;
    }

    int index = s.length() - 2;
    return s.substring(0, index) + newChar + s.substring(index + 1);
}
```

Đề rất hay dùng cụm "second last character", "the character before the last character", "third from the end". Công thức chung cho vị trí cách cuối `k` bước: `index = s.length() - 1 - k`, kèm điều kiện `s.length() > k`.

| Đề | Index |
|---|---|
| last character | `length() - 1` |
| second last | `length() - 2` |
| third last | `length() - 3` |
| middle character (lẻ) | `length() / 2` |
| ký tự giữa (chẵn, lấy bên trái) | `length() / 2 - 1` |

### Mẫu E – đếm ký tự hoa/thường trên field của object trong List

```java
public int countObjectsWithLongName(List<Product> list, int minLength) {
    int count = 0;

    for (Product p : list) {
        String name = p.getName();

        if (name != null && name.length() >= minLength) {
            count++;
        }
    }

    return count;
}
```

Luôn guard field `String` có thể `null` trước khi `.length()`. Getter có thể trả `null` nếu setter cho phép, và đề thi hay cố tình để trống.

## 59.15. Bảng tra nhanh: cụm từ tiếng Anh → code

| Cụm trong đề | Code |
|---|---|
| length of the string | `s.length()` |
| number of characters | `s.length()` |
| empty string | `s.isEmpty()` / `s.length() == 0` |
| not empty | `!s.isEmpty()` |
| at least n characters | `s.length() >= n` |
| more than n characters | `s.length() > n` |
| at most n characters | `s.length() <= n` |
| exactly n characters | `s.length() == n` |
| first n characters | `s.substring(0, n)` |
| last n characters | `s.substring(s.length() - n)` |
| last character | `s.charAt(s.length() - 1)` |
| remove the last character | `s.substring(0, s.length() - 1)` |
| remove the first character | `s.substring(1)` |
| truncate / keep first n | `s.substring(0, Math.min(n, s.length()))` |
| pad to n characters | mục 59.5 |
| longest / shortest word | mục 59.7 |
| count words | `s.trim().split("\\s+").length` |
| number of digits | mục 59.10 |
| length of StringBuilder | `sb.length()` |
| number of elements | `list.size()` / `arr.length` |

## 59.16. Checklist lỗi độ dài trước khi nộp bài

| Kiểm tra | Đúng | Sai |
|---|---|---|
| Gọi trên String | `s.length()` | `s.length` |
| Gọi trên mảng | `arr.length` | `arr.length()` |
| Gọi trên List | `list.size()` | `list.length()` |
| Điều kiện vòng lặp | `i < s.length()` | `i <= s.length()` |
| Index ký tự cuối | `s.length() - 1` | `s.length()` |
| Guard trước `charAt`/`substring` | `length() > 0` | không guard |
| Field String có thể null | `name != null && name.length() > 0` | `name.length() > 0` |
| Đếm số có thể âm | `Math.abs(n)` | bỏ qua dấu |
| `split` có thể rỗng | guard `trim().isEmpty()` | dùng `.length` trực tiếp |
| Đệm đúng N ký tự | cắt rồi đệm | chỉ `String.format("%Ns")` |
| Đếm "characters" với Unicode | `codePointCount` | `length()` |
| Đếm "bytes" | `getBytes(...).length` | `length()` |

Ba câu tự hỏi trước khi kết thúc mỗi method có `length()`:

1. Chuỗi này **có thể rỗng** không? Nếu có, `charAt` và `substring` cần guard.
2. Chuỗi này **có thể null** không? Nếu có, kiểm tra `null` trước.
3. Tôi đang lấy độ dài của **String, mảng hay List**? Mỗi kiểu có cú pháp riêng và không thay thế cho nhau được.
