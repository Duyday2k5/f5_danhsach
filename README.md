# f5_danhsach

## Các bài nâng cao đã thực hiện

### Bài NC1: Thanh tìm kiếm lọc danh sách theo tên khi đang gõ
- **Mô tả yêu cầu**: Thêm một thanh tìm kiếm cho phép lọc danh sách sản phẩm hiển thị trên màn hình ngay khi người dùng đang nhập từ khóa.
- **Cách thực hiện**:
  - Khai báo thêm biến trạng thái `_tuKhoa` (kiểu chuỗi) để lưu trữ từ khóa tìm kiếm hiện tại trong `_ProductListTabState`.
  - Thêm một widget `TextField` nằm phía trên danh sách sản phẩm, với thuộc tính `onChanged` để lắng nghe sự thay đổi văn bản.
  - Mỗi khi văn bản thay đổi, gọi hàm `setState()` để cập nhật biến `_tuKhoa`.
  - Tính toán danh sách lọc `dsLoc` từ danh sách gốc `_ds` bằng cách dùng phương thức `where()`: lọc ra các sản phẩm có tên chứa `_tuKhoa` (không phân biệt chữ hoa, chữ thường).
  - Truyền danh sách đã lọc `dsLoc` vào `ListView.builder` để chỉ hiển thị các sản phẩm phù hợp. Ngoài ra cũng xử lý lỗi khi danh sách lọc rỗng sẽ hiển thị thông báo "Không tìm thấy sản phẩm".