# Buổi 2 — Khi Conflict Bắt Đầu Xuất Hiện

## Mục tiêu buổi học

Buổi 1 giúp sinh viên làm quen với GitHub Flow:

- Clone project
- Tạo branch
- Commit
- Push
- Pull Request
- Merge

Nhưng đó mới chỉ là giai đoạn dễ nhất.

Khi nhiều người cùng làm trên một project, vấn đề thực sự bắt đầu xuất hiện:

- Sửa đè code của nhau
- Merge Conflict
- Reviewer reject Pull Request
- Branch bị lỗi thời
- Code chạy trên máy mình nhưng không chạy trên máy người khác
- Requirement thay đổi giữa chừng

Mục tiêu của buổi học không phải tránh conflict.

Mục tiêu là:

- Hiểu conflict là gì
- Biết vì sao conflict xảy ra
- Tự resolve conflict
- Giao tiếp với đồng đội khi xảy ra conflict

---

# Conflict Là Gì?

Conflict xảy ra khi Git không biết nên giữ thay đổi nào.

Git có thể tự merge khi:

- Hai người sửa hai file khác nhau
- Hai người sửa hai vị trí khác nhau

Git KHÔNG thể tự merge khi:

- Hai người sửa cùng một dòng
- Hai người sửa cùng một đoạn code

Lúc đó Git sẽ yêu cầu con người quyết định.

---

# Minh Hoạ Conflict Thực Tế

File ban đầu:

```html
<h1>FPT Polytechnic</h1>
```

## Thành viên A

Sửa:

```html
<h1>FPT Polytechnic Hà Nội</h1>
```

Commit:

```bash
git add .
git commit -m "Update title HN"
git push
```

Pull Request được merge.

---

## Thành viên B

Trong lúc đó vẫn đang làm việc trên branch cũ.

B sửa cùng dòng:

```html
<h1>FPT Polytechnic Summer 2026</h1>
```

Commit:

```bash
git add .
git commit -m "Update title summer"
```

Khi pull code mới:

```bash
git pull origin main
```

Git báo:

```bash
CONFLICT (content): Merge conflict in index.html
Automatic merge failed
```

---

# Git Đang Nói Điều Gì?

Git thấy:

Main:

```html
<h1>FPT Polytechnic Hà Nội</h1>
```

Branch của B:

```html
<h1>FPT Polytechnic Summer 2026</h1>
```

Git không biết:

- Giữ Hà Nội?
- Giữ Summer?
- Hay giữ cả hai?

Nên Git dừng lại và hỏi lập trình viên.

---

# Cấu Trúc Một Conflict

Git tạo:

```html
<<<<<<< HEAD
FPT Polytechnic Summer 2026
=======
FPT Polytechnic Hà Nội
>>>>>>> main
```

Ý nghĩa:

HEAD:

```html
FPT Polytechnic Summer 2026
```

Là code hiện tại.

main:

```html
FPT Polytechnic Hà Nội
```

Là code từ branch được merge vào.

---

# Resolve Conflict

Lập trình viên quyết định:

```html
<h1>FPT Polytechnic Hà Nội - Summer 2026</h1>
```

Sau đó:

```bash
git add .
git commit -m "Resolve conflict"
```

Conflict được xử lý.

---

# Vì Sao Sinh Viên Hay Gặp Conflict?

## Nguyên nhân 1 — Làm Chung Một File

Ví dụ:

- Cả nhóm cùng sửa App.tsx
- Cả nhóm cùng sửa index.js
- Cả nhóm cùng sửa routes.ts

Đây là nguyên nhân phổ biến nhất.

---

## Nguyên nhân 2 — Quên Pull

Buổi sáng:

```bash
git pull
```

Sau đó code liên tục 4 tiếng.

Trong lúc đó:

- 3 người merge code
- main thay đổi

Đến chiều mới pull.

Conflict xuất hiện.

---

## Nguyên nhân 3 — Branch Quá Lâu

Tạo branch thứ Hai.

Đến thứ Sáu mới merge.

Trong 5 ngày:

- hàng chục commit đã xuất hiện

Khả năng conflict rất cao.

---

# Quy Tắc Hạn Chế Conflict

## Quy tắc 1

Pull trước khi bắt đầu làm việc.

```bash
git checkout main
git pull
```

## Quy tắc 2

Branch nhỏ.

Không giữ branch nhiều ngày.

## Quy tắc 3

Merge thường xuyên.

Không đợi hoàn thành toàn bộ dự án.

## Quy tắc 4

Trao đổi với đồng đội.

Nếu cùng sửa một module:

- Ai làm phần nào?
- Ai merge trước?

---

# Workshop Thực Hành 1

Mục tiêu:

Tạo conflict đầu tiên.

### Bước 1

Tạo nhóm 2 người.

### Bước 2

Cả hai sửa cùng một dòng.

### Bước 3

Người A merge trước.

### Bước 4

Người B pull code.

### Bước 5

Resolve conflict.

### Bước 6

Push lại thành công.

---

# Workshop Thực Hành 2

Mục tiêu:

Conflict trong React.

File:

```jsx
function Header() {
    return <h1>Website</h1>;
}
```

Người A:

```jsx
return <h1>FPT Polytechnic</h1>;
```

Người B:

```jsx
return <h1>Summer 2026</h1>;
```

Tạo conflict.

Sinh viên phải tự xử lý.

---

# Workshop Thực Hành 3

Mục tiêu:

Conflict nhiều file.

Các nhóm:

- Người A sửa Header
- Người B sửa Footer
- Người C sửa Navbar

Sau đó:

Giảng viên yêu cầu tất cả sửa Navbar.

Conflict sẽ xuất hiện hàng loạt.

---

# Pull Request Bị Reject

Trong công ty:

Không phải PR nào cũng được merge.

Reviewer có thể comment:

- Chưa đúng coding convention
- Tên biến chưa rõ nghĩa
- Code bị lặp
- Chưa xử lý lỗi

Ví dụ:

```text
Please rename this variable.
```

```text
Need validation.
```

```text
Duplicate logic.
```

Sinh viên phải:

- sửa code
- commit lại
- push lại

Thay vì tạo PR mới.

---

# Teamwork Thực Tế

Khi project lớn lên:

Conflict không còn là vấn đề kỹ thuật.

Nó trở thành vấn đề giao tiếp.

Ví dụ:

Người A sửa Navbar.

Người B cũng sửa Navbar.

Nếu trao đổi trước:

Không conflict.

Nếu không trao đổi:

Conflict gần như chắc chắn.

---

# Mini Challenge

Mỗi nhóm nhận project chung.

Giảng viên cố tình:

- thay đổi requirement
- merge code bất ngờ
- tạo conflict
- reject Pull Request

Nhóm phải:

- giao tiếp
- resolve conflict
- sửa PR
- hoàn thành task

---

# Kết Quả Sau Buổi Học

Sinh viên có thể:

✅ Hiểu conflict là gì

✅ Đọc được conflict marker

✅ Resolve conflict thủ công

✅ Pull code đúng thời điểm

✅ Hiểu nguyên nhân conflict

✅ Biết cách hạn chế conflict

✅ Chỉnh sửa Pull Request sau review

✅ Trải nghiệm teamwork gần với môi trường doanh nghiệp
