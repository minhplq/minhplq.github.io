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

Đây là ví dụ một file cơ bản mà mình chạy trên ubuntu, các distro khác tương tự nhé

```bash
# update OS

sudo apt update \
  && sudo apt upgrade -y \
  && sudo apt autoclean -y \
  && sudo apt autoremove -y \
  && sudo snap refresh

# go to Downloads folder

cd ~/Downloads

# install zsh - source: https://github.com/jotyGill/ezsh

git clone https://github.com/jotyGill/ezsh
./install.sh -c        # only run with '-c' the first time, running multiple times will duplicate history entries

# install pyenv

# Prerequisites
sudo apt-get update; sudo apt-get install make build-essential libssl-dev zlib1g-dev \
    libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
    libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev

# auto install
curl https://pyenv.run | bash

# restart shell
exec $SHELL

# config for shell
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zprofile
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zprofile
echo 'eval "$(pyenv init --path)"' >> ~/.zprofile

echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile
echo 'eval "$(pyenv init --path)"' >> ~/.profile

echo 'eval "$(pyenv init -)"' >> ~/.zshrc

# need to logout - login, and choose python version to install

# install wget
sudo apt install wget

# download chrome.deb
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo install ./google-chrome-stable_current_amd64.deb

# install docker - source: https://github.com/docker/docker-install
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh

sudo groupadd docker
sudo usermod -aG docker $USER

# install dbeaver 
wget https://dbeaver.io/files/dbeaver-ce_latest_amd64.deb
sudo apt install ./dbeaver-ce_latest_amd64.deb

# install vscode - source: https://code.visualstudio.com/docs/setup/linux
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm -f packages.microsoft.gpg

sudo apt install apt-transport-https
sudo apt update
sudo apt install code # or code-insiders

```

Lưu đoạn bash này vào đâu đó, để các bạn có thể sử dụng ngay khi mới cài OS. Riêng mình thì mình lưu trên Gist - Một công cụ note của Github khá là hữu ích.

Vầ từ nay trở đi, mỗi khi các bạn cần thiết lập môi trường mới, thì công việc của bạn bây giờ chỉ còn:

Cài hệ điều hành -> tải và chạy tập lệnh cài đặt -> đi uống ly cafe + trò chuyện cùng vài đồng nghiệp :v -> 10p sau quay lại và code hết mình!!

Vậy là mình chỉ mất một khoảng thời gian ban đầu để viết script, còn những lần sau thì mình chỉ cần chờ thôi :D không phải lăn tăn việc thiếu đủ công cụ nhé!!

Hy vọng bài viết này có thể giúp các bạn dễ dàng hơn trong công việc một chút!!

Happy Coding!!!

P/s: à mà ngoài việc tự mình viết shell, các bạn còn có thể sử dụng các công cụ khác để làm.

P/s 2: Ngoài Linux ra thì các OS khác (Mac và Windows) cũng hỗ trợ Shell đấy (với windows thì là command promt). Với cách làm tương tự, bạn cũng có thể tự động hoá bước này, nhưng Windows thì hơi khó để dùng đấy nhá!!!
