# Changelog

All notable changes to the **OpenCode Kuli Pro Edition** configuration will be documented in this file.

## [v1.2.0] - 2026-01-08

### 🚀 Major Changes (Indo Kuli Style)
- **New Default Provider**: Beralih sepenuhnya ke `proxycli-indo-kuli` (berbasis CLIProxyAPI fork).
  - Tidak perlu lagi pusing mikirin API Key (`apiKey: ""`).
  - BaseURL diarahkan ke `http://127.0.0.1:8318/v1`.
- **Plugin Removal**:
  - Menghapus dependency `opencode-antigravity-auth` by default (sekarang jadi opsional).
  - Menghapus konfigurasi provider `vibedev` untuk menyederhanakan config.

### ⚙️ Configuration Updates
- **opencode.json / opencode.example.json**:
  - Default model set ke `proxycli-indo-kuli/gemini-3-pro-preview`.
  - Membersihkan daftar model `google` (Antigravity) yang obsolete.
  - Menambahkan list model spesifik untuk proxy:
    - `claude-sonnet-4-5`
    - `claude-opus-4-5-thinking`
    - `gemini-3-pro-preview`
    - `gemini-3-flash-preview`
    - `gemini-3-pro-image-preview`
- **oh-my-opencode.json / oh-my-opencode.example.json**:
  - Update semua agent (`Sisyphus`, `oracle`, dll.) untuk menggunakan model dari provider `proxycli-indo-kuli`.

### 📚 Documentation
- **README.md**:
  - Menambahkan panduan autentikasi "Opsi A: CLI Proxy (Recommended)" dan "Opsi B: Plugin Antigravity (Legacy)".
  - Update tabel Providers untuk mencerminkan setup terbaru.
