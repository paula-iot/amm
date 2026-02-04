# 🚀 Guia Rápido de Deploy no Vercel

## Opção 1: Deploy via Interface Web (Mais Fácil)

### Passo 1: Preparar Repositório GitHub
```bash
# Inicializar git (se ainda não fez)
git init

# Adicionar arquivos
git add .

# Commit inicial
git commit -m "Initial commit - Conversor RH"

# Criar repositório no GitHub e adicionar remote
git remote add origin https://github.com/SEU-USUARIO/conversor-rh.git

# Push para GitHub
git branch -M main
git push -u origin main
```

### Passo 2: Deploy no Vercel
1. Acesse https://vercel.com
2. Faça login com GitHub
3. Clique em **"Add New Project"**
4. Selecione o repositório **conversor-rh**
5. Clique em **"Deploy"**
6. Aguarde alguns minutos ⏳
7. Pronto! 🎉 Você receberá uma URL como: `https://conversor-rh-xxxx.vercel.app`

---

## Opção 2: Deploy via CLI (Mais Rápido)

### Instalação da CLI
```bash
npm i -g vercel
```

### Login
```bash
vercel login
```

### Deploy
```bash
# Deploy em preview
vercel

# OU deploy direto em produção
vercel --prod
```

### Resultado
Você receberá imediatamente uma URL de produção!

---

## ⚙️ Configurações Automáticas

O Vercel detecta automaticamente:
- ✅ Next.js
- ✅ TypeScript
- ✅ Dependências do package.json
- ✅ Comandos de build

**Nenhuma configuração adicional necessária!**

---

## 🔄 Atualizações Futuras

### Se usou GitHub:
Qualquer push para a branch `main` fará deploy automático!

```bash
git add .
git commit -m "Atualização"
git push
```

### Se usou CLI:
```bash
vercel --prod
```

---

## 🌐 URL Customizada (Opcional)

No dashboard da Vercel:
1. Vá em **Settings** → **Domains**
2. Adicione seu domínio customizado
3. Siga as instruções de DNS

---

## 📊 Monitoramento

Dashboard da Vercel mostra:
- 📈 Analytics de uso
- ⚡ Performance
- 🐛 Logs de erro
- 📊 Métricas de build

---

## 🚨 Troubleshooting Comum

### Build falha
```bash
# Testar build localmente primeiro
npm run build
```

### Dependências faltando
```bash
# Reinstalar todas
rm -rf node_modules package-lock.json
npm install
```

### Limites do Vercel (Plano Gratuito)
- ✅ Bandwidth: 100GB/mês
- ✅ Executions: 100GB-hrs/mês
- ✅ Serverless Function Duration: 10 segundos
- ✅ Deployment Size: 100MB

**Este projeto está bem dentro dos limites!** ✅

---

## 🎯 Checklist Final

- [ ] Código commitado no Git
- [ ] Repositório criado no GitHub (se opção 1)
- [ ] Vercel CLI instalado (se opção 2)
- [ ] Deploy realizado
- [ ] URL de produção funcionando
- [ ] Teste de upload e conversão

---

## 💡 Dicas Pro

1. **Variáveis de Ambiente**: Use o dashboard da Vercel em Settings → Environment Variables
2. **Preview Deployments**: Cada branch/PR gera uma preview URL automática
3. **Rollback**: Você pode voltar para qualquer deploy anterior no dashboard
4. **Custom Domain**: Adicione domínio próprio gratuitamente

---

**Bom deploy! 🚀**
