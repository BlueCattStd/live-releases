# BlueCast Live

Base desktop oficial de ingest do BlueCast.

## Escopo atual

- login com `BlueCatt Account` via Supabase Auth
- leitura da estacao do usuario pela API do BlueCast
- exibicao do contrato atual de ingest e do link publico
- conexao local de transmissao por microfone
- envio do audio ao endpoint autenticado de ingest
- atualizacao basica de metadata via Icecast admin

## Stack

- `Electron` para shell desktop
- `Vite + React` no renderer
- `@supabase/supabase-js` para autenticacao BlueCatt
- `@material/web` para os componentes Material Web
- shell visual baseado em `MeowMaterial`
- `lamejs` para encode `MP3` no cliente

## Shell reutilizado

O `LIVE` agora reutiliza a base visual do Meow:

- registro de componentes Material Web
- tema e runtime de paleta do `MeowMaterial`
- tokens `md-sys` e aliases `shell-*`
- primitivas globais do shell

Arquivos base copiados para o app:

- `src/renderer/material/*`
- `src/renderer/lib/settings.js`
- `src/renderer/styles/MeowMaterial.css`
- `src/renderer/styles/MeowMaterialPrimitives.css`
- `src/renderer/styles/colors/*`

## Variaveis

Copiar `.env.example` para `.env` e ajustar:

- `BLUECAST_API_URL`
- `SUPABASE_URL`
- `SUPABASE_ANON_KEY`
- `BLUECAST_LIVE_APP_NAME` opcional

## Scripts

- `npm install`
- `npm run dev`
- `npm run build`
- `npm start`

## Observacoes

- Esta primeira entrega transmite audio de microfone em `MP3 mono`.
- O fluxo ja respeita o contrato atual de ingest do BlueCast.
- Selecao avancada de fonte, automacoes e multiplas estacoes simultaneas ficam para ciclos seguintes.
