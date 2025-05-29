## 🧩 RSATunnelChat

Este repositório contém um conjunto de projetos integrados que implementam um sistema de chat peer-to-peer com criptografia RSA, totalmente escrito em Rust com Tauri e Axum.

### 📦 Projetos incluídos

| Projeto                    | Descrição                                                                  |
| -------------------------- | -------------------------------------------------------------------------- |
| [`rsa-rust`](https://github.com/akda007/rsa-rust)   | Biblioteca RSA educacional implementada do zero em Rust.                   |
| [`rust-chat`](https://github.com/akda007/rust-chat) | Aplicativo de chat peer-to-peer com criptografia de ponta-a-ponta via RSA. |

---

### 🔧 Como funciona

* Cada peer roda uma instância local com servidor HTTP (Axum).
* Um processo de **handshake** troca as chaves públicas e URLs dos peers.
* As mensagens são criptografadas com a chave pública do destinatário e enviadas via `POST`.
* O receptor descriptografa localmente e exibe no frontend Tauri.
* Toda a lógica de criptografia é feita pela biblioteca [`rsa-rust`](https://github.com/akda007/rsa-rust).

---

### 🧪 Exemplo de uso

1. Clone o repositório:

   ```bash
   git clone https://github.com/akda007/RSATunnelChat.git --recursive
   cd RSATunnelChat
   ```

2. Instale as dependências do frontend:

   ```bash
   cd rust-chat
   npm i
   ```

3. Rode a aplicação:

   ```bash
   npx tauri dev
   ```

4. Faça o mesmo em outro dispositivo (na mesma rede) e use o comando Tauri `perform_handshake` para conectar os peers.

---

### 📁 Estrutura do repositório

```
RSATunnelChat/
├── rsa-rust/        # Biblioteca RSA customizada (sem dependências externas)
├── rust-chat/       # App de chat peer-to-peer com Tauri
└── README.md        # Este arquivo
```

---

### 📌 Requisitos

* Rust (1.70+)
* Node.js (para o frontend Tauri)
* Tauri CLI

---

### 🚨 Aviso

Este projeto é para **fins educacionais**. A implementação de RSA não é segura para uso em produção. Ela não inclui padding (como OAEP), validação de chaves ou proteções contra ataques conhecidos.

---

### 📄 Licença

MIT

---
