# Tổng quan tag dữ liệu:

Tag dữ liệu dùng để truy xuất mọi dữ liệu từ hệ thống cọp vàng. Dữ liệu bao gồm về sản phẩm, bài viết, giỏ hàng, đơn hàng... giúp cho các developer theme có thể dễ dàng tương tác với các dữ liệu một cách đơn giản và gần giống như đang sử dụng HTML.

# Mô phỏng sơ lược

* Các tag dữ liệu đều có chung các thuộc tính và các biến:

Tham trị trên tag | Gía trị mặc định | Mô tả
------------ | ------------- | -------------
assign-model | model | Biến dùng để truy xuất các dữ liệu (Dữ liệu bên trong biến này sẽ khác nhau tùy theo thẻ)
assign-is-first | isFirst | Dùng để xác định có phải là dữ liệu đầu tiên hay không
assign-is-last | isLast | Dùng để xác định có phải là dữ liệu cuối cùng hay không
assign-index | index | Số thứ tự của dữ liệu hiện tại (bắt đầu từ 0)
assgin-key | key | Khóa của dữ liệu hiện tại

* Thẻ đơn

```html
<products>

  <div><$model.name></div>

  <if $isLast>
    <div class='clear-fix'></div>
  </if>
</products>

```

* Thẻ trong thẻ:

```html
<products assign-model='product'>
  <div><$product.name></div> 
  
  <tags assign-model='tag'>
    <div><a href='<$tag.url>'><$tag.name></div>
  </tags>
</products>

```
 

# Thông tin các thẻ

* Product:

  * Các thành phần trong `=`:
  
  Tên thành phần | Mô tả | Gợi ý trang sử dụng
  ------------ | ------------- | -------------
  name | Tên của sản phẩm | \*
  price | Gía gốc của sản phẩm | \*
  discount | Số tiền giảm giá | \*
  new_price | Gía mới của sản phẩm | \*
  desc | Bài giới thiệu sản phẩm | Trang chi tiết sản phẩm
  short_desc | Mô tả ngắn | Các trang show sản phẩm
  url | Đường dẫn đến trang chi tiết | *
