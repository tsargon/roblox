# 🚀 Blueprint & Mindmap Proyek Roblox

Dokumen ini memvisualisasikan seluruh strategi proyek *game* Roblox untuk tim (**Aziz, Dehan, Rizky**), mulai dari pembagian peran, cara teknis membuat *Gamepass*, *AI tech stack*, hingga alur tahapan *development* menuju target **DevEx**.

---

## 🧠 1. Master Mindmap Proyek & Monetisasi

```mermaid
mindmap
  root((Proyek Roblox: Goal Cuan))
    Tim & Pembagian Peran
      Aziz [Product & Monetization]
        Struktur Harga & FOMO
        Desain UI Shop Mencolok
        AI Prompting Visual & Ikon
      Dehan [Game Designer & Player]
        Riset Tren & Psikologi Player
        Konsep Story / Grindy Game
        QA Testing Ritme Gameplay
      Rizky [Lead Engineer]
        Setup Roblox Studio & Group
        Scripting Luau dibantu AI
        DataStore & MarketplaceService
    Cara Bikin Gamepass
      1. Wadah Game & Group
        Bikin Roblox Group 100 Robux
        Publish Game di Roblox Studio
      2. Creator Hub Web
        Monetization > Passes
        Upload Ikon 512px & Set Harga
        Salin Asset ID
      3. Integrasi Skrip Luau
        UserOwnsGamePassAsync
        PromptGamePassPurchaseFinished
    Strategi Monetisasi
      Gamepasses [Sekali Beli]
        +30% Damage
        VIP & 2x WalkSpeed
        Auto-Collect
      Dev Products [Beli Berulang]
        Revive / Nyawa Tambahan
        15 Menit 2x Luck Boost
        Skip Stage
      Trik Harga Aman
        Timed Starter Pack 15 Menit
        Hindari Fake Discount Permanen
      Target Pencairan DevEx
        70% Net Revenue Tim
        Min 30.000 Earned Robux
    AI Tech Stack
      Coding: Roblox Assistant, Claude, ChatGPT
      3D Assets: Meshy.ai, Tripo3D
      Ikon & Thumbnail: Recraft, Midjourney
```

---

## 🛠️ 2. Flowchart Tahapan Development (16+ Hari)

Diagram alur di bawah ini memetakan tahapan eksekusi berurutan untuk tim:

```mermaid
flowchart TD
    F1["<b>FASE 1: Konsep, Ekonomi & Wireframe</b><br/>(Hari 1 - 2)"]
    F2["<b>FASE 2: Grayboxing & Mekanik Inti</b><br/>(Hari 3 - 7)"]
    F3["<b>FASE 3: Integrasi Monetisasi & Visual</b><br/>(Hari 8 - 12)"]
    F4["<b>FASE 4: QA Testing & Keamanan Server</b><br/>(Hari 13 - 15)"]
    F5["<b>FASE 5: Soft Launch, Promosi & DevEx</b><br/>(Hari 16+)"]

    F1 --> F2 --> F3 --> F4 --> F5

    subgraph Detail_F1 [Fokus Fase 1]
        direction LR
        F1A[Rizky: Bikin Roblox Group<br/>& Aktifkan Team Create]
        F1B[Dehan: Kunci Core Loop<br/>& List 4-6 Gamepass]
        F1C[Aziz: Wireframe UI Shop<br/>& Generate Ikon AI]
    end

    subgraph Detail_F2 [Fokus Fase 2]
        direction LR
        F2A[Rizky + AI: Prototipe<br/>Gameplay Balok Polos]
        F2B[Rizky + AI: Pasang<br/>DataStoreService]
        F2C[Dehan: Uji Ritme<br/>Grinding / Story]
    end

    subgraph Detail_F3 [Fokus Fase 3]
        direction LR
        F3A[Publish Game & Create<br/>Passes di Creator Hub]
        F3B[Rizky + AI: Skrip<br/>MarketplaceService]
        F3C[Aziz & Rizky: Pasang<br/>Aset 3D AI & Custom UI]
    end

    subgraph Detail_F4 [Fokus Fase 4]
        direction LR
        F4A[Simulasi Beli Gratis<br/>di Test Server Studio]
        F4B[Cek Rejoin Server<br/>Perk Tetap Aktif]
        F4C[Validasi Server-Side<br/>Anti-Exploiter]
    end

    subgraph Detail_F5 [Fokus Fase 5]
        direction LR
        F5A[Set Game ke Public<br/>Soft Launch]
        F5B[Dehan & Aziz: Konten<br/>TikTok / Shorts / Reels]
        F5C[Kumpulkan 30.000 Robux<br/>Cairkan via DevEx]
    end

    F1 --- Detail_F1
    F2 --- Detail_F2
    F3 --- Detail_F3
    F4 --- Detail_F4
    F5 --- Detail_F5
```

---

## ⚙️ 3. Alur Teknis Aktivasi Gamepass (Rizky & Aziz)

```mermaid
sequenceDiagram
    actor Player as Pemain Roblox
    participant UI as Shop UI (Desain Aziz)
    participant Hub as Roblox Creator Hub
    participant Server as Server Script (Rizky + AI)

    Note over Hub,Server: Setup Awal (Sebelum Rilis)
    Hub->>Server: Copy Asset ID Gamepass

    Note over Player,Server: Saat Game Berjalan
    Player->>UI: Klik tombol beli "+30% Damage"
    UI->>Server: Trigger PromptGamePassPurchase
    Server-->>Player: Muncul Pop-up Bayar Robux
    Player->>Server: Konfirmasi Pembelian
    Server->>Server: PromptGamePassPurchaseFinished
    Server-->>Player: Efek +30% Damage Langsung Aktif!
```