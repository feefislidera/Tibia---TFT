
# Jogo do Feefis — Multiplayer (Firebase)

Protótipo multiplayer (4 jogadores) com lobby/ready, dono da sala inicia, fase de loja/posição com **30 segundos**, e batalha automática após o tempo. Estado sincronizado via **Firebase Realtime Database**. Frontend em **React + Vite + TypeScript**.

## Como rodar local
1) `npm install`
2) Crie um projeto no [Firebase Console](https://console.firebase.google.com/), ative **Realtime Database** (modo teste) e obtenha as credenciais Web.
3) Copie `.env.example` para `.env` e preencha com suas credenciais.
4) `npm run dev` e abra o endereço mostrado.

## Deploy (Vercel)
1) Suba estes arquivos para um repositório (GitHub/GitLab).
2) No Vercel: **Import Project** → selecione o repositório.
3) Adicione as variáveis do `.env` em **Settings → Environment Variables** (prefixo `VITE_...`).
4) Deploy. O link (ex.: `https://seu-projeto.vercel.app`) já aceita `?room=ABC123` para entrar direto na sala.

## Notas
- **Sem autenticação**: cada cliente gera um `uid` simples salvo em `localStorage`.
- A **autoridade** é do **dono da sala** (primeiro a entrar). Ele processa as batalhas e avança as rodadas quando o timer termina (automaticamente).
- Segurança/anticheat não foi foco (protótipo de testes).
