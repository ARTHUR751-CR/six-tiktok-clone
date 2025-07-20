# Six - Clone do TikTok

Um clone moderno do TikTok construído com Next.js, Prisma, NextAuth e Tailwind CSS.

## 🚀 Características

- **Design moderno**: Interface preta e laranja inspirada no TikTok
- **Autenticação múltipla**: Login via telefone (OTP) e Google OAuth
- **Banco de dados real**: PostgreSQL com Prisma ORM
- **Feed de vídeos**: Scroll vertical infinito como o TikTok
- **Sistema de likes e comentários**: Interação social completa
- **Responsivo**: Funciona perfeitamente em mobile e desktop

## 🛠️ Tecnologias

- **Frontend**: Next.js 15, React 19, TypeScript
- **Styling**: Tailwind CSS, shadcn/ui
- **Autenticação**: NextAuth.js
- **Banco de dados**: PostgreSQL, Prisma ORM
- **SMS**: Twilio (para OTP)
- **Deploy**: Vercel (recomendado)

## 📋 Pré-requisitos

- Node.js 18+ 
- PostgreSQL
- Conta Google Cloud (para OAuth)
- Conta Twilio (para SMS - opcional)

## 🔧 Instalação

1. **Clone o repositório**
```bash
git clone <seu-repositorio>
cd six-tiktok-clone
```

2. **Instale as dependências**
```bash
npm install
```

3. **Configure as variáveis de ambiente**
```bash
cp .env.example .env.local
```

Edite o arquivo `.env.local` com suas configurações:

```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/six_db"

# NextAuth
NEXTAUTH_URL="http://localhost:8000"
NEXTAUTH_SECRET="seu-secret-aqui"

# Google OAuth
GOOGLE_CLIENT_ID="seu-google-client-id"
GOOGLE_CLIENT_SECRET="seu-google-client-secret"

# Twilio (opcional)
TWILIO_ACCOUNT_SID="seu-twilio-sid"
TWILIO_AUTH_TOKEN="seu-twilio-token"
TWILIO_PHONE_NUMBER="seu-numero-twilio"
```

4. **Configure o banco de dados**
```bash
# Gerar o cliente Prisma
npx prisma generate

# Executar as migrações
npx prisma migrate dev --name init

# (Opcional) Visualizar o banco
npx prisma studio
```

5. **Execute o projeto**
```bash
npm run dev
```

O app estará disponível em `http://localhost:8000`

## 🔑 Configuração do Google OAuth

1. Acesse o [Google Cloud Console](https://console.cloud.google.com/)
2. Crie um novo projeto ou selecione um existente
3. Ative a API do Google+
4. Vá para "Credenciais" > "Criar credenciais" > "ID do cliente OAuth 2.0"
5. Configure as URLs autorizadas:
   - **Origens JavaScript autorizadas**: `http://localhost:8000`
   - **URIs de redirecionamento autorizados**: `http://localhost:8000/api/auth/callback/google`
6. Copie o Client ID e Client Secret para o `.env.local`

## 📱 Configuração do Twilio (SMS)

1. Crie uma conta no [Twilio](https://www.twilio.com/)
2. Obtenha seu Account SID e Auth Token
3. Compre um número de telefone Twilio
4. Configure as variáveis no `.env.local`

**Nota**: O SMS é opcional. Em desenvolvimento, o código OTP é exibido no console.

## 🗄️ Estrutura do Banco de Dados

O projeto usa as seguintes tabelas principais:

- **User**: Usuários do sistema
- **Video**: Vídeos postados
- **Like**: Sistema de curtidas
- **Comment**: Comentários nos vídeos
- **Follow**: Sistema de seguidores
- **OtpCode**: Códigos OTP para autenticação

## 🚀 Deploy

### Vercel (Recomendado)

1. Conecte seu repositório ao Vercel
2. Configure as variáveis de ambiente no painel da Vercel
3. Configure um banco PostgreSQL (recomendado: Neon, Supabase ou Railway)
4. Atualize a `NEXTAUTH_URL` para sua URL de produção
5. Deploy!

### Outras plataformas

O projeto é compatível com qualquer plataforma que suporte Next.js:
- Netlify
- Railway
- Heroku
- DigitalOcean App Platform

## 🎯 Funcionalidades

### ✅ Implementadas
- [x] Layout responsivo preto e laranja
- [x] Sistema de autenticação (telefone + Google)
- [x] Feed de vídeos com scroll vertical
- [x] Sistema de likes
- [x] Banco de dados completo
- [x] APIs RESTful

### 🔄 Em desenvolvimento
- [ ] Upload de vídeos
- [ ] Sistema de comentários
- [ ] Perfil de usuário
- [ ] Sistema de seguidores
- [ ] Busca e hashtags
- [ ] Notificações push

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 🆘 Suporte

Se você encontrar algum problema ou tiver dúvidas:

1. Verifique se todas as dependências estão instaladas
2. Confirme se as variáveis de ambiente estão configuradas
3. Verifique se o banco de dados está rodando
4. Consulte os logs do console para erros específicos

## 🎉 Créditos

Desenvolvido com ❤️ usando as melhores tecnologias web modernas.
