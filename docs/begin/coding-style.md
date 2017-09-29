# Các quy ước để làm việc với Ducky

- **Cấp độ:** Cơ bản
- **Bắt buộc:** Rất cao

----------


*Dưới đây tôi sẽ giới thiệu tới các bạn vấn đề đầu tiên mà các bạn cần nắm vững khi muốn làm việc cùng Ducky FW...*

## Đặt tên tệp ##

Khi tạo 1 tệp mới, các bạn phải chú ý là có sự phân biệt giữa tệp chứa `Class` và tệp thông thường.

Nếu tệp chứa `class`, phải đặt tên theo quy tắc "Lạc đà". Nếu tệp là tệp thông thường, phải đặt tên bằng chữ in thường.

Tất cả các **tệp thông thường** nếu có tên từ 2 từ trở lên **phải** phân cách bằng dấu `gạch ngang` (`-`).

**SAI:**

```php
my-class.php  
my_class.php  
My_class.php

mynormalfile.php  
MyNormalFile.php
```

**ĐÚNG:**

```php
MyClass.php  
```

```php
my-normal-file.php
```

**Chú ý:** 


1. Tên tệp chứa `class` phải là tên `class`, ví dụ tệp có tên `MyClass.class.php` thì chứa `class` tên `MyClass`.
2. Các tệp dùng trong các thư mục sau sẽ có phần mở rộng như sau:

  - **core**: `*.class.php`
  - **controllers**: `*.controller.php`
  - **models**: `*.model.php`
  - **libraries**: `*.lib.php`
  - **config**: `*.conf.php`
  - **languages**: `*.language.php`

Ví dụ:

	MyExampleClass.class.php
	MyExampleController.controller.php
	MyExampleModel.model.php
	MyExampleLibrary.lib.php

## Đặt tên `class` và `method` (Lớp và hàm)

**Tên lớp:**  

Đặt tên theo nguyên tắc "lạc đà", **không** dùng gạch ngang (`-`) và nối thêm thư mục tương ứng.

- **core**: `MyExampleClass.class.php`  
- **controllers**: `MyExampleController.controller.php`  
- **models**: `MyExampleModel.model.php`    
- **libraries**: `MyExampleLib.lib.php`  

**Tên hàm:**

Đặt tên theo nguyên tắc chữ cái đầu tiên viết thường, các chữ cái khác theo nguyên tắc "lạc đà", **không** dùng dấu gạch ngang (`-`). Riêng các hàm nội bộ (`private`, `protected`) phải dùng dấu gạch dưới (`_`) làm tiền tố.

Ví dụ:

    myFunc();  //Hàm thông thường
    _myPrivateFunc(); //Hàm nội bộ



## Đặt tên biến

Tên biến đặt tương tự như tên hàm.

Riêng tên khóa (`key`) của mảng, phải viết in thường toàn bộ và dùng dấu gạch dưới (`_`) để phân cách từ.

Ví dụ:

    $myVar; //Biến thông thường
    $_myPrivateVar; //Biến nội bộ
    $myArray[my_key]; //Tên biến mảng và khóa



## Ghi chú
Ghi chú được sử dụng trước mỗi `class`, `function`, khi cần và ở đầu mỗi tệp với mục đích làm cho code dễ hiểu và dễ phát triển hoặc sửa lỗi.

Có 2 loại ghi chú: *dạng khối* và *dạng dòng đơn*. Khi dùng để ghi chú cho `class`, `function` và ở đầu tệp thì phải dùng dạng khối. Còn lại dùng dạng dòng đơn.

Ghi chú được viết bằng Tiếng Việt có dấu.

Dưới đây là các hướng dẫn cụ thể cho từng hoàn cảnh:

**Ghi chú đầu tệp:**

Mục đích: Cung cấp cho coder biết các thông tin sau:

- Tên tệp
- Người sửa cuối cùng
- Ngày sửa cuối cùng
- Đường dẫn (`link`) dẫn đến changelog
- Các ghi chú khác (nếu có)

Ví dụ:

	/**
	 * login.controller.php
	 * 
	 * @last_editor: Nguyễn Văn A
	 * @last_edit_date: 13/09/2017 - 20h30'
	 * @changelog: http://link_to_changelog.html
	 * @notes: 
	 *	 - Đã sửa và kiểm thử thành công chức năng đăng nhập.
	 *	 - Còn đang tìm thuật toán cho việc xử lý mật khẩu.
	 */

**Ghi chú trước `class` và  `function`:**

Mục đích: Cung cấp cho coder biết các thông tin sau:

- Tên lớp (hoặc hàm)
- Tác giả
- Người sửa cuối cùng
- Ngày sửa cuối cùng
- Các tham số và chi tiết về các tham số đó
- Giá trị trả về
- Đường dẫn tài liệu tra cứu
- Các ghi chú khác (nếu có)

Ví dụ:

	/**
	 * LoginClass
	 *
	 *  @author: Nguyễn Văn A
	 *  @last_editor: Trần Văn B
	 *  @last_edit_date: 13/09/2017 20h30'
	 *  @params:
	 *		(string)		$str			Chuỗi đầu vào
	 *		[(int)]			$number = 0		Số đầu vào
	 *	@return: void
	 *	@docs: http://link_to_docs.html
	 *	@notes: 
	 *		- Chưa làm xong phần disable nút đăng nhập khi đang xử lý đăng nhập
	 *		- Đã nghỉ ra cách để xử lý tốt hơn mật khẩu
	 */
	
	class LoginClass extends Controller {
		// Code ở đây
	}


**Ghi chú dòng đơn (`//`):**

Mục đích: Để code dễ đọc hơn.

Khi ghi chú dòng đơn, phải viết hoa đầu dòng, dòng ghi chú phải cách khối code phía trên ra 1 dòng.

Ví dụ 1:
​	
	if()
	{
		//Code phía trên
	}
	
	// Biến toàn cục $session
	$session = $_SESSION['key'];

Ví dụ 2:

	return $authorName; //Trả về chuỗi chứa tên tác giả

***Chú ý:** Không lạm dụng ghi chú, khi viết ghi chú, nếu mục nào không có có thể bỏ.*



## Hằng số

Có 2 loại hằng số, hằng số *tĩnh* và hằng số *động*. 

Hằng số tĩnh là dạng hằng số được gán giá trị trực tiếp và không thay đổi trong suốt quá trình thực thi code.

Hằng số động được gán và thay đổi tùy theo trường hợp cụ thể, thường có dạng mảng.

Chú ý:

- Luôn luôn sử dụng hằng số mỗi khi có cơ hội.
- Tên hằng số phải luôn dùng chữ in hoa toàn bộ, dùng dấu gạch dưới (`_`) để phân cách từ.
- Không sử dụng tên hằng số không rõ nghĩa.
- Không sử dụng tên hằng số 1 chữ cái, dạng N, M, A, X...

Ví dụ:

**SAI:**

    myConstant  //không có gạch dưới và không dùng in hoa toàn bộ
    N   //Không dùng hằng số 1 chữ cái
    S_C_VER //Không rõ nghĩa
    $str = str_replace('{foo}', 'bar', $str);   //Không thay dấu ngoặc nhọn bằng hằng số

**ĐÚNG:**

	MY_CONSTANT
	NEWLINE
	SUPER_CLASS_VERSION
	$str = str_replace(LD.'foo'.RD, 'bar', $str);


## Khi sử dụng `TRUE`, `FALSE`, `NULL`

`TRUE`, `FALSE`, `NULL` là các từ khóa của PHP nên sử dụng dạng in hoa toàn bộ.

**SAI:**

    if ($foo == true)
    $bar = false;
    function foo($bar = null)

**ĐÚNG:**

    if ($foo == TRUE)
    $bar = FALSE;
    function foo($bar = NULL)


##Toán tử logic

Toán tử logic gồm `||` hoặc `OR`, `&&` hoặc `AND`, `!` hoặc `NOT`.

Tuy nhiên, để thống nhất và được hỗ trợ tốt nhất cho phần hightlighter. Chúng ta quy ước như sau:

- Toán tử **hoặc**: Dùng `OR` không dùng `||`
- Toán tử **và**: Dùng `&&` không dùng `AND`
- Toán tử **phủ định**: Dùng `!` không dùng `NOT`
- **Trước và sau** dấu `!` phải luôn có dấu cách

Ví dụ:

**SAI:**

    if ($foo || $bar)
    if ($foo AND $bar)  
    if (!$foo)
    if (! is_array($foo))

**ĐÚNG:**

    if ($foo OR $bar)
    if ($foo && $bar) 
    if ( ! $foo)
    if ( ! is_array($foo))



## So sánh và ép kiểu

Một số hàm của PHP sẽ trả về `false` nếu thất bại, nhưng đa số sẽ trả về "" (rỗng) hoặc `0`. Điều này sẽ dễ khiến cho kết quả so sánh với `FALSE` bị sai, 
ví dụ:
​	
	//Hàm strpos sẽ trả về 0 nếu như chuỗi 'foo' nằm ở đầu của $str.
	// Cho nên nếu so sánh như hàng dưới đây sẽ ra kết quả TRUE
	
	if (strpos($str, 'foo') == FALSE) //Return TRUE (vì FALSE = 0)

Cho nên khi so sánh với `FALSE` hoặc `TRUE` phải sử dụng dấu `===` thay vì `==`.

Ví dụ:

**SAI:**

	if (strpos($str, 'foo') == FALSE)

**ĐÚNG:**

	if (strpos($str, 'foo') === FALSE)


**SAI:**

	function build_string($str = "")
	{
	    if ($str == "") //LoL! Nếu $str được truyền vào là 0 hoặc FALSE thì sao
	    {
	
	    }
	}

**ĐÚNG:**

	function build_string($str = "")
	{
	    if ($str === "")
	    {
	
	    }
	}

Về ép kiểu (typecasting), khi ép, `NULL` và `FALSE` sẽ thành chuỗi rỗng, số 0 và các số khác sẽ trở thành số tương ứng, riêng `TRUE` sẽ trở thành chuỗi '1'.

Ví dụ:
​	
	$str = (string)$str;



## Không ghi chú code "để dành"

Trong quá trình phát triển mã nguồn, chúng ta hay sử dụng hàm `echo` hoặc `print_r`, `var_dump` để kiểm thử. Nên nhớ phải xóa hết các hàm này trước khi hoàn thành một tệp.

Và đặc biệt, một số bạn có thói quen `comment` code cũ lại "để dành". Nói thật, việc đó cũng như bạn chạy chiếc xe mới mua trong khi kéo theo chiếc xe cũ "để dành" xe mới hư thì lấy xe cũ ra chạy???

Tóm lại, code đẹp là code sạch, không rác, không dư thừa dù chỉ là 1 khoảng trắng.



## Không để dư khoảng trắng

PHP framework chạy theo mô hình MVC thường có Template Engine. Cho nên, nếu một tệp nào đó của bạn để dư khoảng trắng hoặc dòng trắng ở trước thẻ mở `<?php` và đặc biệt là sau thẻ đóng `?>` sẽ ảnh hưởng đến hoạt động của Template Engine.

Tốt nhất là nên xóa bỏ hết tất cả các chỗ dư thừa không cần thiết.


## Mỗi tệp chỉ chứa duy nhất 1 `class`

Tiêu đề đã nói rõ ràng rồi, mỗi tệp chỉ chứa 1 lớp. Và mỗi hàm chỉ thực thi 1 công việc duy nhất. Đây chính là tiêu chuẩn cao cấp nhất của "clean code".


## Thụt lề

Đã là một coder thì phải dành ra 1 ngón tay ở bàn tay trái để ấn phím tab. Đó là văn hóa ứng xử tối thiểu mà một coder phải có. Đừng để "những người đến sau" phải thất kinh bát đảo với đóng hỗn độn mà bạn để lại.

À, và một điều nữa, không viết dấu ngoặc nhọn ngay sau mệnh đề `if` hoặc vòng lặp `for`...

Ví dụ:

**KHÔNG SAI, NHƯNG VÔ VĂN HÓA:**

    function foo($bar) {
    // ...
    }
    
    foreach ($arr as $key => $val) {
    // ...
    }
    
    if ($foo == $bar) {
    // ...
    } else {
    // ...
    }
    
    for ($i = 0; $i < 10; $i++)
    {
    for ($j = 0; $j < 10; $j++)
    {
    // ...
    }
    }
    
    try {
    // ...
    }
    catch() {
    // ...
    }

**CÓ VĂN HÓA:**

    function foo($bar)
    {
    	// ...
    }
    
    foreach ($arr as $key => $val)
    {
    	// ...
    }
    
    if ($foo == $bar)
    {
    	// ...
    }
    else
    {
    	// ...
    }
    
    for ($i = 0; $i < 10; $i++)
    {
    for ($j = 0; $j < 10; $j++)
    {
    	// ...
    }
    }
    
    try
    {
    	// ...
    }
    catch()
    {
    	// ...
    }



## Truyền tham số

Khi truyền tham số vào một hàm, tuyệt đối không để thừa khoảng trắng trước và sau tham số, ví dụ:

**SAI:** 

	print_r( $arr );

	$name = $arr[ 'name' ];

**ĐÚNG:**

	print_r($arr);

	$name = $arr['name'];


## Code chuẩn là code không hiện lỗi và cảnh báo

Đừng có tắt báo lỗi rồi cứ thế mà chạy nhé. Đặc biệt là những cảnh báo liên quan đến không tồn tại biến.

Hãy nhớ, luôn viết code sao cho có logic, luôn bật báo lỗi - cảnh báo. Khi nào không báo lỗi nữa thì mới gọi là production.

	error_reporting(-1); //Luôn dùng hàm này để bật báo lỗi


## Sử dụng thẻ mở dài

Khi bắt đầu viết code trong PHP, bạn phải viết một thẻ mở, xem ví dụ và làm cho đúng nhé.

Ví dụ:

**SAI:**

	<?
		//Code
	?>

**ĐÚNG:**

	<?php
		//Code
	?>


## Mỗi dòng chỉ được gõ 1 câu lệnh

Không bao giờ viết liên tục nhiều câu lệnh trên cùng 1 dòng.

**SAI:**

	foo = 'this'; $bar = 'that'; $bat = str_replace($foo, $bar, $bag);


**ĐÚNG:**

    $foo = 'this';
    $bar = 'that';
    $bat = str_replace($foo, $bar, $bag); 


## Chuỗi

Luôn dùng nháy đơn (`'`) cho chuỗi thuần và nháy kép (`"`) cho chuỗi chứa biến.

**SAI:**

	"My String"     	//Không có biến nên phải dùng nháy đơn                                
	"My string $foo" 	// Cần dùng dấu ngoặc nhọn bao biến lại
	'SELECT foo FROM bar WHERE baz = \'bag\''       //Chứa biến nên phải dùng nháy kép

**ĐÚNG:**

	'My String'
	"My string {$foo}"
	"SELECT foo FROM bar WHERE baz = 'bag'"


## Câu lệnh SQL

Các từ khóa như `SELECT`, `UPDATE`, `DELETE`, `WHERE`... phải được viết hoa toàn bộ và xuống hàng ở mỗi vế.

Ví dụ:

**SAI:**

	$query = $this->db->query("select foo, bar, baz, foofoo, foobar as raboof, foobaz from exp_pre_email_addresses	where foo != 'oof' and baz != 'zab' order by foobaz limit 5, 100");


**ĐÚNG:**

	$query = $this->db->query("SELECT foo, bar, baz, foofoo, foobar 
								AS raboof, foobaz 
								FROM exp_pre_email_addresses 
								WHERE foo != 'oof' 
								AND baz != 'zab' 
								ORDER BY foobaz 
								LIMIT 5, 100");

----------

Ngày viết: 27/09/2017