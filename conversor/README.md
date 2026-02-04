# 🚀 Conversor RH - Sesame para FOPAG

Aplicação web para converter automaticamente dados exportados do Sesame para o formato de planilha de folha de pagamento (FOPAG) usado internamente pelo RH.

## ✨ Funcionalidades

- 📤 **Upload drag-and-drop** - Arraste e solte arquivos ou clique para selecionar
- ✏️ **Nome customizável** - Escolha o nome do arquivo de saída
- ⚡ **Conversão rápida** - Processamento automático em segundos
- 🧮 **Cálculos automáticos** - INSS, DSR, Vale Transporte, Horas Extras, Adicional Noturno
- 💾 **Download direto** - Arquivo pronto para conferência
- 🎨 **Interface moderna** - Design limpo e intuitivo

## 🛠️ Tecnologias

- **Next.js 14** - Framework React
- **TypeScript** - Tipagem estática
- **Tailwind CSS** - Estilização
- **ExcelJS** - Manipulação de planilhas Excel
- **Vercel** - Deploy e hospedagem

## 📋 Pré-requisitos

- Node.js 18+ 
- npm ou yarn

## 🚀 Instalação e Execução Local

```bash
# Instalar dependências
npm install

# Executar em modo de desenvolvimento
npm run dev

# Build para produção
npm run build

# Executar build de produção
npm start
```

Acesse: `http://localhost:3000`

## 🌐 Deploy no Vercel

### Método 1: Via CLI (Recomendado)

```bash
# Instalar Vercel CLI
npm i -g vercel

# Fazer login
vercel login

# Deploy
vercel

# Deploy em produção
vercel --prod
```

### Método 2: Via GitHub

1. Faça push do código para um repositório GitHub
2. Acesse [vercel.com](https://vercel.com)
3. Clique em "Import Project"
4. Selecione seu repositório
5. Clique em "Deploy"

### Configurações no Vercel

Não são necessárias configurações especiais! O Vercel detecta automaticamente Next.js.

**Opcional** - Configurações de ambiente (se necessário):
- `Node.js Version`: 18.x ou superior

## 📖 Como Usar

1. **Acesse a aplicação**
2. **Arraste o arquivo Sesame** (.xlsx) para a área de upload ou clique para selecionar
3. **Digite o nome** que deseja para o arquivo de saída (padrão: `fopag_fevereiro_2026`)
4. **Clique em "Converter e Baixar"**
5. **Aguarde** alguns segundos enquanto o arquivo é processado
6. O arquivo será **baixado automaticamente**

## 📊 Dados Processados

A conversão inclui automaticamente:

### Proventos
- ✅ Salário Base
- ✅ Salário Mês (proporcional aos dias trabalhados)
- ✅ Hora Extra 100%
- ✅ Adicional Noturno 30%
- ✅ DSR (Descanso Semanal Remunerado)
- ✅ Ajuda de Custo

### Descontos
- ✅ INSS (com teto de R$ 988,10)
- ✅ IR (campo preparado)
- ✅ Vale Transporte (6% do salário para salários até R$ 10.000)
- ✅ Assistências (campos preparados)

### Extras
- ✅ Total de Proventos
- ✅ Total de Descontos
- ✅ Valor Líquido
- ✅ Aba com Tabela INSS 2026

## 🔧 Estrutura do Projeto

```
conversor-rh/
├── app/
│   ├── api/
│   │   └── convert/
│   │       └── route.ts          # API de conversão
│   ├── globals.css               # Estilos globais
│   ├── layout.tsx                # Layout principal
│   └── page.tsx                  # Página inicial
├── components/
│   └── FileUploader.tsx          # Componente de upload
├── lib/
│   └── converter.ts              # Lógica de conversão
├── public/                       # Arquivos estáticos
├── package.json
├── tsconfig.json
├── tailwind.config.js
└── next.config.js
```

## ⚙️ Configurações Técnicas

### Referências Fevereiro 2026
- **Dias úteis**: 23
- **Domingos/Feriados**: 5
- **Teto INSS**: R$ 988,10

### Fórmulas Implementadas
- Salário Mês: `Salário Base / 30 * Dias Trabalhados`
- Hora Extra: `Salário Base / 200 * 2 * Horas Extras`
- Adicional Noturno: `(Salário Base / 200 * 0.3) * Horas Noturnas`
- DSR: `(Hora Extra + Adicional Noturno) / Dias Úteis * Domingos/Feriados`
- INSS: `MIN((Total Proventos * 0.14 - 181.18), 988.10)`
- Vale Transporte: `Salário Mês * 6%` (se salário <= R$ 10.000)

## 🐛 Troubleshooting

### Erro ao fazer upload
- Verifique se o arquivo é .xlsx
- Verifique se o arquivo tem o formato correto do Sesame

### Erro na conversão
- Verifique se o cabeçalho "Sobrenomes" está presente
- Verifique se as colunas estão na ordem correta

### Build falha no Vercel
- Verifique se todas as dependências estão no `package.json`
- Verifique a versão do Node.js (deve ser 18+)

## 📝 Notas

- Os arquivos NÃO são armazenados no servidor
- O processamento é feito em tempo real
- Todas as fórmulas usam formato contabilidade brasileiro (R$)

## 🔒 Segurança

- Processamento server-side
- Sem armazenamento de dados
- Arquivos processados apenas em memória

## 📄 Licença

Este projeto é de uso interno da empresa.

**Desenvolvido para otimizar o processo de conferência da folha de pagamento** ⚡
