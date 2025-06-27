# NVN.PLUS

<div align="center">

![NVN.PLUS Logo](https://github.com/user-attachments/assets/8cd401e2-a783-4b69-a3b2-ab371fac711a)

[![Versão](https://img.shields.io/badge/versão-1.0.5-blue.svg)](https://nvn.plus)

**Plataforma completa de comunicação com CRM e helpdesk integrada ao WhatsApp**

🚀 **NOVIDADE v1.0.5**: PWA avançado com notificações, feature flag, rollout incremental e fallback retroativo! Veja detalhes abaixo.

</div>

## 📋 Índice

- [Visão Geral](#visão-geral)
- [Backup e Restore do Banco de Dados](#backup-e-restore-do-banco-de-dados)
- [Roadmap](#roadmap)
- [Requisitos](#requisitos)
- [Configuração](#configuração)
- [Instalação](#instalação)
  - [🐳 Instalação com Docker (Recomendado)](#-instalação-com-docker-recomendado)
  - [📦 Instalação Manual](#-instalação-manual)
- [Como Usar](#como-usar)
  - [🐳 Usando com Docker](#-usando-com-docker)
  - [📦 Usando Instalação Manual](#-usando-instalação-manual)
- [API](#api)
- [Troubleshooting](#troubleshooting)
- [Contribuições](#contribuições)
- [Empresas que Usam](#empresas-que-usam)

## 🚀 Visão Geral

NVN.PLUS é uma poderosa solução de comunicação que combina CRM e helpdesk, utilizando o WhatsApp como principal canal para interação com seus clientes. A plataforma oferece uma experiência completa de atendimento multicanal com ferramentas avançadas para gerenciamento de conversas, automatização de processos e análise de desempenho.

> **🐳 Novo: Agora com suporte completo ao Docker!** Execute todo o ambiente com um único comando. Inclui todos os serviços necessários: PostgreSQL, Redis, MinIO, Evolution API e Nginx pré-configurados.

Nossa arquitetura foi otimizada para garantir máxima performance nos atendimentos. O processo de download de arquivos e mídias opera de forma independente do servidor principal, permitindo que os atendentes continuem interagindo com os clientes sem interrupções ou lentidão, mesmo durante transferências de arquivos grandes.

A experiência do usuário foi completamente modernizada na versão 1.0.2 com a implementação de um design system unificado. O FlowBuilder agora apresenta uma interface moderna com gradientes elegantes, nós categorizados por cores temáticas e editor modal responsivo. Essas melhorias proporcionam maior produtividade e uma experiência visual consistente em toda a plataforma.

A versão 1.0.3 expande significativamente as capacidades do FlowBuilder com o sistema de **Transferência de Fluxos**, permitindo criar automações ainda mais sofisticadas. O novo nó `transferFlowNode` possibilita transferir contatos entre diferentes fluxos ativos, mantendo contexto através de parâmetros configuráveis, ideal para especializações de atendimento, escalation e segmentação inteligente de clientes.

A plataforma também conta com o react-whatsmarked, desenvolvido por Claudemir, que substitui o sistema de Markdown antigo do Whaticket. Esta melhoria proporciona uma visualização de mensagens muito mais fiel ao WhatsApp Web, tornando o ambiente familiar e intuitivo para os atendentes.

## 🛡️ Backup e Restore do Banco de Dados

O NVN.PLUS oferece um script automatizado para backup e restore do banco PostgreSQL, facilitando a gestão e segurança dos dados.

### Como funciona
- O script `scripts/backup_restore.sh` realiza backup e restore do banco PostgreSQL usando as variáveis do seu arquivo `.env`.
- Detecta automaticamente as configurações de conexão (host, porta, usuário, senha, nome do banco) a partir do `.env` na raiz do projeto.
- Os arquivos de backup são salvos na pasta `./backup` (ou outra definida em `BACKUP_DIR`).

### Como usar
Abra o terminal na raiz do projeto e execute:

**Backup:**
```sh
./scripts/backup_restore.sh backup
```
Cria um arquivo de backup com data/hora no nome.

**Restore:**
```sh
./scripts/backup_restore.sh restore caminho/para/arquivo.backup
```
Restaura o banco a partir do arquivo informado.

> O script funciona em Linux/macOS e no Windows via WSL ou Git Bash. É necessário ter `pg_dump` e `pg_restore` instalados e acessíveis no PATH.

**Variáveis suportadas no .env:**
- `DB_HOST`, `DB_PORT`, `DB_NAME`, `DB_USER`, `DB_PASS`, `BACKUP_DIR`

---

## 🔜 Roadmap

### 🎯 **Categorias de Desenvolvimento**

<table>
<tr>
<td width="25%">

#### 📊 **Analytics & Reports**
- [ ] **Relatórios Avançados**
  - ✅ Filtros por data de criação/atualização
  - ⏳ Dashboards personalizáveis
  - 🔄 Exportação automática
  - 📈 Métricas em tempo real

- [ ] **Business Intelligence**
  - 📊 KPIs de atendimento
  - 📈 Análise de performance
  - 🎯 Forecasting de demanda

</td>
<td width="25%">

#### 💼 **Business Features**
- [ ] **Sistema de Afiliados**
  - 🤝 Programa de parcerias
  - 💰 Dashboard de comissões
  - 📊 Tracking de referrals
  - 🏆 Sistema de recompensas

- [ ] **Gestão Empresarial**
  - ⏰ SLA personalizado
  - 👔 Multi-empresa
  - 📋 Compliance LGPD

</td>
<td width="25%">

#### 🚀 **Platform Evolution**
- [ ] **WhatsApp Business API**
  - 📱 WABA completo
  - 📸 Status/Stories

- [ ] **Infrastructure**
  - ☁️ Migração S3
  - 🔧 Auto-scaling

</td>
<td width="25%">

#### 🤖 **AI & Automation**
- [ ] **FlowBuilder 2.0**
  - 🧠 Novos tipos de nós
  - 🔄 Loops condicionais
  - 🎨 UI/UX aprimorado

- [ ] **Inteligência Artificial**
  - 🤖 Chatbots avançados
  - 📝 NLP melhorado
  - 🎯 Personalização IA

</td>
</tr>
</table>

### 🎯 **Como Contribuir com o Roadmap**

<div align="center">

| 💭 **Sugestões** | 🐛 **Bugs** | 🗳️ **Votação** |
|:---------------:|:-----------:|:---------------:|
| [💡 Ideias](https://github.com/brunocgc/whaticket-nvnplus/discussions) | [🐛 Issues](https://github.com/brunocgc/whaticket-nvnplus/issues) | [🗳️ Features](https://github.com/brunocgc/whaticket-nvnplus/discussions/categories/polls) |

</div>

> 📢 **Quer priorizar uma feature?** Entre em contato conosco via [WhatsApp](https://wa.me/552120428610) ou [GitHub Discussions](https://github.com/brunocgc/whaticket-nvnplus/discussions)

## 📋 Requisitos

<div align="center">

### 🔍 **Análise de Sistema e Compatibilidade**

</div>

<table>
<tr>
<td width="50%">

### 🐳 **Docker (Recomendado)**

<details>
<summary><strong>✅ Configuração Simplificada</strong></summary>

| Componente | Versão | Status | Observações |
|------------|--------|--------|-------------|
| ![Docker](https://img.shields.io/badge/Docker-20.10+-2496ED?logo=docker&logoColor=white) | 20.10+ | ✅ Obrigatório | Container runtime |
| ![Docker Compose](https://img.shields.io/badge/Docker_Compose-2.0+-2496ED?logo=docker&logoColor=white) | 2.0+ | ✅ Obrigatório | Orquestração |
| ![RAM](https://img.shields.io/badge/RAM-4GB-FF6B6B?logo=memory&logoColor=white) | 4GB | ⚠️ Mínimo | 8GB recomendado |
| ![Storage](https://img.shields.io/badge/Disco-10GB-4ECDC4?logo=harddisk&logoColor=white) | 10GB | ⚠️ Mínimo | SSD recomendado |
| ![Internet](https://img.shields.io/badge/Internet-Necessário-45B7D1?logo=wifi&logoColor=white) | Banda larga | ✅ Obrigatório | Download inicial ~2GB |

</details>

**🚀 Vantagens:**
- ✅ Setup automático de dependências
- ✅ Ambiente isolado e seguro
- ✅ Atualizações simplificadas
- ✅ Backup/restore integrado
- ✅ Escalabilidade horizontal

</td>
<td width="50%">

### 📦 **Instalação Manual**

<details>
<summary><strong>🔧 Configuração Avançada</strong></summary>

| Componente | Versão | Status | Observações |
|------------|--------|--------|-------------|
| ![Node.js](https://img.shields.io/badge/Node.js-20+-339933?logo=node.js&logoColor=white) | 20+ LTS | ✅ Obrigatório | JavaScript runtime |
| ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16+-336791?logo=postgresql&logoColor=white) | 16+ | ✅ Obrigatório | Banco principal |
| ![Redis](https://img.shields.io/badge/Redis-6+-DC382D?logo=redis&logoColor=white) | 6+ | ✅ Obrigatório | Cache e filas |
| ![RAM](https://img.shields.io/badge/RAM-2GB-FF6B6B?logo=memory&logoColor=white) | 2GB | ⚠️ Mínimo | 4GB recomendado |
| ![WhatsApp](https://img.shields.io/badge/WhatsApp-Business-25D366?logo=whatsapp&logoColor=white) | Ativo | ✅ Obrigatório | Conta válida |

</details>

**⚙️ Características:**
- 🔧 Controle total do ambiente
- 🎯 Customização avançada
- 📊 Monitoramento granular
- 🔒 Integração com sistemas existentes
- ⚡ Performance otimizada

</td>
</tr>
</table>

### 🖥️ **Compatibilidade de Sistema Operacional**

<table align="center">
<tr>
<td align="center" width="25%">
<h4>🐧 Linux</h4>
<img src="https://img.shields.io/badge/Ubuntu-20.04+-E95420?logo=ubuntu&logoColor=white" alt="Ubuntu"/><br/>
<img src="https://img.shields.io/badge/CentOS-8+-262577?logo=centos&logoColor=white" alt="CentOS"/><br/>
<img src="https://img.shields.io/badge/Debian-11+-A81D33?logo=debian&logoColor=white" alt="Debian"/><br/>
<p><strong>✅ Totalmente Suportado</strong></p>
</td>
<td align="center" width="25%">
<h4>🪟 Windows</h4>
<img src="https://img.shields.io/badge/Windows-10+-0078D4?logo=windows&logoColor=white" alt="Windows 10+"/><br/>
<img src="https://img.shields.io/badge/WSL2-Recomendado-0078D4?logo=windows&logoColor=white" alt="WSL2"/><br/>
<img src="https://img.shields.io/badge/Docker_Desktop-4.0+-2496ED?logo=docker&logoColor=white" alt="Docker Desktop"/><br/>
<p><strong>✅ Suportado com Docker</strong></p>
</td>
<td align="center" width="25%">
<h4>🍎 macOS</h4>
<img src="https://img.shields.io/badge/macOS-12+-000000?logo=apple&logoColor=white" alt="macOS 12+"/><br/>
<img src="https://img.shields.io/badge/Docker_Desktop-4.0+-2496ED?logo=docker&logoColor=white" alt="Docker Desktop"/><br/>
<img src="https://img.shields.io/badge/Apple_Silicon-Compatível-000000?logo=apple&logoColor=white" alt="Apple Silicon"/><br/>
<p><strong>✅ Totalmente Suportado</strong></p>
</td>
<td align="center" width="25%">
<h4>☁️ Cloud</h4>
<img src="https://img.shields.io/badge/AWS-EC2-FF9900?logo=amazonaws&logoColor=white" alt="AWS"/><br/>
<img src="https://img.shields.io/badge/Google_Cloud-Compute-4285F4?logo=googlecloud&logoColor=white" alt="GCP"/><br/>
<img src="https://img.shields.io/badge/Azure-VMs-0078D4?logo=microsoftazure&logoColor=white" alt="Azure"/><br/>
<p><strong>✅ Produção Ready</strong></p>
</td>
</tr>
</table>

### ⚡ **Configurações Recomendadas por Ambiente**

<details>
<summary><strong>🏠 Desenvolvimento Local</strong></summary>

```yaml
Especificações Ideais:
CPU: 4 cores (Intel i5/AMD Ryzen 5)
RAM: 8GB DDR4
Disco: 50GB SSD
Internet: 10 Mbps
OS: Linux/macOS/Windows 10+

Docker Resources:
Memory: 4GB
CPU: 2 cores
Swap: 1GB
```

</details>

<details>
<summary><strong>🏢 Ambiente de Teste</strong></summary>

```yaml
Especificações Recomendadas:
CPU: 8 cores (Intel i7/AMD Ryzen 7)
RAM: 16GB DDR4
Disco: 100GB SSD
Internet: 50 Mbps
OS: Ubuntu Server 22.04 LTS

Load Balancer: Nginx
Monitoring: Prometheus + Grafana
Backup: Automático diário
```

</details>

<details>
<summary><strong>🚀 Produção</strong></summary>

```yaml
Especificações Mínimas:
CPU: 16 cores (Intel Xeon/AMD EPYC)
RAM: 32GB DDR4 ECC
Disco: 500GB NVMe SSD
Internet: 100 Mbps dedicado
OS: Ubuntu Server 22.04 LTS

High Availability:
- Load Balancer: HAProxy/Nginx
- Database: PostgreSQL Cluster
- Redis: Sentinel/Cluster
- Storage: S3/MinIO Distributed
- Monitoring: Full observability stack
```

</details>

### 🔍 **Verificação de Compatibilidade**

<div align="center">

| Comando | Resultado Esperado | Status |
|---------|-------------------|--------|
| `docker --version` | Docker version 20.10+ | ✅ |
| `docker-compose --version` | Docker Compose version 2.0+ | ✅ |
| `node --version` | v20+ | ✅ |
| `npm --version` | 8+ | ✅ |
| `git --version` | 2.0+ | ✅ |

</div>

<div align="center">

```bash
# 🔧 Script de verificação rápida (PowerShell)
# Execute este comando para verificar compatibilidade:

Write-Host "🔍 Verificando compatibilidade..." -ForegroundColor Cyan
docker --version; docker-compose --version; node --version; git --version
```

</div>

## ⚙️ Configuração

### Variáveis de Ambiente

Antes da instalação, configure os arquivos de ambiente necessários:

#### Para Docker (Recomendado)

1. **Arquivo Principal (.env)**:
   ```bash
   # Portas dos serviços
   BACKEND_PORT=8000
   FRONTEND_PORT=3000
   DB_PORT=5432
   REDIS_PORT=6379
   NGINX_PORT=80

   # Configurações do Banco
   DB_USER=postgres
   DB_PASS=postgres
   DB_NAME=nvnplus
   ```

2. **Backend (backend/.env)**:
   ```bash
   # Configurações do banco de dados
   DB_HOST=timescaledb
   DB_PORT=5432
   DB_NAME=nvnplus
   DB_USER=postgres
   DB_PASS=postgres

   # JWT Secret
   JWT_SECRET=sua_chave_secreta_aqui

   # Redis
   REDIS_HOST=redis
   REDIS_PORT=6379

   # URL da aplicação
   BACKEND_URL=http://localhost:8000
   FRONTEND_URL=http://localhost:3000
   ```

3. **Frontend (frontend/.env)**:
   ```bash
   REACT_APP_BACKEND_URL=http://localhost:8000
   PORT=3000
   ```

#### Para Instalação Manual

Configure seu banco PostgreSQL e Redis localmente, e ajuste as variáveis de ambiente correspondentes nos arquivos `.env`.

### Configuração do WhatsApp

1. Acesse a interface em `http://localhost:3000`
2. Vá em **Configurações > Conexões**
3. Adicione uma nova conexão
4. Escaneie o QR Code com seu WhatsApp
5. Aguarde a sincronização

### Configuração da Transcrição de Áudio (Opcional)

Para ativar a transcrição automática de áudios:

1. Obtenha uma chave da API Groq em [console.groq.com](https://console.groq.com)
2. Acesse **Configurações > Integrações**
3. Configure a chave da API Groq
4. Ative a **"Transcrição automática de áudio"** em **Configurações > Opções**

## 💻 Instalação

### 🐳 Instalação com Docker (Recomendado)

A forma mais rápida e fácil de executar o NVN.PLUS é utilizando Docker. Esta configuração inclui todos os serviços necessários:

```bash
# Clone o repositório
git clone https://github.com/brunocgc/whaticket-nvnplus.git

# Entre no diretório
cd whaticket-nvnplus

# Copie e configure os arquivos de ambiente
cp .env.docker.example .env
cp backend/.env.example backend/.env  # Se não existir, crie baseado no exemplo abaixo
cp frontend/.env.example frontend/.env  # Se não existir, crie baseado no exemplo abaixo

# Configure suas variáveis de ambiente nos arquivos .env

# Inicie todos os serviços
docker-compose up -d
```

#### Serviços Incluídos

- **Backend**: API do NVN.PLUS (porta 8000)
- **Frontend**: Interface web (porta 3000)
- **TimescaleDB**: Banco de dados PostgreSQL otimizado (porta 5432)
- **Redis**: Cache e filas (porta 6379)
- **MinIO**: Armazenamento de arquivos (porta 9000/9001)
- **Evolution API**: API do WhatsApp (porta 8080)
- **Nginx**: Proxy reverso (porta 80)

#### Comandos Úteis do Docker

```bash
# Ver logs dos serviços
docker-compose logs -f

# Ver logs de um serviço específico
docker-compose logs -f backend

# Parar todos os serviços
docker-compose down

# Parar e remover volumes (ATENÇÃO: Remove todos os dados)
docker-compose down -v

# Reiniciar um serviço específico
docker-compose restart backend

# Executar comando no container
docker-compose exec backend bash
```

#### Acesso aos Serviços

- **NVN.PLUS**: http://localhost:3000
- **MinIO Console**: http://localhost:9001 (usuário: minioadmin, senha: minioadmin)
- **Evolution API**: http://localhost:8080

### 📦 Instalação Manual

Caso prefira instalar sem Docker:

```bash
# Clone o repositório
git clone https://github.com/brunocgc/whaticket-nvnplus.git

# Entre no diretório
cd whaticket-nvnplus

# Instale o pnpm e pm2 globalmente
npm install -g pnpm pm2 yarn

# Entre na pasta de backend
cd backend
# Instale as dependências
pnpm install
# Compile o projeto
pnpm run build
# Execute as migrações do banco de dados
pnpm run db:migrate
# Popule o banco de dados com dados iniciais
pnpm run db:seed
# Inicie o servidor
pnpm run start

# Volte para a pasta principal e entre na pasta de frontend
cd ../frontend
# Instale as dependências
yarn install
# Compile o projeto
yarn run build
# Inicie o servidor
yarn run start
```

> **Nota**: A instalação inclui automaticamente o react-whatsmarked, proporcionando uma experiência visual de mensagens similar ao WhatsApp Web. A versão 1.0.2 também introduz o novo design system modernizado do FlowBuilder com interface modal responsiva e nós categorizados por cores temáticas para melhor organização visual.

## 📱 Como Usar

### 🐳 Usando com Docker

Se você instalou usando Docker, os serviços já estão rodando automaticamente. Apenas acesse:

1. **Interface Principal**: http://localhost:3000
2. **Faça login** com as credenciais padrão (admin@admin.com / 123456)
3. **Configure** seus canais de atendimento
4. **Conecte** seu WhatsApp via QR Code
5. **Comece** a atender seus clientes!

Para **parar** os serviços:
```bash
docker-compose down
```

Para **iniciar** novamente:
```bash
docker-compose up -d
```

### 📦 Usando Instalação Manual

#### Backend

1. Inicie o servidor do backend:
   ```bash
   cd backend
   pm2 start npm --name "nvnplus-backend" -- run start
   ```

2. O serviço de download é iniciado automaticamente como um processo separado, garantindo que:
   - As transferências de arquivos não sobrecarreguem o servidor principal
   - Os atendimentos continuem fluidos mesmo durante downloads de arquivos grandes
   - A interface do usuário permaneça responsiva durante operações de mídia

#### Frontend

2. Inicie o servidor do frontend:
   ```bash
   cd ../frontend
   pm2 start npm --name "nvnplus-frontend" -- run start
   ```

3. Acesse o painel em `http://localhost:3000`
4. Faça login com suas credenciais
5. Configure seus canais de atendimento
6. Comece a atender seus clientes!

## 🔌 API

A plataforma oferece uma API RESTful completa para integração com outros sistemas:

- **Mensagens de Texto**: Envie mensagens de texto via API
- **Mensagens de Mídia**: Envie imagens, documentos e outros arquivos

Para mais detalhes, consulte a [documentação da API](https://api.nvn.plus/docs).

## 🐛 Troubleshooting

### Problemas Comuns com Docker

#### Porta já em uso
```bash
# Verificar portas em uso
netstat -an | findstr ":3000"
netstat -an | findstr ":8000"

# Alterar portas no arquivo .env
FRONTEND_PORT=3001
BACKEND_PORT=8001
```

#### Problemas de memória
```bash
# Aumentar memória disponível para Docker
# No Docker Desktop: Settings > Resources > Memory

# Verificar uso de recursos
docker stats
```

#### Logs de erro
```bash
# Ver logs detalhados
docker-compose logs -f [nome_do_servico]

# Exemplos:
docker-compose logs -f backend
docker-compose logs -f timescaledb
docker-compose logs -f redis
```

#### Recriação completa dos containers
```bash
# Parar e remover tudo (ATENÇÃO: Apaga dados)
docker-compose down -v

# Reconstruir images
docker-compose build --no-cache

# Iniciar novamente
docker-compose up -d
```

#### Backup e Restore com Docker

**Backup do banco de dados:**
```bash
docker-compose exec timescaledb pg_dump -U postgres nvnplus > backup_$(date +%Y%m%d_%H%M%S).sql
```

**Restore do banco de dados:**
```bash
cat backup_file.sql | docker-compose exec -T timescaledb psql -U postgres -d nvnplus
```

**Backup dos arquivos (MinIO):**
```bash
docker-compose exec minio mc mirror /data /backup
```

### Problemas Comuns com Instalação Manual

#### Erro de conexão com banco
- Verifique se o PostgreSQL está rodando
- Confirme as credenciais no arquivo `.env`
- Teste a conexão: `psql -h localhost -U postgres -d nvnplus`

#### Erro de porta em uso
- Altere as portas nos arquivos de configuração
- Verifique processos rodando: `netstat -an | findstr ":3000"`

## 👥 Contribuições

<div align="center">

### 🤝 **Faça Parte da Comunidade NVN.PLUS**

[![Contributors](https://img.shields.io/github/contributors/brunocgc/whaticket-nvnplus?style=for-the-badge&logo=github)](https://github.com/brunocgc/whaticket-nvnplus/graphs/contributors)
[![Pull Requests](https://img.shields.io/github/issues-pr/brunocgc/whaticket-nvnplus?style=for-the-badge&logo=git)](https://github.com/brunocgc/whaticket-nvnplus/pulls)
[![Issues](https://img.shields.io/github/issues/brunocgc/whaticket-nvnplus?style=for-the-badge&logo=github)](https://github.com/brunocgc/whaticket-nvnplus/issues)

</div>

<table>
<tr>
<td width="50%">

### 🚀 **Como Contribuir**

<details>
<summary><strong>💻 Desenvolvimento de Código</strong></summary>

**🎯 Processo Completo:**
1. **Fork do Projeto**
   ```bash
   # Clone seu fork
   git clone https://github.com/SEU_USUARIO/whaticket-nvnplus.git
   cd whaticket-nvnplus
   ```

2. **Configurar Upstream**
   ```bash
   # Adicionar repositório original
   git remote add upstream https://github.com/brunocgc/whaticket-nvnplus.git
   ```

3. **Criar Branch**
   ```bash
   # Atualizar main
   git checkout main
   git pull upstream main

   # Criar nova branch
   git checkout -b feature/nova-funcionalidade
   ```

4. **Desenvolver e Testar**
   ```bash
   # Fazer suas alterações
   # Testar localmente
   npm test
   ```

5. **Commit e Push**
   ```bash
   # Commit semântico
   git add .
   git commit -m "feat: adiciona nova funcionalidade de X"
   git push origin feature/nova-funcionalidade
   ```

6. **Pull Request**
   - Abra PR com descrição detalhada
   - Aguarde revisão da equipe

</details>

<details>
<summary><strong>📚 Documentação</strong></summary>

**📝 Como Ajudar:**
- Melhorar README.md
- Traduzir documentação
- Criar tutoriais
- Corrigir typos
- Adicionar exemplos

**📋 Diretrizes:**
- Linguagem clara e objetiva
- Exemplos práticos
- Screenshots quando necessário
- Manter consistência

</details>

</td>
<td width="50%">

### 🎯 **Tipos de Contribuição**

<table>
<tr>
<td align="center">
<h4>🐛 Bug Reports</h4>
<p>Encontrou um problema?<br/>Reporte no GitHub Issues</p>
<a href="https://github.com/brunocgc/whaticket-nvnplus/issues/new?template=bug_report.md">
<img src="https://img.shields.io/badge/Reportar%20Bug-red?style=for-the-badge&logo=github" alt="Report Bug"/>
</a>
</td>
</tr>
<tr>
<td align="center">
<h4>✨ Feature Request</h4>
<p>Tem uma ideia incrível?<br/>Compartilhe conosco</p>
<a href="https://github.com/brunocgc/whaticket-nvnplus/issues/new?template=feature_request.md">
<img src="https://img.shields.io/badge/Sugerir%20Feature-blue?style=for-the-badge&logo=lightbulb" alt="Feature Request"/>
</a>
</td>
</tr>
<tr>
<td align="center">
<h4>💡 Discussões</h4>
<p>Dúvidas ou ideias?<br/>Vamos conversar</p>
<a href="https://github.com/brunocgc/whaticket-nvnplus/discussions">
<img src="https://img.shields.io/badge/Participar-purple?style=for-the-badge&logo=github" alt="Discussions"/>
</a>
</td>
</tr>
<tr>
<td align="center">
<h4>📖 Wiki/Docs</h4>
<p>Melhore a documentação<br/>do projeto</p>
<a href="https://github.com/brunocgc/whaticket-nvnplus/wiki">
<img src="https://img.shields.io/badge/Contribuir-green?style=for-the-badge&logo=wikipedia" alt="Wiki"/>
</a>
</td>
</tr>
</table>

</td>
</tr>
</table>

### 📋 **Diretrizes de Contribuição**

<details>
<summary><strong>🎨 Padrões de Código</strong></summary>

**Frontend (React/TypeScript):**
```javascript
// ✅ Bom
const MessageComponent: React.FC<MessageProps> = ({ message }) => {
  const [isLoading, setIsLoading] = useState(false);

  return (
    <div className="message-container">
      {message.content}
    </div>
  );
};

// ❌ Evitar
function msg(props) {
  return <div>{props.msg}</div>;
}
```

**Backend (Node.js/TypeScript):**
```typescript
// ✅ Bom
export class MessageController {
  public async createMessage(req: Request, res: Response): Promise<Response> {
    try {
      const messageService = new MessageService();
      const message = await messageService.create(req.body);
      return res.status(201).json(message);
    } catch (error) {
      return res.status(400).json({ error: error.message });
    }
  }
}
```

</details>

<details>
<summary><strong>📝 Commit Guidelines</strong></summary>

**🎯 Formato de Commit:**
```bash
<tipo>(<escopo>): <descrição>

[corpo opcional]

[rodapé opcional]
```

**📋 Tipos Aceitos:**
- `feat`: Nova funcionalidade
- `fix`: Correção de bug
- `docs`: Documentação
- `style`: Formatação, sem mudança de lógica
- `refactor`: Refatoração de código
- `test`: Adição/correção de testes
- `chore`: Tarefas de build, etc.

**✅ Exemplos:**
```bash
feat(flowbuilder): adiciona nó de transferência de fluxo
fix(api): corrige erro de autenticação JWT
docs(readme): atualiza instruções de instalação
```

</details>

<details>
<summary><strong>🧪 Testes</strong></summary>

**🎯 Requisitos:**
- Testes unitários para novas funcionalidades
- Coverage mínimo de 80%
- Testes de integração para APIs

**🚀 Executar Testes:**
```bash
# Backend
cd backend
npm test

# Frontend
cd frontend
npm test

# Coverage
npm run test:coverage
```

</details>

### 🏆 **Hall da Fama - Contribuidores**

<div align="center">

<a href="https://github.com/brunocgc/whaticket-nvnplus/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=brunocgc/whaticket-nvnplus" />
</a>

**🙏 Agradecimentos especiais a todos que contribuem para o projeto!**

</div>

## 🏢 Empresas que Usam

<div align="center">

### 🌟 **Empresas Confiando no NVN.PLUS**

<sub>*Empresas reais usando nossa solução em produção*</sub>

</div>

<table>
<tr>
<td align="center" width="20%">
<img src="https://via.placeholder.com/120x80/0066cc/ffffff?text=Neww+Select" alt="Neww Select" width="120" height="80"/>
<br><strong>Neww Select</strong>
<br><sub>Soluções Empresariais</sub>
</td>
<td align="center" width="20%">
<img src="https://via.placeholder.com/120x80/cc6600/ffffff?text=B%26R+Holdings" alt="B&R Holdings" width="120" height="80"/>
<br><strong>B&R Holdings</strong>
<br><sub>Holding Empresarial</sub>
</td>
<td align="center" width="20%">
<img src="https://via.placeholder.com/120x80/006600/ffffff?text=AN+Marketing" alt="AN Marketing" width="120" height="80"/>
<br><strong>AN Marketing</strong>
<br><sub>Marketing Digital</sub>
</td>
<td align="center" width="20%">
<img src="https://via.placeholder.com/120x80/660066/ffffff?text=Avant+Serviços" alt="Avant Serviços" width="120" height="80"/>
<br><strong>Avant Serviços</strong>
<br><sub>Prestação de Serviços</sub>
</td>
<td align="center" width="20%">
<img src="https://via.placeholder.com/120x80/cc0066/ffffff?text=Nobre+Comercio" alt="Nobre Comercio" width="120" height="80"/>
<br><strong>Nobre Comercio</strong>
<br><sub>Comércio & Varejo</sub>
</td>
</tr>
</table>

### 📊 **Estatísticas de Uso**

<table align="center">
<tr>
<td align="center">
<h3>📈 50K+</h3>
<p>Mensagens/dia</p>
</td>
<td align="center">
<h3>🎫 10K+</h3>
<p>Tickets/mês</p>
</td>
<td align="center">
<h3>⚡ 99.9%</h3>
<p>Uptime</p>
</td>
<td align="center">
<h3>🕰️ <5s</h3>
<p>Tempo resposta</p>
</td>
</tr>
</table>

### 🤝 **Sua Empresa Aqui**

<div align="center">

**💼 Usa o NVN.PLUS na sua empresa?**

<table>
<tr>
<td align="center">
<h4>📧 Nos Conte Sobre Seu Caso</h4>
<p>Compartilhe como o NVN.PLUS<br/>está transformando seu negócio</p>
<a href="mailto:brunocgc@nvn.plus?subject=Case%20Study%20-%20Nossa%20Empresa">
<img src="https://img.shields.io/badge/Enviar%20Case%20Study-0078D4?style=for-the-badge&logo=microsoft-outlook" alt="Case Study"/>
</a>
</td>
<td align="center">
<h4>🎯 Benefícios de Aparecer Aqui</h4>
<p>• Visibilidade para sua marca<br/>• Networking com outras empresas<br/>• Feedback valioso da comunidade</p>
<a href="https://wa.me/552120428610?text=Olá!%20Gostaríamos%20de%20aparecer%20na%20lista%20de%20empresas%20que%20usam%20o%20NVN.PLUS">
<img src="https://img.shields.io/badge/Falar%20Conosco-25D366?style=for-the-badge&logo=whatsapp" alt="WhatsApp"/>
</a>
</td>
</tr>
</table>

</div>

---

<div align="center">

<table>
<tr>
<td align="center">
<h3>🚀 Comece Agora</h3>
<p>
<a href="#-quick-start">
<img src="https://img.shields.io/badge/Quick%20Start-Começar%20Agora-brightgreen?style=for-the-badge&logo=rocket" alt="Quick Start"/>
</a>
</p>
</td>
<td align="center">
<h3>📞 Suporte</h3>
<p>
<a href="https://wa.me/552120428610">
<img src="https://img.shields.io/badge/WhatsApp-Falar%20Conosco-25D366?style=for-the-badge&logo=whatsapp" alt="WhatsApp"/>
</a>
</p>
</td>
<td align="center">
<h3>⭐ GitHub</h3>
<p>
<a href="https://github.com/brunocgc/whaticket-nvnplus">
<img src="https://img.shields.io/badge/GitHub-Dar%20Estrela-181717?style=for-the-badge&logo=github" alt="GitHub"/>
</a>
</p>
</td>
<td align="center">
<h3>💬 Comunidade</h3>
<p>
<a href="https://github.com/brunocgc/whaticket-nvnplus/discussions">
<img src="https://img.shields.io/badge/Discord-Entrar%20Agora-7289DA?style=for-the-badge&logo=discord" alt="Discord"/>
</a>
</p>
</td>
</tr>
</table>

<br>

**Desenvolvido com ❤️ por NvN Group**

<sub>© 2025 NVN.PLUS - Todos os direitos reservados</sub>

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Code of Conduct](https://img.shields.io/badge/Code%20of%20Conduct-✓-green.svg)](CODE_OF_CONDUCT.md)

</div>
