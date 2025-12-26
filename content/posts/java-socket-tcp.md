+++
date = '2025-12-26T15:58:01+07:00'
draft = false
title = 'Lập trình Socket Tcp trong Java'
+++
### 1. Khái niệm về Socket
Trong lập trình mạng, Socket là điểm cuối (endpoint) của một liên kết truyền thông hai chiều giữa hai chương trình đang chạy trên mạng.

### 2. Ví dụ Code đơn giản
Dưới đây là cách tạo một Server đơn giản:

```java
ServerSocket serverSocket = new ServerSocket(6666);
Socket s = serverSocket.accept(); // Đợi kết nối từ Client
