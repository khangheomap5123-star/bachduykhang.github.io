+++
date = '2025-12-26T15:58:43+07:00'
draft = false
title = 'Js Async Await'
+++
### 1. Khái niệm về Js Async Await
Async/Await trong JavaScript giúp viết code bất đồng bộ (async) trông giống code đồng bộ, dùng async khai báo hàm để luôn trả về Promise, và dùng await (chỉ trong hàm async) để tạm dừng chờ Promise trả kết quả, giúp xử lý API và các tác vụ đợi (delay) dễ dàng hơn nhiều so với dùng .then() hay callbacks, ví dụ: tạo hàm async chờ setTimeout, rồi gọi nó với await để in ra thông báo sau một khoảng thời gian. 

### 2. Ví dụ Code đơn giản
Dưới đây là cách tạo một hàm chờ đơn giản:
```java
// 1. Tạo một Promise đơn giản giả lập việc chờ đợi (ví dụ: gọi API)
function fakeApiCall(data, delay) {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log(`[API] Dữ liệu nhận được: ${data}`);
      resolve(data); // Trả về kết quả khi Promise hoàn thành
    }, delay);
  });
}

// 2. Hàm chính dùng async/await
async function fetchData() {
  console.log("Bắt đầu lấy dữ liệu...");

  // Dùng await để đợi fakeApiCall hoàn thành
  const result1 = await fakeApiCall("Dữ liệu A", 2000); // Chờ 2s
  console.log(`[Hàm chính] Nhận được: ${result1}`);

  const result2 = await fakeApiCall("Dữ liệu B", 1000); // Chờ 1s
  console.log(`[Hàm chính] Nhận được: ${result2}`);

  console.log("Lấy dữ liệu hoàn tất!");
}

// Gọi hàm để bắt đầu
fetchData();
console.log("Đây là dòng code chạy ngay, không đợi fetchData xong!");

