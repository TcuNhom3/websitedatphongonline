# Đề tài môn học Phát triển phần mềm mã nguồn mở

## Website quản lý đặt phòng online khách sạn Fairybay

​	 				<p align="center">
  <img src="http://imageshack.com/a/img924/2930/fQcWH2.png">
</p>







​	Ngày nay việc đặt phòng khách sạn thật sự đơn giản . Trước đây, khách du lịch thường mua dịch vụ trọn gói của đại lý hoặc tự tìm thông tin liên hệ  khách sạn và đặt phòng. Nhưng giờ đây, chỉ đơn giản bằng cách truy cập vào trang web, với các thao tác đơn giản  du khách quên đi mối lo lắng về nơi ăn chốn nghỉ cho Chuyến du lịch thú vị của mình

​	Công nghệ thông tin phát triển, the web trực tuyến trang bắt đầu ra đời giành vị trí lớn trong việc đặt phòng ở Việt Nam. Các web trang online ngày càng thu hút lượng lớn khách .

​	Hệ thống dữ liệu có sẵn luôn, thông tin đầy đủ về vị trí, giá phòng, tiêu chuẩn, the tiện ích, dịch vụ giải trí, hình ảnh của hàng trăm khách sạn been phân loại cụ thể từ địa điểm đến giá phòng với nhiều cấp độ từ bình dân đến cao cấp, du khách dễ dàng chọn  khách sạn phù hợp với mình, 

 #### Mục tiêu phát triển của dự án

Tạo ra một website gồm những chức năng:

- Module Đặt phòng online cho du khách
- Áp dụng phương thức thanh toán online
- Quản lý số lượng du khách đặt phòng
- Quản lý doanh thu khách thanh toán
- Thống kê báo cáo
- Sử dụng các phương thức mã hóa trong quá trình giao dịch online

#### Quản lý phiên bản:

Chúng tôi dùng [Git](https://git-scm.com/) để tổ chức quản lý phiên bản theo hướng phân tán

#### Tác giả

- Lê Thị Hoài thuận - Trưởng Nhóm (Giám đốc dự án) | Email: Hoaithuan95@gmail.com 
- Trần Thanh Phương - cộng tác viên | Email:itplus1a1@gmail.com

#### Giấy phép: 

[Đồ án này được cấp phép theo giấy phép của General Public License - xem file [thông tin giấy phép](https://github.com/TcuNhom3/websitedatphongonline/blob/master/Th%C3%B4ng%20tin%20v%E1%BB%81%20gi%E1%BA%A5y%20ph%C3%A9p.md)



#### Kênh truyền thông cho dự án

[Chuyển tiếp đến kênh truyền thông dự án](https://www.facebook.com/Kh%C3%A1ch-s%E1%BA%A1n-Fairy-Bay-148207479088621/)

#### Chuẩn lập trình

Project được viết theo mô hình MVC kết hợp với các nguyên tắc trong lập trình

Các quy tắc về chuẩn lập trình:[Thông tin chi tiết về chuẩn lập trình](https://github.com/itplus77/4305-phan-mem-quan-ly-khach-san/blob/master/Quy%20t%E1%BA%AFc%20v%C3%A0%20phong%20c%C3%A1ch%20vi%E1%BA%BFt%20code%20trong%20l%E1%BA%ADp%20tr%C3%ACnh.md)

## Triển khai

Website đặt phòng khác sạn online được triển khai theo mô hình 3 lớp (Presentation - Bussiness Logic - Data Access) Khi bạn làm việc với các ứng dụng, nếu với những dự án nhỏ thì việc tạo một ứng dụng theo ý của chúng ta rất dễ dàng, tuy nhiên khi bạn làm với những dự án lớn hơn, cần nhiều người cùng làm hơn thì việc lập trình trở nên phức tạp hơn, vậy nên đễ dễ dàng hơn trong việc quản lý các thành phần của hệ thống cũng như ảnh hưởng tới các thành phần khác khi ta thay đổi một thành phần, chúng ta thường nhóm các thành phần có cùng chức năng lại với nhau. Chính vì thế các mô hình lập trình được sinh ra, một trong những mô hình lập trình đó là mô hình 3 lớp (3 - Layer).

- Tổ chức mô hình 3-Layer Có rất nhiều cách đặt tên cho các thành phần của 3 lớp như: Cách 1: GUI, BUS, DAL Cách 2: GUI, BLL, DAO, DTO Ở đây chúng tôi xin sử dụng cách này! Cách 3: Presentation, BLL, DAL
- Business Logic Layer Đây là layer xử lý chính các dữ liệu trước khi được đưa lên hiển thị trên màn hình hoặc xử lý các dữ liệu trước khi chuyển xuống Data Access Layer để lưu dữ liệu xuống cơ sở dữ liệu. Đây là nơi đê kiểm tra ràng buộc, các yêu cầu nghiệp vụ, tính toán, xử lý các yêu cầu và lựa chọn kết quả trả về cho Presentation Layers.
- Data Access Layer Lớp này thực hiện các nghiệp vụ liên quan đến lưu trữ và truy xuất dữ liệu của ứng dụng như đọc, lưu, cập nhật cơ sở dữ liệu.
- Cách vận hành của mô hình Đối với 3-Layer, yêu cầu được xử lý tuần tự qua các layer như hình.


- Đầu tiên User giao tiếp với Presentation Layers (GUI) để gửi đi thông tin và yêu cầu. Tại layer này, các thông tin sẽ được kiểm tra, nếu OK chúng sẽ được chuyển xuống Business Logic Layer (BLL).
- Tại BLL, các thông tin sẽ được nhào nặn, tính toán theo đúng yêu cầu đã gửi, nếu không cần đến Database thì BLL sẽ gửi trả kết quả về GUI, ngược lại nó sẽ đẩy dữ liệu (thông tin đã xử lý) xuống Data Access Layer (DAL).
- DAL sẽ thao tác với Database và trả kết quả về cho BLL, BLL kiểm tra và gửi nó lên GUI để hiển thị cho người dùng.
- Một khi gặp lỗi (các trường hợp không đúng dữ liệu) thì đang ở layer nào thì quăng lên trên layer cao hơn nó 1 bậc cho tới GUI thì sẽ quăng ra cho người dùng biết
- Các dữ liệu được trung chuyển giữa các Layer thông qua một đối tượng gọi là Data Transfer Object (DTO), đơn giản đây chỉ là các Class đại diện cho các đối tượng được lưu trữ trong Database.



#### Tài liệu dành cho nhà thiết kế:

Tài liệu thiết kế: [Tài liệu dành cho thiết kế Html css](https://thachpham.com/web-development/html-css/html-va-css-can-ban-danh-cho-cho-moi-nguoi.html)

#### Tài liệu cho người dùng cuối 

[See instructions](https://github.com/itplus77/4305-phan-mem-quan-ly-khach-san/blob/master/T%C3%A0i%20li%E1%BB%87u%20ng%C6%B0%E1%BB%9Di%20d%C3%B9ng%20cu%E1%BB%91i.docx)



#### Cách lấy mã và đóng góp mã nguồn

[Xem video hướng dẫn chi tiết](https://www.youtube.com/watch?v=yXT1ElMEkW8)

#### Tài liệu cho nhà phát triển:

- Hệ thống CSDL DB2: [hướng dẫn chi tiết](https://www.ibm.com/developerworks/vn/library/contest/dw-freebooks/Nhap_Mon_DB2_ExpressC/Nhap_mon_DB2_ExpressC_v9.7.pdf)
- Hướng dẫn lập trình JSP:[hướng dẫn chi tiết](http://o7planning.org/vi/10263/huong-dan-lap-trinh-java-jsp)
- Hướng dẫn kết nối CSDL:[chuyển tiếp đến trang hướng dẫn](https://zstar2.wordpress.com/2011/05/06/java-k%E1%BA%BFt-n%E1%BB%91i-csdl-t%E1%BB%AB-netbean/)



#### Danh sách các lỗi và cách sửa chữa:

- Lỗi kết nối CSDL: [kết nối CSDL DB2 đến JSP Hướng dẫn](http://congdongjava.com/forum/threads/help-k%E1%BA%BFt-n%E1%BB%91i-t%E1%BB%9Bi-csdl-b%E1%BA%B1ng-jsp.16832/)

- Tổng hợp lỗi trong JSP: [Cách khắc phục](http://kenhlaptrinh.net/bai-20-tong-hop-mot-so-loi-va-cach-khac-phuc-trong-jsp-servlet/)

  ​

#### Thông tin về tổ chức mã nguồn

Mã nguồn được viết theo mô hình MVC :

Thư mục [connections](https://github.com/TcuNhom3/websitedatphongonline/tree/master/connection): Chứa lớp kết nối

Thư mục [entities](https://github.com/TcuNhom3/websitedatphongonline/tree/master/entities): Chứa các đổi tượng

Thư mục [model](https://github.com/TcuNhom3/websitedatphongonline/tree/master/model): Chứa các trạng thái của đối tượng.



#### Demo Giao diện ban đầu

[chuyển tiếp đên trang web demo giao diện](https://itplus77.github.io/demodatphongonline.github.io/)



#### Kiến thức áp dụng

####  



- Sử dụng ngôn ngữ JSP và CSDL DB2 

- DataGridView, DataSet, DataTable, DataRow.

- Phân tích thiết kế hệ thống cơ sở dữ liệu.

- Phân tích thiết kế giao diện.

- Trigger SQL.

- Procedure, function SQL.

- Kết nối DB2 với JSP dùng JDBC.

- Chuyển data giữa các form.

- Phân quyền người dùng trên ứng dụng

- Thêm, xóa, sửa dữ liệu từ trang quản trị.

  ​

  ​















