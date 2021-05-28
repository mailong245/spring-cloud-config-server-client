# SPRING CLOUD CONFIG CLIENT-SERVER EXAMPLE

## 1. Định nghĩa client-server config:
 - Sử dụng Spring cloud bus
 - Giúp việc đọc và sửa config của dự án dễ dàng mà không phải build lại

## 2. Server config: 
 - có nhiệm vụ lấy config từ các git server hoặc server vật lý
 - Server sử dụng annotation @EnableConfigServer để đăng ký làm một Server config
 - Server sử dụng config spring.cloud.config.server.git.uri=git_url để đọc config từ git
 - sau khi đọc xong có thể truy cập bằng cách localhost:port/tên-file-trên-git.properties

## 3. Client config:
 - Lấy config từ server config
 - @Value: Lấy ra các key có trong config
 - @RefreshScope để lấy config mới (kết hợp với POST localhost:7777/actuator/refresh để load lại dữ liệu)
 - Actuator cho phép ta theo dõi, giám sát ứng dụng, thu thập số liệu, lưu lượng truy cập hay trạng thái cơ sở dữ liệu,...
 - management.endpoints.web.exposure.include=*: cấu hình cho phép user truy cập vào tất cả (*) các endpoint của actuator

## 4. Các bước thực hiện demo
 - Bước 1: Tạo file cấu hình trên git
 - Bước 2: Chạy project server config
 - Bước 3: Chạy project client config
