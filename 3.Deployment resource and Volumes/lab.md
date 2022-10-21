# Deployment resource and Volumes

```
Tạo một Deployment có tên web-server:
- Các pod trong Deployment này chạy 2 container, 1 container chạy dịch vụ nginx, 1 container chạy sidecar clone code dùng gitRepo rồi mount code vào container chính sử dụng EmptyDir volume.

- Log của web server nginx được mount ra Node tại path /tmp/
```