# My OpenCode Configuration 🚀 (Kuli Pro Edition)

Koleksi konfigurasi [OpenCode](https://opencode.ai) yang dioptimalkan untuk produktivitas tinggi, menggabungkan infrastruktur **Oh My OpenCode** dan kecerdasan spesialis **OpenAgents**.

## ✨ Fitur Utama

- **Oh My OpenCode (OMO)**: Backbone infrastruktur yang memberikan kemampuan LSP canggih, manajemen token otomatis, dan orkestrasi background agents.
- **Hybrid Agent Ecosystem**: Kolaborasi antara `Sisyphus` (CEO/Orchestrator) dan 100+ agen spesialis dari OpenAgents (Darren Hinde).
- **Antigravity Auth**: Akses model tier-1 seperti Gemini 3 Pro High dan Claude 4.5 dengan rate limit tinggi.
- **TokenScope Monitoring**: Visualisasi penggunaan token dan estimasi biaya secara real-time di terminal.
- **Local Security Guard**: Plugin `kuli-pro-safety.js` yang melindungi file sensitif kamu dari penglihatan AI.

---

### 🧠 Advanced Thinking Engines (The Brain)

Konfigurasi ini dilengkapi dengan 6 mesin pemikiran untuk akurasi logika maksimal:

1. **Sequential Thinking (Anthropic)**: Standar emas untuk pemecahan masalah langkah-demi-langkah guna menghindari jawaban dangkal.
2. **Sequential Thinking Ultra (hyokunkwak)**: Versi "Pro" dengan:
   - **Quality Metrics**: Penilaian real-time terhadap konsistensi dan praktikabilitas solusi.
   - **Bias Detection**: Mendeteksi cognitive bias (confirmation, sunk cost, dll).
   - **Budget Management**: Mode efisiensi cerdas (Fast/Balanced/Exhaustive).
3. **MCP Reasoner (Jacck/frgmt0)**: Menggunakan algoritma *Beam Search* dan *Monte Carlo Tree Search (MCTS)* untuk mengeksplorasi berbagai jalur solusi sebelum memberikan jawaban akhir.
4. **Clear Thought (Chirag Singhal)**: Framework komprehensif yang menyatukan:
   - **Mental Models**: First Principles, Occam's Razor, Pareto Principle.
   - **Design Patterns**: Modular Architecture, Agentic Design.
   - **Debugging Frameworks**: Binary Search, Divide and Conquer, Cause Elimination.
5. **Atom of Thoughts (AoT)**: Fokus pada dekomposisi masalah ke unit terkecil (atomik), memastikan setiap detail teknis krusial terverifikasi.
6. **Shannon Thinking (The Systematizer)**: Berdasarkan metodologi Claude Shannon (Bapak Teori Informasi):
   - **Problem Definition**: Mengupas masalah ke elemen fundamental.
   - **Constraints Identification**: Memetakan batasan sistem secara eksplisit.
   - **Mathematical Modeling**: Membangun kerangka teoritis/logika yang solid.
   - **Experimental Validation**: Uji coba empiris sebelum implementasi final.

---

### 🤖 Agent Ecosystem: The Hybrid Team

#### 1. Oh My OpenCode (Sisyphus) — The Orchestrator
[Oh My OpenCode](https://github.com/code-yeongyu/oh-my-opencode) bertindak sebagai **CEO/Manager** yang mengelola infrastruktur:
- **Sisyphus** (Claude Opus 4.5): Main orchestrator yang merencanakan dan mendelegasikan tugas.
- **Oracle** (GPT 5.2): Ahli strategi arsitektur dan debugging berat.
- **Librarian** (Claude Sonnet 4.5): Riset dokumentasi dan implementasi Open Source di GitHub.
- **Parallel Background Execution**: Menjalankan banyak agent sekaligus (misal: Gemini menulis frontend sementara Claude handle backend).

#### 2. OpenAgents (Darren Hinde) — The Specialists
[OpenAgents](https://github.com/darrenhinde/OpenAgents) menyediakan **100+ Agent Spesialis** yang dipanggil oleh Sisyphus sesuai kebutuhan:
- **`nextjs-app-router-developer`**: Pakar Next.js 16+, RSC, dan Server Actions.
- **`python-pro` / `go-pro`**: Ahli bahasa spesifik dengan pola best-practice.
- **`security-auditor`**: Melakukan scan keamanan pada code sebelum ship.
- **`ai-engineer`**: Membangun RAG, Vector DB, dan integrasi LLM.
- **`debugger`**: Spesialis pelacak root-cause error yang sulit ditemukan.

---

### 🚀 Panduan Instalasi

#### 1. Setup Dasar & Plugin
Salin `opencode.example.json` menjadi `opencode.json` di folder konfigurasi:
```bash
mkdir -p ~/.config/opencode
cp opencode.example.json ~/.config/opencode/opencode.json
```

#### 2. Instalasi OpenAgents (Spesialis)
Dapatkan 100+ agent spesialis dengan menjalankan installer OpenAgents:
```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/darrenhinde/OpenAgents/main/install.sh | bash -s full
```

#### 3. Instalasi Shannon Thinking
Tambahkan konfigurasi Shannon Thinking ke bagian `mcp` di `opencode.json`:
```json
"shannon-thinking": {
  "type": "local",
  "command": ["npx", "-y", "server-shannon-thinking@latest"],
  "enabled": true
}
```

#### 4. Instalasi MCP Lokal Lainnya
Clone dan build MCP berikut di folder `~/.config/opencode/mcp/`:
- `mcp-reasoner`: `git clone https://github.com/frgmt0/mcp-reasoner.git`
- `sequential-thinking-ultra`: `git clone https://github.com/hyokunkwak/Sequential-thinking-ultra-mcp.git`
- `clear-thought`: `git clone https://github.com/chirag127/clear-thought-mcp-server.git`

---

### ⚙️ Konfigurasi Oh My OpenCode (`oh-my-opencode.json`)

Sesuaikan model yang digunakan oleh para manager di `~/.config/opencode/oh-my-opencode.json`:

```json
{
  "$schema": "https://raw.githubusercontent.com/code-yeongyu/oh-my-opencode/master/assets/oh-my-opencode.schema.json",
  "google_auth": false,
  "agents": {
    "Sisyphus": { "model": "google/claude-opus-4-5-thinking" },
    "librarian": { "model": "opencode/glm-4.7" },
    "oracle": { "model": "google/claude-opus-4-5-thinking" },
    "frontend-ui-ux-engineer": { "model": "google/gemini-3-pro-high" },
    "document-writer": { "model": "google/gemini-3-flash" },
    "multimodal-looker": { "model": "google/gemini-3-flash" },
    "explore": { "model": "opencode/glm-4.7" }
  }
}
```

---

### 🛠️ Daftar Lengkap Plugin & MCP

#### Esensial Plugins
| Nama | Fungsi |
|------|--------|
| `oh-my-opencode` | Core: Sisyphus agents, background tasks, LSP, hooks. |
| `./plugin/superpowers.js` | **Enforcer**: Memaksa agent cek Skill/SOP sebelum bekerja. |
| `./plugin/kuli-pro-safety.js` | **Protector**: Memblokir akses AI ke file sensitif (.env, config). |
| `opencode-antigravity-auth` | **Gateway**: Provider model Claude 4.5 & Gemini 3 Pro. |
| `@ramtinj95/opencode-tokenscope` | **Analytic**: Tracking token dan biaya real-time. |

#### Thinking MCPs
- **Sequential Thinking**: Berpikir urut (Anthropic).
- **Sequential Thinking Ultra**: Berpikir urut dengan metrik kualitas (hyokunkwak).
- **MCP Reasoner**: Algoritma MCTS untuk logika berat (frgmt0).
- **Clear Thought**: Mental models & architecture patterns (Chirag Singhal).
- **Shannon Thinking**: Metodologi sistematis Claude Shannon.

#### Development MCPs
- **Prisma-Local**: Database management via Prisma.
- **Next-Devtools**: Debugging & inspeksi Next.js App Router.
- **Playwright**: Browser automation & E2E testing.
- **Exa**: Deep web search & code context.

---

### 🎮 Workflow "Kuli Pro"

1. **Memulai Sesi**: Jalankan OpenCode dan pilih agent `Sisyphus`.
2. **Brainstorming**: Berikan instruksi global, Sisyphus akan membuat **Plan**.
3. **Delegasi**: Jika tugasnya adalah Next.js, Sisyphus akan memanggil `@nextjs-app-router-developer`.
4. **Validasi**: Setelah koding, gunakan `@code-reviewer` untuk memastikan kualitas.
5. **Ship**: Gunakan command `/commit` untuk commit pesan konvensional otomatis.

## ⚠️ Keamanan
Jangan pernah melakukan *commit* pada file `opencode.json` asli. Selalu gunakan `opencode.example.json` sebagai template dan simpan API Key di Environment Variable.

## 📄 Lisensi
MIT - [Alfian](https://github.com/alfian) & Open Source Community.
