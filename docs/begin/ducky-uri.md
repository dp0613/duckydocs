# Tìm hiểu về URI trong Ducky Framework

- **Cấp độ:** Cơ bản
- **Bắt buộc:** Rất cao

----------


*Việc quan trọng nhất khi bắt đầu làm quen với DF là hiểu về cấu trúc URI, bài viết này tôi sẽ cố gắng giúp các bạn nắm vững được điều này...*

## Tổng quan

DF sử dụng kết hợp MVC Pattern và Singleton Pattern. Cho nên mọi request được chuyển về tệp `index.php` để xử lý. Chính vì vậy, URI phải tuân theo một cấu trúc nhất định, và cấu trúc mà DF chọn như sau:

> http://domain.com/***shape/language/controller/controller_function/param1/param2***

Trong đó:

- `shape`: Là tham số sử dụng trong Template Engine
- `language`: Là tham số sử dụng trong chức năng đa ngôn ngữ
- `controller`: Là tên controller
- `controller_function`: Là tên method nằm trong controller ở trên
- `param1`, `param2`: Là các param truyền kèm theo (nếu có)

Ví dụ:

> http://domain.com/***home/vi/home/index*** (đây là URI mặc định, dẫn đến trang chủ)
> http://domain.com/***admin/en/dashboard/index*** (vào trang admin bằng tiếng anh)

## Tham số mặc định
Khi một tham số nào được bỏ trống, DF sẽ tự động sử dụng tham số mặc định được thiết lập trong tệp `/system/config/default.conf.php`:

- `shape`: ***home***
- `language`: ***vi***
- `controller`: ***home***
- `controller_function`: ***index***

## Các ví dụ minh họa

Dưới đây là các ví dụ minh họa giúp coder tạo ra một URI mới.

**Trường hợp 1: URI dẫn đến trang chủ:**

Khi muốn dẫn đến trang chủ, không cần sử dụng URI. Khi URI được bỏ trống, các tham số mặc định sẽ được sử dụng.

> http://domain.com

**Trường hợp 2: URI dẫn đến trang authorization, phần form đăng nhập:**

Có 2 cách, gán ngôn ngữ luôn hoặc bỏ trống. 

> http://domain.com/autho/vi/author-controller/index  
> http://domain.com/autho/author-controller/index


**Trường hợp 3: URI dẫn đến trang authorization, phần xử lý đăng nhập:**

Có 2 cách, gán ngôn ngữ luôn hoặc bỏ trống. Ở cuối URI là tên đăng nhập và mật khẩu.

> http://domain.com/autho/vi/author-controller/submit/username/password  
> http://domain.com/autho/author-controller/submit/username/password


**Trường hợp 4: URI dẫn đến trang authorization, phần form đăng ký:**

Có 2 cách, gán ngôn ngữ luôn hoặc bỏ trống.

> http://domain.com/autho/vi/author-controller/signup  
> http://domain.com/autho/author-controller/signup


**Trường hợp 5: URI dẫn đến trang authorization, phần đăng xuất:**

Có 2 cách, gán ngôn ngữ luôn hoặc bỏ trống.

> http://domain.com/autho/vi/author-controller/logout  
> http://domain.com/autho/author-controller/logout


----------

Ngày viết: 28/09/2017