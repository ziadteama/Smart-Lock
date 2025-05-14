
---

## 🚀 Quick Start

### 1. Clone with Submodules

```bash
git clone --recurse-submodules https://github.com/ziadteama/Smart-Lock-Docker.git
cd Smart-Lock-Docker


git submodule update --init --recursive
git pull --recurse-submodules
git submodule update --remote --merge
cp Smart-Lock-Server/.env.example Smart-Lock-Server/.env
docker compose up --build

