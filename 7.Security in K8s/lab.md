
```
- Chạy pod ubuntu với user non-root

- Khởi tạo 1 pod chạy redis, cấu hình pod này chỉ có thể gọi vào từ những
namespace có label ns=webserver và những pod có label pod=nginx (dùng
cùng 1 NetworkPolicy)

- Tạo người dùng viewer chỉ có quyền get resoures tại namespace default
```
