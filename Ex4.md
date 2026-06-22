# BÀI 4: Phân tích & Lựa chọn

## 1. Đáp án lựa chọn

**Đáp án đúng: B**

---

## 2. Giải thích lý do lựa chọn phương án B

Phương án B là phản hồi tối ưu nhất vì nó thể hiện đúng kỹ thuật **Iterative Prompting**. Người dùng không chỉ nói chung chung rằng code chậm, mà còn phản hồi cụ thể dựa trên kết quả AI đã sinh ra ở lượt trước.

Phương án B chỉ rõ vấn đề của thuật toán ban đầu:

```java
return fib(n - 1) + fib(n - 2);
```

Đây là cách tính Fibonacci bằng đệ quy cổ điển, khiến nhiều giá trị bị tính đi tính lại nhiều lần. Vì vậy, độ phức tạp thời gian xấp xỉ `O(2^N)`, làm chương trình dễ bị treo khi `n = 50`.

Phương án B tối ưu vì có các ràng buộc kỹ thuật rõ ràng:

* Chỉ ra lỗi hiệu năng: thuật toán đệ quy có độ phức tạp `O(2^N)`.
* Nêu rõ tình huống gây lỗi: hệ thống bị treo khi `n = 50`.
* Yêu cầu thuật toán cụ thể: sử dụng **Dynamic Programming**.
* Cho phép hướng triển khai rõ ràng: **Tabulation** hoặc **Memoization**.
* Đặt mục tiêu độ phức tạp: thời gian `O(N)`.
* Đưa ra ràng buộc bộ nhớ: không gian `O(1)` hoặc `O(N)`.
* Giữ nguyên kiểu trả về `long`, tránh việc AI tự ý đổi sang `int`, `double` hoặc `BigInteger`.

Nhờ các thông tin này, AI có đủ ngữ cảnh và yêu cầu cụ thể để sửa đúng vấn đề hiệu năng, đồng thời vẫn giữ được hành vi mong muốn của hàm ban đầu.

---

## 3. Nhược điểm của phương án A

Phương án A:

> "Code chạy chậm quá, viết lại bằng thuật toán khác tối ưu hơn giúp tôi."

Phương án này chưa tối ưu vì quá chung chung.

Các nhược điểm chính:

* Không chỉ rõ thuật toán hiện tại chậm ở đâu.
* Không nêu độ phức tạp hiện tại là `O(2^N)`.
* Không yêu cầu cụ thể dùng **Dynamic Programming**.
* Không đặt mục tiêu độ phức tạp sau khi tối ưu.
* Không yêu cầu giữ nguyên kiểu trả về `long`.
* Không nêu tình huống cụ thể như `n = 50`.

Vì vậy, AI có thể sửa theo nhiều hướng khác nhau nhưng chưa chắc đúng yêu cầu. Ví dụ, AI có thể chỉ viết lại code cho “gọn hơn” nhưng vẫn giữ đệ quy chậm.

---

## 4. Nhược điểm của phương án C

Phương án C:

> "Hãy viết lại code tính Fibonacci bằng cách sử dụng Java Stream API để code chạy song song (parallel) cho nhanh hơn."

Phương án này không phù hợp vì xác định sai hướng tối ưu.

Lỗi chính của thuật toán Fibonacci đệ quy không nằm ở việc thiếu chạy song song, mà nằm ở việc tính lặp lại quá nhiều bài toán con. Nếu chỉ dùng Java Stream API hoặc parallel stream, chương trình có thể vẫn phải tính lại rất nhiều giá trị giống nhau.

Các nhược điểm chính:

* Tập trung sai giải pháp: dùng Stream API thay vì Dynamic Programming.
* Parallel không giải quyết tận gốc độ phức tạp `O(2^N)`.
* Có thể làm code phức tạp hơn nhưng không cải thiện đáng kể.
* Có thể phát sinh overhead do quản lý luồng.
* Không đặt ràng buộc giữ nguyên kiểu trả về `long`.
* Không yêu cầu mục tiêu độ phức tạp `O(N)`.

Vì vậy, phương án C có nguy cơ tạo ra mã nguồn dài hơn, khó hiểu hơn và vẫn không xử lý đúng nguyên nhân gốc rễ của vấn đề hiệu năng.

---

## 5. Kết luận

Phương án **B** là lựa chọn tối ưu nhất vì phản hồi rõ ràng, có cơ sở thuật toán và đưa ra yêu cầu kỹ thuật cụ thể. Đây là ví dụ tốt của kỹ thuật **Iterative Prompting**, trong đó người dùng dựa trên kết quả chưa đạt yêu cầu của AI để đưa thêm ràng buộc, mục tiêu và hướng tối ưu chính xác hơn.
