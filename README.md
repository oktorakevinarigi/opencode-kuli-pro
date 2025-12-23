# My OpenCode Configuration 🚀

Koleksi konfigurasi [OpenCode](https://opencode.ai) yang dioptimalkan untuk produktivitas tinggi dengan berbagai MCP (Model Context Protocol) canggih dan plugin esensial.

## ✨ Fitur Utama
- **Oh My OpenCode**: Plugin utama yang mengaktifkan semua fitur canggih (LSP, Background Tasks, Hooks).
- **Antigravity Auth**: Akses model Gemini 3 Pro High dan Claude 4.5 dengan rate limit tinggi via Google OAuth.
- **TokenScope**: Analisis penggunaan token dan estimasi biaya secara real-time.
- **Deep Research**: Integrasi penuh dengan Exa AI dan Websets.
- **Advanced Thinking & Reasoning**: Dilengkapi dengan 6 mesin pemikiran (Thinking Engines) untuk akurasi maksimal:
  1. **Sequential Thinking (Anthropic)**: Versi standar untuk memecahkan masalah secara berurutan.
  2. **Sequential Thinking Ultra (hyokunkwak)**: Versi "pro" dengan *Quality Metrics*, *Bias Detection*, dan *Budget Management*.
  3. **MCP Reasoner (Jacck/frgmt0)**: Algoritma *Beam Search* dan *MCTS* untuk logika rumit.
  4. **Clear Thought (Chirag Singhal)**: Framework komprehensif dengan *Mental Models* dan *Design Patterns*.
  5. **Atom of Thoughts**: Dekomposisi masalah ke unit terkecil (atomik).
  6. **Shannon Thinking**: Metodologi sistematis Claude Shannon (Definition, Model, Proof).

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

#### 1. Setup Dasar & Plugin
Salin `opencode.example.json` menjadi `opencode.json` di folder konfigurasi OpenCode Anda:
```bash
mkdir -p ~/.config/opencode
cp opencode.example.json ~/.config/opencode/opencode.json
```

#### 2. Instalasi OpenAgents (Spesialis)
Untuk mendapatkan 100+ agent spesialis, jalankan installer OpenAgents:
```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/darrenhinde/OpenAgents/main/install.sh | bash -s full
```
*Agent-agent ini akan terinstall di folder `agent/` dan bisa dipanggil otomatis oleh Sisyphus.*

#### 3. Autentikasi Antigravity
1. Jalankan `opencode auth login`.
2. Pilih **Google** -> **OAuth with Google (Antigravity)**.

#### 4. Instalasi MCP Lokal
Clone dan build MCP berikut di folder `~/.config/opencode/mcp/`:
- `mcp-reasoner`
- `sequential-thinking-ultra`
- `clear-thought-mcp-server`
- `atom-of-thoughts`

---

### ⚙️ Konfigurasi Akhir

#### Konfigurasi Oh My OpenCode (`oh-my-opencode.json`)
Sesuaikan model di `~/.config/opencode/oh-my-opencode.json`:

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
1. **Start Session**: Pilih agent `Sisyphus` (OMO) atau `openagent` (Darren).
2. **Plan First**: Agent akan membuat rencana kerja sebelum mulai koding.
3. **Automatic Delegation**: Sisyphus akan memanggil spesialis (misal `@ai-engineer`) jika tugasnya spesifik.
4. **Superpowers Enforced**: Setiap agent dipaksa mengikuti SOP di folder `skills/` berkat plugin `superpowers.js`.
5. **Background Work**: Gunakan background tasks untuk multitasking koding.

## 🛠️ Daftar MCP & Plugin

### Plugins
| Nama | Fungsi |
|------|--------|
| `oh-my-opencode` | Core plugin: Sisyphus agents, background agents, LSP tools, hooks |
| `./plugin/superpowers.js` | **Local Plugin**: Memberikan kemampuan "superpowers" & skill system pada agent |
| `./plugin/kuli-pro-safety.js` | **Local Plugin**: Proteksi file sensitif & welcome greeting |
| `opencode-antigravity-auth` | OAuth & Model High-End (Gemini 3, Claude 4.5) |
| `@ramtinj95/opencode-tokenscope` | Analisis penggunaan token & estimasi biaya |
| `opencode-skills` | Skill system untuk workflow automation |

### MCP Lokal (Thinking Engines)
- `sequential-thinking` (Anthropic)
- `sequential-thinking-ultra` (hyokunkwak)
- `mcp-reasoner` (frgmt0)
- `clear-thought` (Chirag Singhal)
- `atom-of-thoughts` (kbsooo)
- `shannon-thinking` (server-shannon-thinking)

### MCP Remote
- `context7`: Official documentation lookup
- `exa`: Web search & deep research
- `websets`: Web entity collections
- `ref-mcp`: Documentation search

## ⚠️ Keamanan
Jangan pernah melakukan *commit* pada file `opencode.json` yang berisi API Key. Gunakan variabel lingkungan `{env:VARIABLE_NAME}`.

## 📄 Lisensi
MIT
