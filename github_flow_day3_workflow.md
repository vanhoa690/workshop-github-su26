# Buổi 3 — Làm Sao Để Team Code Không Toang?

## Mục tiêu buổi học

Sau Buổi 1 sinh viên đã biết GitHub Flow cơ bản.

Sau Buổi 2 sinh viên đã trải nghiệm conflict, PR bị reject và các vấn đề khi teamwork.

Buổi 3 tập trung vào một câu hỏi:

Làm sao để team làm việc hiệu quả hơn và giảm bớt những vấn đề đã gặp?

## Nội dung chính

- Viết commit message rõ ràng
- Chia task hợp lý
- Review code hiệu quả
- Giảm conflict
- Xây dựng workflow ổn định
- Thực hành mini project theo quy trình tốt hơn

---

# 1. Nhìn Lại Drama Của Buổi 2

Mỗi nhóm thảo luận:

- Conflict xuất hiện ở đâu?
- Vì sao conflict xuất hiện?
- PR nào bị reject?
- Lỗi nào lặp lại nhiều lần?
- Điều gì khiến teamwork khó khăn nhất?

Bài học:

Conflict thường xuất phát từ:

- Không pull thường xuyên
- Sửa cùng file
- Chia task chưa rõ ràng
- Giao tiếp chưa tốt

---

# 2. Viết Commit Message Chuyên Nghiệp

## Commit Message Tệ

git commit -m "fix"

git commit -m "update"

git commit -m "123"

Không ai biết commit đó làm gì.

## Commit Message Tốt

git commit -m "Add login form UI"

git commit -m "Fix email validation"

git commit -m "Update navbar responsive"

Người khác chỉ cần đọc lịch sử commit là hiểu được thay đổi.

---

# 3. Chia Task Để Giảm Conflict

Ví dụ không tốt:

5 người cùng sửa App.tsx

Kết quả:

- Conflict liên tục
- Khó review
- Khó merge

Ví dụ tốt:

Người A: Login

Người B: Register

Người C: Product

Người D: Cart

Người E: Profile

Mỗi người phụ trách một module.

---

# 4. Review Code Hiệu Quả

Review không phải để bắt lỗi.

Review nhằm:

- Phát hiện bug sớm
- Giữ code đồng nhất
- Chia sẻ kiến thức

Những điều cần review:

- Naming
- Logic
- Readability
- Validation
- Code duplication

---

# 5. Giảm Conflict Ngay Từ Đầu

Nguyên tắc 1:

Pull code thường xuyên

Nguyên tắc 2:

Branch nhỏ và ngắn hạn

Nguyên tắc 3:

Merge sớm

Nguyên tắc 4:

Trao đổi trước khi sửa phần code dùng chung

Nguyên tắc 5:

PR nhỏ dễ review hơn PR lớn

---

# 6. Workflow Team Ổn Định

1. Nhận task
2. Tạo branch
3. Code
4. Commit rõ ràng
5. Push
6. Tạo Pull Request
7. Review
8. Sửa theo review
9. Merge
10. Xóa branch

---

# 7. Mini Project Cuối Workshop

Mỗi nhóm thực hiện lại mini project.

Yêu cầu:

- Chia task rõ ràng
- Commit message tốt
- Review code
- Tạo Pull Request
- Merge thành công

Mục tiêu:

Workflow mượt hơn Buổi 2.

---

# Điều Sinh Viên Nhận Được Sau Workshop

Sau 3 buổi, sinh viên có thể:

- Hiểu GitHub Flow thực tế
- Làm việc nhóm bằng Git/GitHub
- Review code cơ bản
- Resolve conflict
- Chia task hợp lý
- Viết commit message rõ ràng
- Hiểu workflow doanh nghiệp

## Thông Điệp Cuối Cùng

Sinh viên thường không nhớ định nghĩa Git.

Nhưng sẽ nhớ rất lâu:

- Lần đầu PR bị reject
- Lần đầu resolve conflict
- Lần đầu teamwork trên một project thật

Đó chính là giá trị lớn nhất của workshop.
