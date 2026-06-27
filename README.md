# DuckInk CLI

Đây là repo phát hành binary cho DuckInk. Repo này chỉ chứa bản build release và
README hướng dẫn cài đặt; mã nguồn nằm ở repo phát triển riêng và không được đưa
vào `git@github.com:DuckMind/di-cli.git`.

- Tag: `v0.0.1`
- Version: `duckink v0.0.1`
- Commit nguồn: `ef582722f421fff53f45f843ed1461fbe7ba8bf4`

## Tệp phát hành theo hệ điều hành

Các binary được tách theo thư mục hệ điều hành để người dùng chọn đúng nền tảng:

- `macos/`
- `linux/`
- `windows/`

| Hệ điều hành/Kiến trúc | Tệp | SHA-256 |
|---|---|---|
| `darwin/arm64` | `macos/duckink-arm64` | `b72b77be42329e5d0ef08c4f718ff7e5fef177aab163125f9f0722a145113d98` |
| `darwin/amd64` | `macos/duckink-amd64` | `d7eda5b763fab57c18b009c45144117a631a6b69523b28110f888ba919d27101` |
| `linux/amd64` | `linux/duckink-amd64` | `65c7c9727384682ba0a24a8d395d186ea5f3695dd40f755380f30d6bbfae0190` |
| `linux/arm64` | `linux/duckink-arm64` | `95a73c21c35298c35ca3f33b7dee8eb8fbbc18ab5c8f7bd9c803a1372d4a368e` |
| `windows/amd64` | `windows/duckink-amd64.exe` | `a17b0b11f612d14842bfe79c413d3a3fbc43669045f1e03d58d92be5b57b8d76` |

Bạn cũng có thể kiểm tra nhanh bằng:

```sh
shasum -a 256 -c SHA256SUMS
```

## Cài đặt trên macOS

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

## Cài đặt trên Windows

PowerShell:

```powershell
Invoke-WebRequest -Uri https://raw.githubusercontent.com/DuckMind/di-cli/v0.0.1/windows/duckink-amd64.exe -OutFile duckink.exe
.\duckink.exe --version
```

Để dùng ở mọi thư mục:

1. Tạo thư mục `C:\Tools\DuckInk`.
2. Chép `duckink.exe` vào thư mục đó.
3. Thêm `C:\Tools\DuckInk` vào biến môi trường `Path`.
4. Mở terminal mới và chạy `duckink --version`.

## Cấu hình

DuckInk đọc cấu hình người dùng ở `~/.duckink/`. Nếu đây là lần chạy đầu, hãy chạy:

```sh
duckink
```

và làm theo hướng dẫn trong TUI để chọn provider, đăng nhập subscription hoặc nhập API key.
