# Redpandoku Level Studio

Tool tạo & thẩm định level cho **Redpandoku** — biến thể Star Battle 1 sao
(1 gấu trúc mỗi hàng, mỗi cột, mỗi vùng; không con nào được kề nhau kể cả chéo).

Toàn bộ tool nằm trong **một file HTML chạy offline** — mở bằng trình duyệt là dùng được,
không cần cài gì.

## Nội dung

`Redpandoku_Level_Studio.html` gồm các khối độc lập:

| Khối | Vai trò |
|---|---|
| `engine` | Bộ sinh + solver gốc (phần lớn đã bị `brain` thay thế) |
| `brain` | Solver theo bậc kỹ thuật T1–T6, mô hình chấm độ khó, bộ sinh theo mục tiêu |
| `similarity` | Đo độ giống nhau giữa các màn bằng tập cạnh biên |
| `picture` / `aesthetics` / `special` | Xưởng màn có hình vẽ & chủ đề cấu trúc cho Thử Thách Ngày |
| `boosters` | Gợi Ý, Vuốt Gấu, Lá Phép |
| `tutorial` | 14 bài hướng dẫn trải trên 21 màn đầu |
| `studio UI` / `bridge` | Giao diện tác giả + xưởng sinh hàng loạt |

## Bất biến của một màn hợp lệ

Mọi màn phải qua `validateLevel` (I01–I15): đúng N vùng, mọi vùng liền khối,
đúng 1 gấu mỗi hàng/cột/vùng, không con nào kề nhau, **đúng 1 nghiệm duy nhất**,
giải được bằng logic thuần (không phải đoán), và không trùng màn nào đã có
kể cả qua 8 phép xoay/lật.
