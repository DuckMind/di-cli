# DuckInk CLI

Đây là repo phát hành binary cho DuckInk. Repo này chỉ chứa bản build release và
README hướng dẫn cài đặt; mã nguồn nằm ở repo phát triển riêng và không được đưa
vào `git@github.com:DuckMind/di-cli.git`.

- Version: `duckink v0.0.0-20260627102517-5c93270ac354`
- Commit nguồn: `5c93270ac35420139c846493a018aadadf72d45e`

## Tệp phát hành

| Hệ điều hành/Kiến trúc | Tệp | SHA-256 |
|---|---|---|
| `darwin/arm64` | `duckink-darwin-arm64` | `80b3cdd1d17308bc114c6626c5b28fc2d50946cddbe8bb0ffdb03af135dafade` |
| `darwin/amd64` | `duckink-darwin-amd64` | `a77839d5d9eb8bd63469c5fc2edf2e30be21f6c8f2332bd14ce9698b38d04bb9` |
| `linux/amd64` | `duckink-linux-amd64` | `708a7ab7cb34806aba24fe03f3237ee107c7599e2d25470c6f79ad32c2dc7444` |
| `linux/arm64` | `duckink-linux-arm64` | `df7ec1b44c59a79d53129a6d3802896962f34ff88ba8aaf08cbe82b68dac59e7` |
| `windows/amd64` | `duckink-windows-amd64.exe` | `4770d519a10f67032c0f0a8f4fc1722e7708dae949784dda47ae7bad736fb273` |

Bạn cũng có thể kiểm tra nhanh bằng:

```sh
shasum -a 256 -c SHA256SUMS
```

## Cài đặt trên macOS

### Apple Silicon

```sh
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/main/duckink-darwin-arm64
chmod +x duckink
sudo mv duckink /usr/local/bin/duckink
duckink --version
```

### Intel

```sh
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/main/duckink-darwin-amd64
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
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/main/duckink-linux-amd64
chmod +x duckink
sudo mv duckink /usr/local/bin/duckink
duckink --version
```

### ARM64

```sh
curl -L -o duckink https://raw.githubusercontent.com/DuckMind/di-cli/main/duckink-linux-arm64
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
Invoke-WebRequest -Uri https://raw.githubusercontent.com/DuckMind/di-cli/main/duckink-windows-amd64.exe -OutFile duckink.exe
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
