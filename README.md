<div align="center">

<img src="https://github.com/Acelake123/vApp/blob/6b3b08b4d02e653f22eadb3edc252eb49519d47d/frontend/public/banner.svg" alt="vApp — Decentralized Voting Platform on Solana" width="100%"/>

<br/><br/>

> vApp is a full-stack decentralized voting platform built on the Solana blockchain.  
> Create polls, cast votes, and view results — all on-chain, in real time.

</div>

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔗 **Decentralized Voting** | Every vote is recorded on the Solana blockchain — immutable and transparent |
| ⚡ **Real-time Results** | Watch poll results update live as votes come in |
| 🎨 **Modern UI** | Clean, responsive interface built with shadcn/ui and Tailwind CSS |
| 🔐 **Wallet Auth** | Authenticate securely using your Solana wallet — no passwords needed |
| 📊 **Custom Polls** | Create and manage your own polls with full control |

---

## 🏗️ Tech Stack

<table>
<tr>
<td valign="top" width="33%">

### 🖥️ Frontend
- **Next.js 13+** (App Router)
- **shadcn/ui** components
- **Tailwind CSS** styling
- **React Context API**
- **@solana/web3.js**
- **@project-serum/anchor**

</td>
<td valign="top" width="33%">

### ⚙️ Backend
- **Django 4.2**
- **Django REST Framework**
- **SQLite** (dev)
- **PostgreSQL** (production)

</td>
<td valign="top" width="33%">

### ⛓️ Blockchain
- **Anchor** (Rust)
- **Solana Devnet / Mainnet**
- On-chain voting logic via smart contracts

</td>
</tr>
</table>

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed before continuing:

- **Node.js** 18+
- **Python** 3.10+
- **Rust & Cargo**
- **Solana CLI**
- **Yarn**
- **PostgreSQL** (for production)

---

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/Acelake123/vApp.git
cd vApp
```

**2. Set up the frontend**

```bash
cd frontend
yarn install
cp .env.example .env.local
# Edit .env.local with your environment variables
```

**3. Set up the backend**

```bash
cd ../booth_backend
python -m venv venv
source venv/bin/activate        # Windows: .\venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
# Edit .env with your environment variables
python manage.py migrate
```

**4. Deploy the Solana program**

```bash
cd ../booth
cargo build
anchor build
anchor deploy
```

---

## 🛠️ Running Locally

Open two terminals and start both servers:

```bash
# Terminal 1 — Backend
cd booth_backend
python manage.py runserver
```

```bash
# Terminal 2 — Frontend
cd frontend
yarn dev
```

Then open your browser:

| Service | URL |
|---|---|
| 🌐 Frontend | http://localhost:3000 |
| 🔌 Backend API | http://localhost:8000/api |
| 🛡️ Admin Panel | http://localhost:8000/admin |

---

## 🧪 Testing

```bash
# Frontend
cd frontend
yarn test

# Solana program
cd booth
anchor build
anchor test

# Backend
cd booth_backend
python manage.py test
```

---

## 🚢 Deployment

<details>
<summary><strong>Frontend — Vercel / Netlify</strong></summary>

1. Connect your GitHub repository
2. Set up environment variables in the dashboard
3. Hit **Deploy** 🚀

</details>

<details>
<summary><strong>Backend — Render / Railway</strong></summary>

1. Provision a PostgreSQL database
2. Configure your environment variables
3. Deploy your Django application

</details>

---

## 🤝 Contributing

Contributions are welcome and appreciated! Here's how to get involved:

```bash
# 1. Create a feature branch
git checkout -b feature/your-feature

# 2. Make your changes and commit
git commit -m 'feat: describe your feature'

# 3. Push and open a pull request
git push origin feature/your-feature
```

---

## 🙏 Acknowledgments

A big thanks to the communities and teams that made this possible:

- 🟣 **Solana Team** — for the blazing-fast blockchain platform
- ⚛️ **Next.js Community** — for the powerful React framework
- 🐍 **Django Community** — for the reliable backend framework

---

<div align="center">


Made with ❤️ by [Acelake123](https://github.com/Acelake123) & Team

⭐ Star this repo if you find it useful!

</div>
