# My OpenCode Configuration 🚀

Koleksi konfigurasi [OpenCode](https://opencode.ai) yang dioptimalkan untuk produktivitas tinggi dengan berbagai MCP (Model Context Protocol) canggih dan plugin esensial.

## ✨ Fitur Utama
- **Oh My OpenCode**: Plugin utama yang mengaktifkan semua fitur canggih (lihat bagian di bawah).
- **Antigravity Auth**: Akses model Gemini 3 Pro High dan Claude 4.5 dengan rate limit tinggi via Google OAuth.
- **TokenScope**: Analisis penggunaan token dan estimasi biaya secara real-time.
- **Deep Research**: Integrasi penuh dengan Exa AI dan Websets.
- **Advanced Thinking & Reasoning**: Dilengkapi dengan 5 mesin pemikiran (Thinking Engines) untuk akurasi maksimal.

### 🤖 Agent Ecosystem: The Hybrid Team
Konfigurasi ini menggabungkan dua framework agent terbaik untuk menciptakan ekosistem "Hybrid" di mana infrastruktur OMO mengelola pasukan spesialis dari OpenAgents.

#### 1. Oh My OpenCode (Sisyphus) — The Orchestrator
[Oh My OpenCode](https://github.com/code-yeongyu/oh-my-opencode) bertindak sebagai **CEO/Manager** yang mengelola infrastruktur:
- **Sisyphus** (Claude Opus 4.5): Main orchestrator yang merencanakan dan mendelegasikan tugas.
- **Oracle** (GPT 5.2): Ahli strategi arsitektur dan debugging berat.
- **Librarian** (Claude Sonnet 4.5): Riset dokumentasi dan implementasi Open Source.
- **Parallel Background Execution**: Menjalankan banyak agent sekaligus (misal: Frontend & Backend dikerjakan bersamaan).

#### 2. OpenAgents (Darren Hinde) — The Specialists
[OpenAgents](https://github.com/darrenhinde/OpenAgents) menyediakan **100+ Agent Spesialis** yang dipanggil oleh Sisyphus sesuai kebutuhan:
- **`nextjs-app-router-developer`**: Pakar Next.js 16+, RSC, dan Server Actions.
- **`python-pro` / `go-pro`**: Ahli bahasa spesifik dengan pola best-practice.
- **`security-auditor`**: Melakukan scan keamanan pada code sebelum ship.
- **`ai-engineer`**: Membangun RAG, Vector DB, dan integrasi LLM.

---

### 🚀 Panduan Instalasi

### 1. Setup Dasar & Plugin
Salin `opencode.example.json` menjadi `opencode.json` di folder konfigurasi OpenCode Anda:
```bash
mkdir -p ~/.config/opencode
cp opencode.example.json ~/.config/opencode/opencode.json
```

### 2. Instalasi OpenAgents (Spesialis)
Untuk mendapatkan 100+ agent spesialis, jalankan installer OpenAgents:
```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/darrenhinde/OpenAgents/main/install.sh | bash -s full
```
*Agent-agent ini akan terinstall di folder `agent/` dan bisa dipanggil otomatis oleh Sisyphus.*

### 3. Autentikasi Antigravity
Untuk menggunakan model-model Google/Claude High-End:
1. Jalankan perintah login:
   ```bash
   opencode auth login
   ```
2. Pilih **Google** -> **OAuth with Google (Antigravity)**.
3. Selesaikan proses login di browser.

### 4. Instalasi MCP Lokal
Jalankan perintah berikut di direktori `~/.config/opencode/mcp` untuk menyiapkan server MCP lokal:

```bash
mkdir -p ~/.config/opencode/mcp
cd ~/.config/opencode/mcp

# 1. MCP Reasoner (Beam Search + MCTS + R1-Sonnet)
git clone https://github.com/frgmt0/mcp-reasoner.git
cd mcp-reasoner && npm install && npm run build && cd ..

# 2. Sequential Thinking Ultra (Quality Metrics + Bias Detection + Budget Management)
git clone https://github.com/hyokunkwak/Sequential-thinking-ultra-mcp.git sequential-thinking-ultra
cd sequential-thinking-ultra && npm install && npm run build && cd ..

# 3. Clear Thought (Mental Models + Design Patterns + Debugging)
git clone https://github.com/chirag127/clear-thought-mcp-server.git clear-thought-mcp-server
cd clear-thought-mcp-server && npm install && npm run build && cd ..

# 4. Atom of Thoughts (AoT)
git clone https://github.com/kbsooo/mcp-atom-of-thoughts.git atom-of-thoughts
cd atom-of-thoughts && npm install && npm run build && cd ..
```

---

### ⚙️ Konfigurasi Akhir

### Konfigurasi Oh My OpenCode (`oh-my-opencode.json`)
File ini mengatur model mana yang digunakan oleh agent utama Sisyphus. Sesuaikan di `~/.config/opencode/oh-my-opencode.json`:

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

### 🎮 Workflow "Kuli Pro"
1. **Start Session**: Pilih agent `Sisyphus` atau `openagent`.
2. **Plan First**: Agent akan membuat rencana kerja sebelum mulai koding.
3. **Automatic Delegation**: Sisyphus akan memanggil spesialis (misal `@ai-engineer`) jika tugasnya spesifik.
4. **Superpowers Enforced**: Setiap agent dipaksa mengikuti SOP di folder `skills/` berkat plugin `superpowers.js`.
5. **Background Work**: Kamu bisa minta agent ngerjain frontend di background sementara kamu diskusi arsitektur database.


## 🛠️ Daftar MCP & Plugin

### Plugins
| Nama | Fungsi |
|------|--------|
| `oh-my-opencode` | Core plugin: Sisyphus agents, background agents, LSP tools, hooks |
| `./plugin/superpowers.js` | **Local Plugin**: Memberikan kemampuan "superpowers" & skill system pada agent |
| `./plugin/kuli-pro-safety.js` | **Local Plugin**: Proteksi file sensitif & welcome greeting |
| `opencode-antigravity-auth` | OAuth & Model High-End (Gemini 3, Claude 4.5, GPT-OSS) |
| `@ramtinj95/opencode-tokenscope` | Analisis penggunaan token & estimasi biaya |
| `opencode-skills` | Skill system untuk workflow automation |

> ℹ️ **Catatan Plugin Lokal**: Plugin seperti `superpowers.js` dimuat menggunakan path relatif (`./plugin/superpowers.js`) di dalam `opencode.json`. Pastikan file tersebut ada di folder `plugin/` agar fitur `use_skill` dan `find_skills` aktif.

### MCP Lokal (Thinking Engines)
| Nama | Fungsi |
|------|--------|
| `sequential-thinking` | Berpikir sekuensial standar (Anthropic) |
| `sequential-thinking-ultra` | Quality metrics, bias detection, budget management, meta-reasoning |
| `mcp-reasoner` | Advanced reasoning (Beam Search, MCTS, R1-Sonnet) |
| `clear-thought` | Mental models, design patterns, debugging frameworks |
| `atom-of-thoughts` | Decomposition-based reasoning, atomic thought units |
| `shannon-thinking` | Claude Shannon's systematic problem-solving methodology |

### MCP Lokal (Development Tools)
| Nama | Fungsi |
|------|--------|
| `Prisma-Local` | Prisma ORM integration untuk database management |
| `next-devtools` | Next.js development tools & debugging |
| `playwright` | Browser automation & testing |

### MCP Remote
| Nama | Fungsi | API Key Required |
|------|--------|------------------|
| `context7` | Official documentation lookup | `CONTEXT7_API_KEY` |
| `exa` | Web search, deep research, code context | `EXA_API_KEY` |
| `websets` | Web entity collections & enrichment | `EXA_API_KEY` |
| `ref-mcp` | Documentation search across web & GitHub | `REF_API_KEY` (opsional) |

### Model yang Tersedia (via Antigravity)
| Model | Deskripsi |
|-------|-----------|
| `gemini-3-pro-high` | Gemini 3 Pro (Antigravity) - Rate Limit Tinggi |
| `gemini-3-pro-low` | Gemini 3 Pro (Antigravity) - Rate Limit Standar |
| `gemini-3-flash` | Gemini 3 Flash (Antigravity) |
| `claude-sonnet-4-5` | Claude Sonnet 4.5 (Antigravity) |
| `claude-sonnet-4-5-thinking` | Claude Sonnet 4.5 (Antigravity) dengan Extended Thinking |
| `claude-opus-4-5-thinking` | Claude Opus 4.5 (Antigravity) dengan Extended Thinking |
| `gpt-oss-120b-medium` | GPT-OSS 120B (Antigravity) |

## 🎮 Cara Menggunakan

### Pilih Model
Gunakan command berikut di terminal OpenCode untuk melihat daftar model yang tersedia:
```bash
/models
```



## ⚠️ Keamanan
Jangan pernah melakukan *commit* pada file `opencode.json` yang berisi API Key. Gunakan variabel lingkungan `{env:VARIABLE_NAME}`.

## 📄 Lisensi
MIT
