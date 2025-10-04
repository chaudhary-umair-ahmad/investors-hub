# Investor's Hub - Bayut.sa

> A comprehensive digital platform enabling international investors to discover, invest in, and manage real estate investments in Saudi Arabia's Free Zones.

## 📋 Project Documentation

This repository contains complete project specifications and documentation for building the Investor's Hub platform. All documentation has been carefully designed to serve as **Cursor AI rules** to guide development.

### Documentation Files

1. **[PROJECT_OVERVIEW.md](./PROJECT_OVERVIEW.md)** - Executive summary and complete feature specifications
2. **[rules/project-rules.mdc](./rules/project-rules.mdc)** - Core project rules and development guidelines
3. **[rules/tech-stack.mdc](./rules/tech-stack.mdc)** - Technology stack specifications and setup instructions
4. **[rules/database-schema.mdc](./rules/database-schema.mdc)** - Complete database schema and data models
5. **[rules/api-specification.mdc](./rules/api-specification.mdc)** - RESTful API endpoint specifications

## 🎯 Project Vision

Investor's Hub is built on three core principles:
- **Transparency**: Complete visibility into investment journey and payments
- **Trust**: End-to-end service management by Bayut
- **Excellence**: White-glove services tailored to investor needs

## 🏗️ System Architecture

### Platform Components

```
┌─────────────────────────────────────────────────────────────┐
│                     Landing Page (Next.js)                   │
│          Public marketing site with lead generation          │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                 Investor Portal (React.js)                   │
│      Private dashboard for investors to manage investments   │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                  Admin Panel (React.js)                      │
│         Back-office for staff to manage operations           │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                  Backend API (Ruby on Rails)                 │
│       Business logic, integrations, data management          │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
         ┌──────────────────────────────────────┐
         │  MySQL Database  │  Redis Cache      │
         └──────────────────────────────────────┘
```

### Third-Party Integrations
- **Keycloak** - User authentication (OAuth 2.0)
- **Checkout.com** - Payment processing
- **WhatsApp Business API** - Direct messaging
- **Unifonic** - SMS notifications
- **MoEngage** - Email campaigns
- **AWS S3** - File storage
- **Bayut CRM** - Lead and customer management

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ (for frontend)
- Ruby 3.x (for backend)
- MySQL 8.x
- Redis 6+
- Git

### Development Setup

**1. Clone the repository**
```bash
git clone <repository-url>
cd investors-hub
```

**2. Set up Backend (Rails)**
```bash
cd backend
bundle install
rails db:create db:migrate db:seed
rails server -p 3000
```

**3. Set up Frontend (React Portal)**
```bash
cd frontend/portal
npm install
npm start
```

**4. Set up Landing Page (Next.js)**
```bash
cd frontend/landing
npm install
npm run dev
```

**5. Set up Admin Panel**
```bash
cd frontend/admin
npm install
npm start
```

### Environment Variables

Create `.env` files in each directory based on `.env.example` templates.

**Backend (.env)**:
```env
DATABASE_URL=mysql2://user:password@localhost:3306/investors_hub_development
REDIS_URL=redis://localhost:6379/0
JWT_SECRET_KEY=your_secret_key
AWS_S3_BUCKET=investors-hub-documents
CHECKOUT_SECRET_KEY=your_checkout_key
# ... more variables (see tech-stack.mdc)
```

**Frontend (.env.local)**:
```env
REACT_APP_API_URL=http://localhost:3000/api/v1
REACT_APP_KEYCLOAK_URL=https://auth.bayut.sa
# ... more variables
```

## 📦 Tech Stack

### Frontend
- **Frameworks**: React 18+, Next.js 14+ (App Router)
- **UI Library**: Ant Design 5.x (minimal, modern theme)
- **Language**: TypeScript 5+
- **State Management**: React Context API, React Query
- **Styling**: CSS Modules, Tailwind CSS
- **Forms**: React Hook Form + Yup validation
- **i18n**: react-i18next (English, Arabic, Russian, Chinese)

### Backend
- **Framework**: Ruby on Rails 7.x (API mode)
- **Language**: Ruby 3.x
- **Database**: MySQL 8.x
- **Cache**: Redis 6+
- **Background Jobs**: Sidekiq
- **Authentication**: JWT (Keycloak integration)
- **Authorization**: Pundit
- **File Upload**: Active Storage (AWS S3)

### Infrastructure
- **Cloud**: AWS (EC2, RDS, S3, CloudFront, ElastiCache)
- **CI/CD**: GitHub Actions / GitLab CI
- **Monitoring**: CloudWatch, New Relic/Datadog
- **Error Tracking**: Sentry

## 🌟 Key Features

### For Investors (Portal)
1. **Projects Discovery** - Browse Free Zone investment opportunities
2. **Investment Tracker** - Track journey from lead to ownership (12 stages)
3. **Portfolio Management** - Monitor properties and real-time gains
4. **Payment Processing** - Secure payments via Checkout.com
5. **Document Management** - Upload and track verification status
6. **Help Center** - FAQs, articles, direct contact with account manager
7. **Multi-language** - English, Arabic (RTL), Russian, Chinese
8. **Multi-currency** - Display prices in 9 currencies

### For Staff (Admin Panel)
1. **Investor Management** - CRUD operations, journey tracking
2. **Projects Management** - Add/edit projects and property types
3. **Lead Management** - Track and convert leads
4. **Document Verification** - Review and approve uploaded documents
5. **Payment Tracking** - Monitor all transactions
6. **Content Management** - FAQs, articles, testimonials
7. **Analytics Dashboard** - Key metrics and reports

### Investment Packages

- **Virtual Tier**: $1,000 (SAR 3,750) - Remote investment, 8 virtual tours, no travel required
- **Basic Tier**: $2,000 (SAR 7,500) - 1 person, 3-star hotel, 4 days, 2 site visits *+flights*
- **Top Tier**: From $7,500 (SAR 28,000) - 1-3 people (+$2,500/person), 4-star hotel, 6 days *+flights*
- **Elite Tier**: From $25,000 (SAR 95,000) - 1-5 people (+$5,500/person), 5-star luxury, 7 days *+flights*

*In-person packages: Flight tickets not included - investors book their own flights*

## 📊 Development Phases

### Phase 1: MVP (12-16 weeks)
- Landing page with lead capture
- Investor portal (hardcoded auth)
- Admin panel (projects CRUD, investor management)
- Backend API with core features
- Payment integration (Checkout.com test mode)
- Basic email notifications
- English language only

### Phase 2: Full Features (8-12 weeks)
- Keycloak authentication integration
- Multi-language support (4 languages)
- Multi-currency with live rates
- WhatsApp Business API
- SMS notifications (Unifonic)
- CRM integration
- Advanced analytics

### Phase 3: Enhancements (Ongoing)
- Mobile apps
- AI-powered recommendations
- Live chat support
- Advanced property management
- VR property tours

## 🧪 Testing

### Frontend Testing
```bash
npm test                 # Run unit tests
npm run test:coverage    # Run with coverage
npm run test:e2e         # Run Cypress E2E tests
```

### Backend Testing
```bash
bundle exec rspec                    # Run all tests
bundle exec rspec spec/models        # Run model tests
bundle exec rspec --format doc       # Detailed output
```

### Test Coverage Goals
- Frontend: 70%+
- Backend: 80%+

## 🚢 Deployment

### Staging
```bash
git push origin develop
# CI/CD pipeline automatically deploys to staging
```

### Production
```bash
git checkout main
git merge develop
git push origin main
# Manual approval required, then CI/CD deploys
```

### AWS Infrastructure
- **Compute**: EC2 / ECS
- **Database**: RDS MySQL (Multi-AZ)
- **Cache**: ElastiCache Redis
- **Storage**: S3 + CloudFront CDN
- **Load Balancer**: Application Load Balancer

## 📖 API Documentation

API documentation is available at:
- Development: `http://localhost:3000/api-docs`
- Staging: `https://staging-api.investors-hub.bayut.sa/api-docs`
- Production: `https://api.investors-hub.bayut.sa/api-docs`

See [api-specification.mdc](./rules/api-specification.mdc) for complete API specs.

## 🔒 Security

- JWT-based authentication
- Role-based access control (RBAC)
- HTTPS/TLS encryption
- PCI DSS compliance (via Checkout.com)
- Secure document storage (private S3 buckets)
- Rate limiting (100 req/min)
- Input validation and sanitization
- SQL injection prevention
- XSS protection

## 🌍 Localization

### Supported Languages
- 🇬🇧 English (en) - Primary
- 🇸🇦 Arabic (ar) - RTL support
- 🇷🇺 Russian (ru)
- 🇨🇳 Chinese (zh) - Simplified

### Supported Currencies
SAR, USD, AUD, AED, GBP, CAD, QAR, INR, PKR

All financial data stored in SAR, converted for display based on user preference.

## 🤝 Contributing

### Git Workflow
1. Create feature branch from `develop`
2. Develop and commit changes
3. Create pull request
4. Code review and approval
5. Merge to `develop`
6. Deploy to staging
7. Merge to `main` for production

### Commit Message Format
```
feat: add project filtering
fix: resolve payment webhook issue
docs: update API documentation
refactor: optimize database queries
test: add unit tests for payment service
```

### Code Review Checklist
- [ ] Code follows style guide (ESLint/RuboCop)
- [ ] Tests included and passing
- [ ] No hardcoded credentials
- [ ] Documentation updated
- [ ] Error handling implemented
- [ ] Security considerations addressed

## 📞 Support

### For Development Team
- Technical Lead: [Name]
- Product Manager: [Name]
- Slack Channel: #investors-hub-dev

### For Business Team
- Project Sponsor: Bayut.sa Management
- Stakeholders: Sales, Operations, Finance teams

## 📝 License

Proprietary - Bayut.sa
All rights reserved.

---

## 🎯 Success Metrics

### Business KPIs
- Lead conversion rate: Target 15%+
- Average investment per investor: Target SAR 1M+
- Customer satisfaction score (CSAT): Target 4.5/5
- Platform uptime: Target 99.9%

### Technical KPIs
- Page load time: <3 seconds
- API response time: <500ms (p95)
- Error rate: <1%
- Test coverage: 80%+

---

**Built with ❤️ by Bayut.sa Development Team**

*Empowering international investors to participate in Saudi Arabia's real estate growth story*

