# Buổi 1 — Code Một Mình Khác Gì Code Theo Team?

## Mục tiêu buổi học

Giúp sinh viên:

- Hiểu vì sao Git/GitHub Flow quan trọng khi làm đồ án nhóm
- Trải nghiệm cảm giác “đụng nhau” khi cùng sửa code
- Biết quy trình cơ bản:
  - Nhận task
  - Tạo branch
  - Commit
  - Push code
  - Tạo Pull Request
  - Review & Merge

### Kết thúc buổi

Mỗi nhóm merge được feature đầu tiên vào `main`.

---

# 1. Mở đầu — Vì Sao Đồ Án Team Hay “Toang”?

## Tình huống quen thuộc

- “Ai từng bị mất code?”
- “Ai từng sửa đè file?”
- “Ai từng copy project của bạn rồi gửi lại zip?”
- “Ai từng ngại pull code vì sợ hỏng?”

## Demo nhanh

### Code một mình

- Sửa trực tiếp
- Thích commit lúc nào cũng được
- Không ai đụng code mình

### Code theo team

- Nhiều người cùng sửa
- Phải chia task
- Phải đồng bộ
- Cần review
- Cần quy trình

## Kết luận

> Git không chỉ để lưu code. Git là cách để teamwork mà không phá project của nhau.

---

# 2. Giới Thiệu Mini Project

## Gợi ý project nhỏ

- Website đặt vé xem phim
- Website quản lý phòng trọ
- Website đặt vé xe
- Website đặt lịch sân bóng

## Yêu cầu project

- Có FrontEnd, Backend
- Chia được task rõ
- Có file dễ conflict

## Ví dụ chia task

| Thành viên | Task     |
| ---------- | -------- |
| A          | Login    |
| B          | Navbar   |
| C          | Register |
| D          | Routes   |

---

# 3. Trải Nghiệm Nhận Task Giống Team Thật

## Sinh viên thực hành

- Tạo GitHub repo
- Add collaborator
- Clone project

## Giải thích Branch

```bash
main
feature/login
feature/navbar
```

### Ý nghĩa

- `main` = code ổn định
- `feature/*` = khu vực làm việc riêng

> Branch giống timeline riêng của mỗi người.

---

# 4. Thực Hành Git Flow Cơ Bản

## Bước 1 — Clone project

```bash
git clone <repo-url>
```

### Giải thích

- Local code
- Remote repo
- `origin`

## Bước 2 — Tạo branch riêng

```bash
git checkout -b feature/login
```

### Giải thích

- Không code trực tiếp trên `main`
- Mỗi task → một branch

Kiểm tra branch:

```bash
git branch
```

## Bước 3 — Code Feature

Mỗi người làm task riêng.

### Giải thích thêm

- Staging area là gì?
- Vì sao không commit tất cả linh tinh?

## Bước 4 — Commit

```bash
git add .
git commit -m "feat: add login form"
```

## Commit message tốt

### Không nên

```text
fix
done
update
aaaa
```

### Nên

```text
feat: add navbar
fix: resolve login validation
style: update button UI
```

---

# 5. Push Code Lên GitHub

```bash
git push origin feature/login
```

## Giải thích

- Local vs Remote
- Push để team thấy code

---

# 6. Pull Request — Khoảnh Khắc “Code Team” Thật Sự

## Pull Request là gì?

Không phải:

> Tôi code xong rồi.

Mà là:

> Mọi người review giúp tôi trước khi nhập vào project.

## Ví dụ PR Description

```md
## Feature

- add login UI
- validate email

## Test

- tested manually
```

---

# 7. Review Code Cơ Bản

## Review chéo

- Naming
- Format
- Thiếu code
- Code khó đọc

## Ví dụ comment review

- “Tên biến này chưa rõ”
- “Tách function này được không?”
- “Hard code chỗ này nhé”

---

# 8. Merge Feature Đầu Tiên

```text
Merge Pull Request
```

Pull code mới:

```bash
git pull origin main
```

> Đây là lần đầu code của nhiều người được ghép lại thành một project.

---

# 9. Mini “Drama” Cuối Buổi

## Cố tình tạo lỗi

- 2 người sửa cùng file
- Quên pull trước khi code
- Commit thiếu file

---

# 10. Tổng Kết Cuối Buổi

## Sinh viên học được gì?

- Git không khó nếu hiểu workflow
- Teamwork cần quy tắc
- Branch giúp không phá code nhau
- PR giúp review trước khi merge

> Code team không giống làm bài tập cá nhân.

---

# Homework Sau Buổi 1

## Mỗi nhóm

Tạo thêm 2 feature.

### Mỗi feature phải:

- Branch riêng
- Commit rõ ràng
- Tạo PR
- Review chéo

## Không được

```text
Push trực tiếp vào main
```

---

# Flow Cả Buổi

```text
Nhận task
→ Tạo branch
→ Code
→ Commit
→ Push
→ Pull Request
→ Review
→ Merge
→ Pull code mới
```

---

# Kết luận

> Sinh viên nhớ conflict và PR reject lâu hơn nhớ định nghĩa Git.
