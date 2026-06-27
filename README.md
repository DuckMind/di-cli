# DuckInk CLI

DuckInk là công cụ viết tiểu thuyết bằng AI chạy trong terminal. Ứng dụng giúp
bạn phác thảo ý tưởng, viết chương, theo dõi bối cảnh, nhân vật và tiến độ ngay
trong giao diện TUI.

Trang này hướng dẫn cài đặt DuckInk CLI trên MacOS, Linux và WSL.

## Kiểm tra tệp tải về

Sau khi tải binary phù hợp, bạn có thể kiểm tra checksum bằng:

```sh
shasum -a 256 -c SHA256SUMS
```

## Cài đặt trên MacOS

### Apple Silicon

```sh
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/v0.0.1/macos/duckink-arm64
chmod +x duckink
sudo mv duckink /usr/local/bin/duckink
duckink --version
```

### Intel

```sh
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/v0.0.1/macos/duckink-amd64
chmod +x duckink
sudo mv duckink /usr/local/bin/duckink
duckink --version
```

Nếu macOS chặn binary tải từ Internet, chạy:

```sh
xattr -d com.apple.quarantine /usr/local/bin/duckink
```

## Cài đặt trên Linux

### x86_64

```sh
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/v0.0.1/linux/duckink-amd64
chmod +x duckink
sudo mv duckink /usr/local/bin/duckink
duckink --version
```

### ARM64

```sh
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/v0.0.1/linux/duckink-arm64
chmod +x duckink
sudo mv duckink /usr/local/bin/duckink
duckink --version
```

Nếu không có quyền `sudo`, dùng `~/.local/bin`:

```sh
mkdir -p ~/.local/bin
mv duckink ~/.local/bin/duckink
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.profile
```

## Cài đặt trên WSL

Trong Ubuntu hoặc distro WSL khác, dùng binary Linux x86_64:

```sh
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/v0.0.1/linux/duckink-amd64
chmod +x duckink
mkdir -p ~/.local/bin
mv duckink ~/.local/bin/duckink
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.profile
source ~/.profile
duckink --version
```

## Cấu hình

DuckInk đọc cấu hình người dùng ở `~/.duckink/`. Nếu đây là lần chạy đầu, hãy chạy:

```sh
duckink
```

và làm theo hướng dẫn trong TUI để chọn provider, đăng nhập subscription hoặc nhập API key.
