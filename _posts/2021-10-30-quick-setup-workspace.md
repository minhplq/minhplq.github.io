---
layout: post
title:  "Thiết lập môi trường làm việc một cách nhanh nhất có thể"
date:   2021-10-30
categories: [tip&trick]
---

## Lý do có bài này

Mình là một đứa khá thích vọc vạch, nên phải cài lại OS khá là nhiều :)) Và mỗi lần cài lại phải cài ty tỷ thứ liên quan thì mới có thể bắt đầu code được!

Rất may là Linux có hỗ trợ Shell, phải nói là có thằng này thì quá tiện cho mọi tác vụ hệ thống mình cần. Bao gồm cả thiết lập môi trường ban đầu.

Cho bạn nào chưa biết thì shell là một môi trường cho phép chúng ta tương tác trực tiếp thông qua lệnh shell, nên việc bắt máy tính chạy cài đặt một vài phần mềm được định sẵn rất là tiện. Mỗi lần cài lại OS, bạn chỉ cần chạy lại một tập lệnh là "A lê hấp!" - mọi thứ bạn cần đã sẵn sàng để sử dụng!!

Đây là lý do mà Linux luôn là môi trường phát triển hàng đầu cho lập trình viên đấy, bạn nào chưa thử thì nên thử ngay và luôn!!

Mình sử dụng Python là ngôn ngữ chính, nên mình thiết lập môi trường xung quanh Python. Các ngôn ngữ/công cụ khác đều tương tự, miễn là bạn nắm được cách cài đặt nó!!

## Mình cần những gì?

Để code được một cách suôn sẻ, mình cần một số công cụ sau:

- zsh (và một số custom function)
- git
- pyenv - python
- chrome
- docker
    - postgresql - pgAdmin4
- dbeaver
- vscode (+extension)

Cơ bản là như vậy, sau khi đã liệt kê các công cụ cần thiết theo thứ tự cài đặt trước sau, việc còn lại chỉ là viết Shell cho Linux nó tự chạy thôi

```bash
$
```

Lưu đoạn bash này vào đâu đó, để các bạn có thể sử dụng ngay khi mới cài OS. Riêng mình thì mình lưu trên Gist - Một công cụ note của Github khá là hữu ích.

Vầ từ nay trở đi, mỗi khi các bạn cần thiết lập môi trường mới, thì công việc của bạn bây giờ chỉ còn:

Cài hệ điều hành -> tải và chạy tập lệnh cài đặt -> đi uống ly cafe + trò chuyện cùng vài đồng nghiệp :v -> 10p sau quay lại và code hết mình!!

Vậy là mình chỉ mất một khoảng thời gian ban đầu để viết script, còn những lần sau thì mình chỉ cần chờ thôi :D không phải lăn tăn việc thiếu đủ công cụ nhé!!

Hy vọng bài viết này có thể giúp các bạn dễ dàng hơn trong công việc một chút!!

Happy Coding!!!

P/s: à mà ngoài việc tự mình viết shell, các bạn còn có thể sử dụng các công cụ khác để làm.
P/s 2: Ngoài Linux ra thì các OS khác (Mac và Windows) cũng hỗ trợ Shell đấy (với windows thì là command promt). Với cách làm tương tự, bạn cũng có thể tự động hoá bước này, nhưng Windows thì hơi khó để dùng đấy nhá!!!
