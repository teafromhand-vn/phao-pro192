# AI_INSTRUCTION – Quy tắc làm việc trong repository này

> File này dành cho mọi AI agent (Claude, Copilot, Cursor, Codex…) làm việc trong repo.
> Đọc hết trước khi sửa bất kỳ file nào.

## 1. Quy tắc bắt buộc: commit và push MỖI thay đổi

Đây là quy tắc quan trọng nhất của repo. Không có ngoại lệ.

Sau **mỗi** thay đổi nội dung (thêm mục, sửa công thức, viết lại đoạn văn, sửa lỗi chính tả, đổi code mẫu…), agent phải:

1. `git add` đúng các file vừa sửa.
2. `git commit` với message mô tả thay đổi.
3. `git push` lên `origin main`.
4. Chỉ sau khi push thành công mới được coi là hoàn thành nhiệm vụ.

```sh
git add Phao_PRO192.md
git commit -m "Add String.length() operation atlas"
git push origin main
```

### Không được làm

- Không gộp nhiều thay đổi không liên quan vào một commit.
- Không để thay đổi nằm ở working tree qua lượt trả lời tiếp theo.
- Không dùng `git commit --amend` hoặc `git push --force` lên `main` nếu chưa được người dùng cho phép rõ ràng.
- Không commit file rác: `*.class`, `*.jar`, `out/`, `build/`, `.idea/`, file tạm của IDE.
- Không commit dữ liệu cá nhân, tài khoản, token, API key.

### Trước khi commit

```sh
git status            # xem file nào sẽ vào commit
git diff              # đọc lại đúng nội dung đã sửa
```

Nếu `git diff` không đúng như ý định thì sửa lại trước, đừng commit rồi mới sửa.

### Message commit

Viết tiếng Anh, thể mệnh lệnh, ngắn gọn, nêu rõ nội dung:

| Nên | Không nên |
|---|---|
| `Add String.length() operation atlas` | `update` |
| `Fix wrong substring end index in 59.4` | `fix bug` |
| `Add StringBuilder setLength examples` | `more stuff` |
| `Correct Vietnamese typo in section 58.9` | `sửa` |

Nếu một thay đổi lớn gồm nhiều phần độc lập, chia thành nhiều commit nhỏ rồi push một lần cũng được — miễn là mọi thay đổi đều đã lên remote.

## 2. Cấu trúc repository

```text
Phao_PRO192.md    # Nội dung chính: cheat sheet PRO192
AI_instruction.md # File này: quy tắc cho AI agent
README.md         # Giới thiệu repository
```

`Phao_PRO192.md` là **file nguồn duy nhất** của tài liệu. Không tạo bản sao, không tách thành nhiều file rời, không sinh thêm file `.txt`/`.pdf` thay thế nếu người dùng không yêu cầu.

## 3. Quy ước nội dung `Phao_PRO192.md`

- Ngôn ngữ: tiếng Việt, giữ nguyên các keyword tiếng Anh của đề thi trong dấu backtick.
- Mã Java: cú pháp **Java 8 / JDK 1.8**. Không dùng `String.isBlank()`, `var`, `List.of()`, text block, `switch` expression — phòng thi có thể không hỗ trợ.
- Đánh dấu nguồn gốc khi thêm dạng bài mới:
  - `[ĐÃ XUẤT HIỆN TRONG ĐỀ MẪU]` – rút ra từ đề thật đã có.
  - `[MỞ RỘNG – CÓ THỂ DÙNG]` – cú pháp Java phổ biến, không chắc xuất hiện.
- Code block có ngôn ngữ: ```` ```java ````, ```` ```sh ````, ```` ```text ````.
- Bảng dùng `|---|---|` cho dễ đọc trên GitHub.
- Đánh số mục theo thứ tự tăng dần, không tái sử dụng số đã có cho nội dung khác.
- Khi thêm mục lớn, cập nhật lại **MỤC LỤC TRA CỨU** ở đầu file.

## 4. Kiểm chứng trước khi ghi vào tài liệu

Không viết vào tài liệu những gì chưa kiểm tra được. Với code Java:

```sh
javac -encoding UTF-8 TenFile.java
java TenFile
```

Chỉ dán vào tài liệu những đoạn đã chạy đúng, hoặc ghi rõ là "mẫu lý thuyết chưa chạy". Đặc biệt cẩn thận với:

- `substring(begin, end)` — `end` là **exclusive**.
- `charAt(s.length())` — luôn sai; index hợp lệ là `0 .. length() - 1`.
- `split(".")` — là regex, phải viết `split("\\.")`.
- `String.length()` vs `array.length` vs `List.size()`.
- Đếm chữ số của số âm — dấu `-` bị tính là một ký tự.

## 5. Không làm gì ngoài phạm vi được yêu cầu

- Không đổi cấu trúc tài liệu, không xóa mục đang có, không "dọn dẹp" nội dung người dùng đã viết nếu không được yêu cầu.
- Không tự thêm license, CI, workflow, script build.
- Không đổi tên file hoặc đổi tên repo.
- Nếu thấy nội dung sai, báo lại và đề xuất sửa — không tự sửa những chỗ ngoài yêu cầu.

## 6. Xử lý khi push thất bại

```sh
git pull --rebase origin main
git push origin main
```

Nếu có xung đột (conflict): đọc kỹ cả hai phía, giữ nội dung đúng, rồi `git rebase --continue`. Không dùng `--force` để "cho xong".

Báo lại cho người dùng nếu không thể giải quyết mà không mất nội dung.
