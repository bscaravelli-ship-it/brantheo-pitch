# 🚀 Brantheo Pitch — Deploy no Vercel

## O que está nessa pasta

```
brantheo-pitch-project/
├── index.html      ← A página interativa completa
└── vercel.json     ← Configuração do Vercel
```

---

## Deploy em 3 passos (< 2 minutos)

### Opção A — Via Vercel CLI (recomendado)

```bash
# 1. Instale o Vercel CLI (uma vez só)
npm install -g vercel

# 2. Acesse a pasta
cd brantheo-pitch-project

# 3. Deploy
vercel --prod
```

Na primeira vez ele vai pedir login — use sua conta Vercel ou crie uma em vercel.com (grátis).

O Vercel vai gerar uma URL como:
**`https://brantheo-pitch.vercel.app`**

---

### Opção B — Via drag & drop (sem CLI)

1. Acesse **vercel.com** → New Project
2. Arraste a pasta `brantheo-pitch-project` para a área de upload
3. Clique **Deploy**
4. Pronto — URL gerada em ~20 segundos

---

### Opção C — Domínio customizado (opcional)

Após o deploy, no painel do Vercel:
- Settings → Domains → Add `pitch.brantheo.com`
- Configure o CNAME no seu DNS apontando para `cname.vercel-dns.com`

---

## Após o deploy — 2 coisas para fazer

### 1. Atualizar a URL no QR code

Abra `gen_qr.py` e troque a linha:
```python
URL = "https://brantheo-pitch.vercel.app"
```
pela URL real que o Vercel gerou, depois rode:
```bash
python gen_qr.py
```

### 2. Conectar o webhook do Make.com

No `index.html`, linha ~270, troque:
```javascript
const MAKE_WEBHOOK = 'https://hook.us1.make.com/YOUR_WEBHOOK_HERE';
```
pela URL do seu webhook real do Make.

O payload enviado ao Make será:
```json
{
  "name": "João",
  "company": "Empresa XYZ",
  "phone": "+1 407 999 9999",
  "source": "qr-pitch-deck",
  "timestamp": "2026-03-23T..."
}
```

---

## QR Code

O arquivo `brantheo-qrcode.png` está pronto para imprimir em cartão de visita.
- Resolução: 618×758px @300dpi
- Formato ideal para cartão: 5×6cm

Para atualizar a URL no QR depois do deploy, rode `gen_qr.py` novamente.

---

**Brantheo LLC · brantheo.com · Orlando, FL**
