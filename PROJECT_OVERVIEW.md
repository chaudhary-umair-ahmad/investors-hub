# Investor's Hub - Project Overview

## Executive Summary

Investor's Hub is a comprehensive digital platform for Bayut.sa that enables international investors to discover, invest in, and manage their real estate investments in Saudi Arabia's Free Zones. The platform consists of a public-facing landing page and a private investor portal with complete investment journey tracking from initial interest to property ownership and beyond.

## Business Context

### Problem Statement
Saudi Arabia is launching Free Zones where expatriates and international residents can invest in designated real estate projects. Currently, there's no centralized platform for international investors to:
- Discover vetted Free Zone investment opportunities
- Navigate the complex investment process including visa, payments, and documentation
- Track their investment journey and portfolio performance
- Access white-glove concierge services for property visits and management

### Solution
Bayut's Investor's Hub provides an end-to-end platform that combines:
1. **Lead Generation**: Marketing landing page showcasing opportunities
2. **Investor Portal**: Private dashboard for managing investments
3. **Journey Tracking**: Complete transparency from application to ownership
4. **Tiered Services**: Flexible packages (Basic, Top, Elite) with varying service levels
5. **Admin Panel**: Back-office system for staff to manage investors, projects, and operations

### Core Value Propositions
- **Transparency**: Real-time tracking of all processes and payments
- **Trust**: Bayut manages documentation, payments, and ownership transfer
- **Exclusivity**: Access to curated Free Zone projects and expert guidance
- **Convenience**: End-to-end service including visa, travel, and property management

## Target Users

### Primary Users
1. **International Investors**
   - Expatriates living outside Saudi Arabia
   - High-net-worth individuals seeking Saudi real estate opportunities
   - Investment groups or family offices
   - Age range: 30-65 years
   - Tech-savvy, multilingual (English, Arabic, Russian, Chinese)

2. **Bayut Account Managers**
   - Sales and relationship managers
   - Dedicated support for investor queries
   - Guide investors through the journey

3. **Bayut Administrative Staff**
   - Super Admins: Full system access
   - Content Managers: Manage projects, properties, and content
   - Operations Team: Handle documentation and processes

## System Architecture

### Platform Components

#### 1. Landing Page (Public)
**Technology**: Next.js
**Purpose**: Marketing and lead generation
**Key Sections**:
- Hero section with value proposition
- Investment opportunities overview
- Listed Free Zone projects showcase
- USPs and benefits of investing through Bayut
- Package comparison (Basic, Top, Elite)
- Testimonials from successful investors
- FAQs
- Lead capture form
- Call-to-action for portal signup

#### 2. Investor Portal (Authenticated)
**Technology**: React.js with Ant Design
**Purpose**: Private dashboard for investors
**Key Features**: Detailed in Features section below

#### 3. Admin Panel (Staff Only)
**Technology**: React.js with Ant Design
**Purpose**: Back-office management
**Key Features**: Detailed in Features section below

#### 4. Backend API
**Technology**: Ruby on Rails
**Purpose**: Business logic, data management, integrations
**Key Responsibilities**:
- RESTful API endpoints
- Authentication via Keycloak integration
- Database operations
- Third-party integrations (payment, CRM, communications)
- File storage and document management
- Currency conversion and calculations

### Technical Stack

#### Frontend
- **Landing Page**: Next.js 14+ (App Router)
- **Portal & Admin**: React.js 18+ with TypeScript
- **UI Framework**: Ant Design 5.x (minimal, modern theme)
- **State Management**: React Context API / Redux Toolkit
- **HTTP Client**: Axios
- **Forms**: React Hook Form with Yup validation
- **Internationalization**: i18next / react-i18next
- **Styling**: CSS Modules / Tailwind CSS with Ant Design

#### Backend
- **Framework**: Ruby on Rails 7.x (API mode)
- **Language**: Ruby 3.x
- **API**: RESTful JSON API
- **Authentication**: JWT tokens via Keycloak
- **File Upload**: Active Storage with AWS S3
- **Background Jobs**: Sidekiq with Redis
- **API Documentation**: Swagger/OpenAPI

#### Database
- **Primary DB**: MySQL 8.x
- **Caching**: Redis
- **Search**: Elasticsearch (optional, for project search)

#### Infrastructure
- **Cloud Provider**: AWS
- **Compute**: EC2 / ECS / Elastic Beanstalk
- **Storage**: S3 (documents, images)
- **CDN**: CloudFront
- **Database**: RDS MySQL
- **Cache**: ElastiCache Redis
- **Load Balancer**: Application Load Balancer
- **Monitoring**: CloudWatch

#### Third-Party Integrations
- **Authentication**: Keycloak (existing Bayut system)
- **Payment Gateway**: Checkout.com (existing account)
- **WhatsApp**: WhatsApp Business API
- **SMS**: Unifonic
- **Email**: MoEngage
- **CRM**: Bayut's in-house CRM (integration required)
- **Currency Exchange**: External API (e.g., exchangerate-api.io)

### Authentication Flow
1. User clicks "Sign Up" or "Login" on landing page
2. Redirect to Keycloak authentication page
3. User completes authentication/registration
4. Keycloak redirects back with JWT token and user information
5. Frontend stores JWT and makes authenticated API calls
6. Backend validates JWT on each request
7. **MVP Note**: Hardcode a test user for initial development

## Features Specification

### Landing Page Features

#### LP-1: Hero Section
- Compelling headline and subheadline
- Primary CTA button (Sign Up / Get Started)
- Background: High-quality imagery of Saudi Arabia / Free Zones
- Multi-language support

#### LP-2: Investment Opportunities
- Overview of Saudi Free Zones
- Benefits of investing (tax incentives, ownership rights, ROI potential)
- Interactive map of Free Zone locations

#### LP-3: Projects Showcase
- Grid/carousel of featured Free Zone projects
- Each project card shows:
  - Project image
  - Project name
  - Developer
  - Location
  - Starting price (in multiple currencies)
  - Expected ROI
  - "View Details" CTA
- Filter by location, price range, property type

#### LP-4: Package Comparison
- Side-by-side comparison table
- Basic, Top, Elite tiers
- Key features highlighted
- Pricing (if applicable)
- "Select Package" CTA

#### LP-5: Why Bayut Section
- Trust indicators (certifications, years of experience)
- Transparency commitment
- Expert guidance promise
- End-to-end service highlight

#### LP-6: Testimonials
- Investor success stories
- Video testimonials (optional)
- Before/after investment journeys

#### LP-7: FAQs
- Accordion-style FAQ section
- Categories: Investment Process, Free Zones, Visa, Payments, Ownership

#### LP-8: Lead Capture Form
- Fields: Name, Email, Phone, Country, Investment Interest
- "Submit Interest" button
- Confirmation message
- Data sent to CRM

#### LP-9: Footer
- Links to terms, privacy policy, contact
- Social media links
- Multi-language selector

### Investor Portal Features

#### P-1: Dashboard (Home)
- Welcome message with investor name
- Quick stats overview:
  - Total investment value
  - Active properties
  - Pending payments
  - Journey stage
- Quick actions:
  - View new projects
  - Track investment journey
  - Contact account manager
  - Upload documents
- Recent activity feed
- Announcements / news banner

#### P-2: Projects Section

##### P-2.1: Projects List
- Grid/list view toggle
- Each project card:
  - Hero image/gallery
  - Project name
  - Developer name
  - Location (with map pin)
  - Price range in selected currency
  - Expected ROI / gains
  - Completion date
  - Availability status
  - "View Details" button
- Filters:
  - Location
  - Price range
  - Property type
  - Developer
  - Availability
- Sorting:
  - Price (low to high, high to low)
  - Expected ROI
  - Newest first
  - Popularity
- Search bar

##### P-2.2: Project Details Page
- Image gallery / carousel
- Project information:
  - Name, developer, location (with embedded map)
  - Description
  - Salient features
  - Amenities (with icons)
  - Master plan / layout images
  - Timeline / completion date
- Property Types offered:
  - List of available unit types (apartments, villas, land plots, etc.)
  - Each type shows:
    - Name / type
    - Size (sq ft / sq m)
    - Bedrooms / bathrooms
    - Starting price (multi-currency)
    - Payment plan
    - Availability
    - Floor plans
    - "Express Interest" button
- Pricing & Payment Plans:
  - Down payment percentage
  - Installment schedule
  - Total price breakdown
- Expected Gains:
  - Projected ROI
  - Historical price trends (if available)
  - Market analysis summary
- Documents:
  - Downloadable brochures, floor plans, legal docs
- Contact Account Manager CTA
- Share project button

#### P-3: Investor Tracker

##### P-3.1: Journey Timeline
Visual timeline with stages:

1. **Lead Submitted** ✅
   - Date of submission
   - Status: Completed

2. **Package Selection** 
   - Selected tier (Basic / Top / Elite)
   - Package details
   - Status: Completed / Pending

3. **Account Manager Assigned** 
   - Manager name, photo, contact
   - Initial consultation scheduled
   - Status: Completed / In Progress / Pending

4. **Property Selection** 
   - Projects shortlisted
   - Site visit scheduled (if applicable)
   - Selected property details
   - Status: In Progress / Pending

5. **Visa Process** 
   - Application status
   - Required documents checklist
   - Upload documents section
   - Visa approval status
   - Status: Not Started / In Progress / Approved / N/A

6. **Travel Arrangements** (if visa included)
   - Flight booking status
   - Ticket details (PNR, dates, download ticket)
   - Hotel booking
     - Hotel name, star rating, location
     - Check-in / check-out dates
   - Trip itinerary
     - Day-by-day schedule
     - Site visits planned
     - Entertainment activities
   - Transportation details
   - Status: Not Started / Booked / Completed / N/A

7. **Site Visit Completed** (if applicable)
   - Visit date
   - Properties visited
   - Notes from visit
   - Status: Scheduled / Completed / N/A

8. **Down Payment** 
   - Amount due (multi-currency)
   - Payment deadline
   - Payment status
   - "Make Payment" button
   - Payment receipt (download)
   - Status: Pending / Paid

9. **Installment Payments** 
   - Payment schedule table:
     - Installment number
     - Due date
     - Amount
     - Status (Upcoming / Due / Paid / Overdue)
   - Payment reminders
   - "Pay Now" button for due installments
   - Auto-payment setup option
   - Status: In Progress

10. **Documentation & Legal** 
    - Required documents checklist
    - Upload section
    - Contract signing
    - Legal verification status
    - Status: In Progress / Completed

11. **Ownership Transfer** 
    - Transfer date
    - Property handover details
    - Title deed documents
    - Status: Pending / Completed

12. **Post-Ownership** (optional)
    - Property management opt-in
    - Rental management
    - Development/construction (for land)
    - Status: Active / N/A

##### P-3.2: Payment Journey Sub-section
- Total amount invested
- Amount paid to date
- Outstanding balance
- Next payment due (date and amount)
- Complete payment history table:
  - Date
  - Description
  - Amount
  - Currency
  - Status
  - Receipt download
- Payment reminders and notifications
- Set up auto-payment

##### P-3.3: Reminders & Notifications
- Upcoming payment reminders
- Document upload reminders
- Milestone notifications
- Notification preferences settings

#### P-4: Portfolio Section

##### P-4.1: Portfolio Overview
- Summary cards:
  - Total properties owned
  - Total investment value
  - Total current value (with real-time gains)
  - Total gains/loss (amount and percentage)

##### P-4.2: Properties List
Table/card view of all properties:
- Property image
- Project name
- Property type (apartment, villa, land)
- Location
- Purchase date
- Purchase price (original)
- Current estimated value
- Gain/Loss (amount and %)
- Status:
  - Off-plan (with completion %)
  - Under construction
  - Ready
  - Owned
- Payment status:
  - Fully paid
  - Installments active (X of Y paid)
  - Next payment date
- Actions:
  - View details
  - Track payments
  - Request property management
  - Download documents

##### P-4.3: Property Details View
- Complete property information
- Purchase details and contract
- Payment schedule and history
- Construction/completion progress (for off-plan)
- Current market value with price history graph
- Documents (title deed, contracts, etc.)
- Property management options:
  - Hand over to Bayut for rental management
  - Request development/construction (for land)
  - Contact property manager

##### P-4.4: Real-time Gains Tracking
- Each property shows live estimated value
- Price updated based on latest project pricing
- Percentage gain/loss calculation
- Historical price trend graph (line chart)
- Market insights and news affecting value

#### P-5: Profile Section

##### P-5.1: Personal Information
- Full name
- Email (verified status)
- Phone number (verified status)
- Country/Nationality
- Date of birth
- Profile photo upload
- Edit button

##### P-5.2: Account Status
- Account type (Investor)
- Package tier (Basic / Top / Elite)
- Member since date
- Account status (Active / Pending verification / Suspended)
- Verification badges (Email ✓, Phone ✓, ID ✓)

##### P-5.3: Contact Details
- Primary email
- Secondary email (optional)
- Phone number
- WhatsApp number
- Preferred contact method
- Mailing address

##### P-5.4: Documents
- Upload and manage documents:
  - National ID / Passport
  - Proof of address
  - Financial documents
  - Visa documents
  - Any additional required documents
- Document status (Pending review / Verified / Rejected)
- Upload new document button
- Download uploaded documents

##### P-5.5: Settings
- Language preference (English / Arabic / Russian / Chinese)
- Currency preference for display
- Notification preferences:
  - Email notifications (on/off for each type)
  - SMS notifications
  - WhatsApp notifications
  - Push notifications (future)
- Privacy settings
- Change password (redirects to Keycloak)

##### P-5.6: Package Information
- Current package details
- Package benefits list
- Upgrade/downgrade option
- Package history

#### P-6: Help & Support Center

##### P-6.1: Account Manager Card
- Manager photo
- Name and title
- Email
- Phone number
- WhatsApp number (with one-click call/WhatsApp buttons)
  - "Call Now" button
  - "WhatsApp" button (opens WhatsApp chat)
- Working hours
- "Send Message" form

##### P-6.2: FAQs Section
Categories:
- Getting Started
- Investment Process
- Free Zones Information
- Visa & Travel
- Payments & Installments
- Property Ownership
- Property Management
- Account & Settings

Each FAQ with expandable answer

##### P-6.3: Knowledge Base / Articles
- Latest articles grid/list:
  - Investment tips
  - New projects announcements
  - Free Zone guidelines and regulations
  - Market insights and opportunities
  - Success stories
  - News and updates
- Filter by category
- Search articles
- Article detail page with rich content

##### P-6.4: Contact Support
- Contact form:
  - Subject
  - Category dropdown
  - Message
  - Attach files
  - Submit button
- Alternative contact methods:
  - Email: support@bayut.sa
  - Phone: +966 XXX XXXX
  - WhatsApp Business
- Live chat widget (optional, future enhancement)

##### P-6.5: Ticket History
- View previous support tickets
- Status: Open / In Progress / Resolved
- Click to view ticket details and conversation

### Admin Panel Features

#### A-1: Dashboard
- Key metrics:
  - Total investors
  - Active leads
  - Total properties listed
  - Total projects
  - Revenue (total, this month)
  - Pending approvals (documents, payments)
- Recent activity feed
- Quick actions
- Charts and analytics:
  - Investor growth over time
  - Revenue by month
  - Popular projects
  - Conversion funnel

#### A-2: Investors Management

##### A-2.1: Investors List
- Table view with columns:
  - ID
  - Name
  - Email
  - Phone
  - Country
  - Package tier
  - Account status
  - Assigned manager
  - Total investment
  - Registration date
  - Actions (View, Edit, Deactivate)
- Filters:
  - Status
  - Package tier
  - Account manager
  - Registration date range
  - Investment amount range
- Search by name, email, phone
- Export to CSV

##### A-2.2: Investor Detail View
- Personal information (all profile data)
- Package and tier information
- Assigned account manager (with reassign option)
- Investment journey timeline (view/edit)
- Properties portfolio
- Payment history
- Uploaded documents:
  - View/download documents
  - Approve/reject documents
  - Document verification status
- Communication history (emails, WhatsApp, tickets)
- Notes section (internal staff notes)
- Activity log
- Actions:
  - Edit information
  - Change status
  - Assign/reassign manager
  - Send notification
  - Generate report

##### A-2.3: Lead Management
- Leads from landing page
- Status: New / Contacted / Qualified / Converted / Lost
- Assign to account manager
- Convert to investor (create portal account)
- Add notes and follow-ups

#### A-3: Projects Management (Content Manager Role)

##### A-3.1: Projects List
- Table/grid view:
  - Project name
  - Developer
  - Location
  - Status (Draft / Published / Archived)
  - Property count
  - Date added
  - Actions (View, Edit, Delete)
- Search and filters
- "Add New Project" button

##### A-3.2: Add/Edit Project
Form sections:
1. **Basic Information**
   - Project name (multi-language)
   - Developer name
   - Description (rich text editor, multi-language)
   - Status (Draft / Published / Archived)

2. **Location**
   - Free Zone area
   - City
   - Address
   - Map coordinates (lat/long or map picker)

3. **Media**
   - Hero image upload
   - Gallery images (multiple upload)
   - Master plan images
   - Videos (upload or YouTube links)

4. **Features & Amenities**
   - Add/remove features (multi-language)
   - Amenity selection (checkboxes with icons)
   - Highlight key features

5. **Pricing & Financial**
   - Price range (from - to) in SAR
   - Expected ROI (percentage)
   - Payment plan details
   - Down payment percentage
   - Installment schedule

6. **Timeline**
   - Start date
   - Expected completion date
   - Current progress percentage

7. **Documents**
   - Upload brochures
   - Legal documents
   - Floor plans
   - Other attachments

8. **SEO & Meta**
   - Meta title
   - Meta description
   - URL slug

- Save as Draft / Publish buttons
- Preview button

##### A-3.3: Property Types (Units) Management
Within each project:
- List of property types/units
- "Add Property Type" button

Add/Edit Property Type Form:
- Property type name (multi-language)
- Unit type (Apartment / Villa / Townhouse / Land Plot / Studio / Other)
- Size (area in sq ft and sq m)
- Bedrooms count
- Bathrooms count
- Description (rich text, multi-language)
- Price in SAR
- Availability status (Available / Sold Out / Coming Soon)
- Stock/inventory count
- Floor plans (image uploads)
- Unit features/specifications
- Gallery images
- Save button

##### A-3.4: Bulk Import
- Import projects from CSV/Excel template
- Import property types in bulk
- Validation and error handling

#### A-4: Content Management (for Help Center)

##### A-4.1: FAQs Management
- List of FAQs
- Add/Edit/Delete FAQ
- Categories management
- Multi-language support
- Order/sort FAQs

##### A-4.2: Articles Management
- List of articles
- Add/Edit/Delete article
- Rich text editor
- Featured image
- Categories and tags
- Publish date
- Author
- Multi-language support
- SEO fields

##### A-4.3: Testimonials Management
- Add/Edit/Delete testimonials
- Investor name
- Photo/video
- Testimonial text
- Publish status

#### A-5: Account Managers Management (Super Admin)
- List of account managers
- Add/Edit/Delete manager
- Manager profile:
  - Name
  - Photo
  - Email
  - Phone
  - WhatsApp
  - Department
  - Working hours
  - Bio
- Assign investors to managers
- Manager performance metrics

#### A-6: Packages Management

##### A-6.1: Package Configuration
- List of tiers (Basic, Top, Elite)
- Edit package details:
  - Package name
  - Description
  - Price (if applicable)
  - Features list (checkboxes/text)
  - Service inclusions:
    - Number of participants allowed
    - Visa consultancy level
    - Hotel star rating
    - Transportation type
    - Trip duration (days)
    - Site visits included
    - Entertainment activities
    - Other benefits
- Comparison view
- Publish/unpublish packages

#### A-7: Payments & Transactions

##### A-7.1: Payments List
- All payments table:
  - Transaction ID
  - Investor name
  - Project/property
  - Amount
  - Currency
  - Payment type (Down payment / Installment X)
  - Payment date
  - Status (Pending / Completed / Failed / Refunded)
  - Payment method
  - Actions (View, Refund, Download receipt)
- Filters and search
- Export to CSV

##### A-7.2: Payment Detail View
- Transaction details
- Investor information
- Property information
- Payment method and gateway details
- Receipt/invoice download
- Refund option (if applicable)
- Internal notes

##### A-7.3: Payment Reminders
- Scheduled reminders for upcoming installments
- Configure reminder timing
- View sent reminders log

#### A-8: Documents Management
- All uploaded documents by investors
- Verification queue:
  - Pending verification
  - Verify/reject actions
  - Add notes
- Document categories
- Search and filter

#### A-9: Reports & Analytics

##### A-9.1: Investor Reports
- Investor acquisition over time
- Conversion rates
- Package distribution
- Geographic distribution

##### A-9.2: Financial Reports
- Revenue reports (by month, quarter, year)
- Payment collection rates
- Outstanding balances
- Refunds and chargebacks

##### A-9.3: Project Reports
- Most viewed projects
- Conversion by project
- Inventory status
- Project completion timeline

##### A-9.4: Custom Reports
- Report builder with filters
- Export to PDF/Excel
- Schedule automated reports

#### A-10: Settings

##### A-10.1: General Settings
- Site settings (name, logo, contact info)
- Email templates configuration
- Notification templates
- Currency exchange rate sync settings

##### A-10.2: Integration Settings
- Keycloak configuration
- Checkout.com API keys
- WhatsApp Business API credentials
- Unifonic SMS settings
- MoEngage email settings
- CRM integration credentials
- Currency API settings

##### A-10.3: User Roles & Permissions
- Manage roles (Super Admin, Content Manager, Account Manager, etc.)
- Permission matrix
- Assign roles to users

##### A-10.4: System Logs
- Audit trail
- API logs
- Error logs
- User activity logs

## Investment Packages Structure

### Virtual Tier (NEW - Remote Investment)
**Target**: Remote investors, time-constrained professionals, cost-conscious
**Price**: $1,000 USD (SAR 3,750) *- no travel required*

**Inclusions**:
- ✅ Full portal access with all features
- ✅ Shared account manager (remote support via email/WhatsApp/video)
- ✅ **8 virtual property tours** with HD video, 3D walkthroughs, drone footage
- ✅ 4-5 video consultation sessions (1 hour each)
- ✅ Complete digital documentation support with e-signatures
- ✅ Payment tracking and installment management
- ✅ Quarterly market reports and insights
- ✅ Full portfolio management tools
- ✅ Real-time property gains tracking

**What's NOT Included**:
- ❌ Physical site visits
- ❌ Visa support
- ❌ Travel arrangements or accommodation
- ❌ In-person meetings

**Duration**: Ongoing remote support

---

### Basic Tier
**Target**: First-time investors, smaller investment amounts
**Price**: $2,000 USD (SAR 7,500) *- flights not included*

**Inclusions**:
- ✅ Portal access with full features
- ✅ Dedicated account manager (shared, email/WhatsApp support)
- ✅ Basic visa consultancy (guidance and document checklist)
- ✅ Single participant (investor only)
- ✅ Saudi visit support:
  - Flight booking assistance (economy class)
  - 3-star hotel accommodation (3 nights)
  - Ground transportation (standard sedan)
  - 2 project site visits
  - Basic city tour (1 day)
- ✅ Payment tracking and reminders
- ✅ Documentation support
- ✅ Ownership transfer assistance

**Duration**: 4 days / 3 nights

### Top Tier
**Target**: Serious investors, mid to high investment amounts
**Price**: $7,500 USD (SAR 28,000) for 1 person *- flights not included*
**Additional person**: +$2,500 USD (SAR 9,500) per person (max 3 total)

**Inclusions**:
- ✅ All Basic Tier features
- ✅ Dedicated account manager (1:1, phone + WhatsApp + video calls)
- ✅ Full visa application handling (we submit for you)
- ✅ Two participants (investor + 1 companion)
- ✅ Premium Saudi visit:
  - Flight booking assistance (business class available)
  - 4-star hotel accommodation (5 nights)
  - Ground transportation (luxury sedan/SUV)
  - 4-5 project site visits
  - Extended city tour and cultural experiences (2 days)
  - Select restaurant dining experiences
  - VIP project presentations
- ✅ Priority documentation processing
- ✅ Quarterly portfolio review calls
- ✅ Exclusive project early access

**Duration**: 6 days / 5 nights

### Elite Tier
**Target**: High-net-worth investors, multiple property investments
**Price**: $25,000 USD (SAR 95,000) for 1 person *- flights not included*
**Additional person**: +$5,500 USD (SAR 20,000) per person (max 5 total)

**Inclusions**:
- ✅ All Top Tier features
- ✅ Senior account manager with 24/7 availability
- ✅ Concierge service for complete visa handling for entire family
- ✅ Five participants (investor + 4 family members/associates)
- ✅ Luxury Saudi experience:
  - Business/First class flights
  - 5-star hotel accommodation (7 nights)
  - Private chauffeur and luxury vehicle
  - Unlimited project site visits
  - Comprehensive cultural and entertainment itinerary:
    - Historical sites (UNESCO heritage sites)
    - Entertainment cities (e.g., Boulevard Riyadh City)
    - Premium dining experiences
    - Desert safari or yacht experience
    - Personal shopping assistance
  - VIP developer meetings
- ✅ Fast-track documentation and legal processing
- ✅ Monthly portfolio review with market insights
- ✅ Exclusive off-market opportunities
- ✅ Post-ownership property management service (1 year included)
- ✅ Annual investor summit invitation
- ✅ Referral incentives

**Duration**: 7 days / 7 nights (up to 1 week)

### Package Comparison Table

| Feature | **Virtual** | **Basic** | **Top** | **Elite** |
|---------|-------------|-----------|---------|-----------|
| **Base Price (USD)** | **$1,000** | **$2,000** | **$7,500** | **$25,000** |
| **Base Price (SAR)** | **3,750** | **7,500** | **28,000** | **95,000** |
| **Additional Person** | N/A | N/A | +$2,500 | +$5,500 |
| **Max Participants** | 1 (digital) | 1 | 3 | 5 |
| **Visit Type** | Remote only | In-person | In-person | In-person |
| **Duration** | Ongoing | 4 days | 6 days | 7 days |
| Portal Access | ✅ | ✅ | ✅ | ✅ |
| Virtual Tours | ✅ 8 tours | ❌ | Optional | Optional |
| Physical Site Visits | ❌ | 2 visits | 4-5 visits | Unlimited |
| Account Manager | Shared (remote) | Shared | Dedicated | Senior 24/7 |
| Visa Support | ❌ | Consultancy | Full handling | Family concierge |
| Hotel Rating | N/A | 3-star | 4-star | 5-star |
| Transportation | N/A | Standard | Luxury sedan | Private chauffeur |
| Video Consultations | ✅ 4-5 sessions | ❌ | ✅ | ✅ Unlimited |
| Dining | N/A | Meals included | Premium dining | Fine dining |
| Documentation | Digital only | Support | Priority | Fast-track |
| Portfolio Reviews | Quarterly | On-demand | Quarterly | Monthly + insights |
| Property Management | Paid add-on | Paid add-on | Paid add-on | 1 year included |
| Early Access | ❌ | ❌ | ✅ | ✅ + Off-market |
| **Perfect For** | Remote investors | First-timers | Serious investors | HNW/Families |

## User Flows

### Flow 1: New Investor Journey (Happy Path)

1. **Discovery**: User lands on public website
2. **Interest**: Views projects, reads about investment opportunities
3. **Lead Submission**: Fills lead form with contact details
4. **Sign Up**: Clicks "Join Investor Club" → Redirects to Keycloak
5. **Registration**: Completes registration on Keycloak
6. **Portal Access**: Redirected back to portal with JWT token
7. **Onboarding**: Welcome screen, brief tutorial/tour
8. **Package Selection**: Chooses Basic/Top/Elite tier
9. **Profile Completion**: Adds personal information, contact details
10. **Account Manager Assignment**: Receives notification, sees manager details
11. **Initial Contact**: Account manager reaches out via WhatsApp/email
12. **Project Browsing**: Explores available projects in portal
13. **Consultation**: Discusses options with account manager
14. **Property Selection**: Selects property, expresses interest
15. **Visa Process** (if applicable):
    - Uploads required documents (passport, ID)
    - Manager guides through visa application
    - Visa approved
16. **Travel Booking** (if applicable):
    - Flights booked, receives e-tickets
    - Hotel confirmed, receives confirmation
    - Itinerary shared
17. **Site Visit** (if applicable):
    - Travels to Saudi Arabia
    - Guided project tours
    - Cultural experiences
    - Final property decision
18. **Down Payment**:
    - Receives payment request
    - Makes down payment via Checkout.com
    - Receives confirmation and receipt
19. **Contract & Documentation**:
    - Reviews and signs contract (digital signature)
    - Uploads additional required documents
    - Legal team processes
20. **Installment Setup**:
    - Installment schedule generated
    - Receives payment reminders
    - Makes installment payments on time
21. **Construction Updates**:
    - Receives progress updates
    - Views completion percentage in portfolio
22. **Ownership Transfer**:
    - Property completed
    - Final payment made
    - Title deed processed and transferred
    - Receives ownership documents
23. **Post-Ownership Options**:
    - Opts for property management by Bayut
    - Property rented out, receives rental income
    - Views rental reports in portal

### Flow 2: Returning Investor (Multiple Properties)

1. **Login**: Existing investor logs into portal
2. **Portfolio Review**: Checks current properties and gains
3. **New Opportunity**: Sees new project featured on dashboard
4. **Project Details**: Explores new project
5. **Quick Decision**: Already familiar with process, expresses interest
6. **Fast-Track**: Existing documents and visa available
7. **Purchase**: Selects property, makes down payment
8. **Tracking**: Tracks new property in portfolio alongside existing ones

### Flow 3: Admin Managing Investor

1. **Login**: Content manager logs into admin panel
2. **Dashboard**: Views pending tasks
3. **New Lead**: Sees new lead from landing page
4. **Lead Review**: Opens lead details, assigns to account manager
5. **Investor Conversion**: Lead converts, investor signs up
6. **Document Verification**: Content manager reviews uploaded passport
7. **Approval**: Verifies and approves document
8. **Notification**: Investor receives approval notification
9. **Payment Tracking**: Monitors payment received
10. **Updates**: Updates investor journey timeline manually if needed

## Data Models (Key Entities)

### User
- id (UUID)
- keycloak_id (string, unique)
- email (string, unique)
- phone (string)
- first_name (string)
- last_name (string)
- country (string)
- nationality (string)
- date_of_birth (date)
- profile_photo_url (string)
- role (enum: investor, admin, content_manager, account_manager)
- status (enum: active, pending_verification, suspended)
- package_tier_id (foreign key)
- account_manager_id (foreign key)
- preferred_language (enum: en, ar, ru, zh)
- preferred_currency (string)
- email_verified (boolean)
- phone_verified (boolean)
- created_at (datetime)
- updated_at (datetime)

### PackageTier
- id (UUID)
- name (string: Basic, Top, Elite)
- description (text, multi-language)
- price (decimal, nullable)
- features (JSON)
- participants_count (integer)
- hotel_star_rating (integer)
- trip_duration_days (integer)
- flight_class (string)
- transportation_type (string)
- site_visits_count (integer)
- visa_support_level (string)
- is_active (boolean)
- sort_order (integer)
- created_at (datetime)
- updated_at (datetime)

### Project
- id (UUID)
- name (string, multi-language)
- slug (string, unique)
- developer_name (string)
- description (text, multi-language)
- location (string)
- city (string)
- free_zone_area (string)
- latitude (decimal)
- longitude (decimal)
- hero_image_url (string)
- gallery_images (JSON array of URLs)
- master_plan_images (JSON array of URLs)
- video_urls (JSON array)
- features (JSON, multi-language)
- amenities (JSON)
- price_range_min (decimal, SAR)
- price_range_max (decimal, SAR)
- expected_roi_percentage (decimal)
- payment_plan_description (text)
- down_payment_percentage (decimal)
- installment_schedule (JSON)
- start_date (date)
- expected_completion_date (date)
- current_progress_percentage (integer)
- status (enum: draft, published, archived)
- view_count (integer)
- documents (JSON array of document objects)
- meta_title (string)
- meta_description (text)
- created_by (foreign key to User)
- created_at (datetime)
- updated_at (datetime)

### PropertyType (Unit)
- id (UUID)
- project_id (foreign key)
- name (string, multi-language)
- unit_type (enum: apartment, villa, townhouse, land_plot, studio, other)
- size_sqft (decimal)
- size_sqm (decimal)
- bedrooms (integer)
- bathrooms (integer)
- description (text, multi-language)
- price_sar (decimal)
- availability_status (enum: available, sold_out, coming_soon)
- stock_count (integer)
- floor_plans (JSON array of URLs)
- specifications (JSON, multi-language)
- gallery_images (JSON array of URLs)
- sort_order (integer)
- created_at (datetime)
- updated_at (datetime)

### InvestorProperty (Portfolio)
- id (UUID)
- investor_id (foreign key to User)
- project_id (foreign key)
- property_type_id (foreign key)
- purchase_date (date)
- purchase_price_sar (decimal)
- current_estimated_value_sar (decimal)
- gain_loss_amount (decimal, calculated)
- gain_loss_percentage (decimal, calculated)
- status (enum: off_plan, under_construction, ready, owned)
- completion_percentage (integer)
- payment_status (enum: fully_paid, installments_active, pending)
- ownership_transferred (boolean)
- ownership_transfer_date (date)
- title_deed_document_url (string)
- contract_document_url (string)
- property_management_opted (boolean)
- created_at (datetime)
- updated_at (datetime)

### InvestorJourney
- id (UUID)
- investor_id (foreign key)
- investor_property_id (foreign key, nullable)
- current_stage (enum: lead_submitted, package_selected, manager_assigned, property_selected, visa_process, travel_arranged, site_visit, down_payment, installments, documentation, ownership_transfer, post_ownership)
- created_at (datetime)
- updated_at (datetime)

### JourneyStage (timeline entries)
- id (UUID)
- investor_journey_id (foreign key)
- stage_name (string)
- stage_type (enum: same as current_stage)
- status (enum: not_started, in_progress, completed, n_a)
- started_at (datetime)
- completed_at (datetime)
- notes (text)
- metadata (JSON) - flexible field for stage-specific data
- created_at (datetime)
- updated_at (datetime)

### VisaApplication
- id (UUID)
- investor_id (foreign key)
- investor_journey_id (foreign key)
- application_status (enum: not_started, documents_pending, submitted, under_review, approved, rejected)
- application_date (date)
- approval_date (date)
- visa_expiry_date (date)
- visa_number (string)
- notes (text)
- created_at (datetime)
- updated_at (datetime)

### TravelBooking
- id (UUID)
- investor_id (foreign key)
- investor_journey_id (foreign key)
- flight_pnr (string)
- flight_details (JSON)
- departure_date (datetime)
- return_date (datetime)
- ticket_document_url (string)
- hotel_name (string)
- hotel_star_rating (integer)
- hotel_location (string)
- check_in_date (date)
- check_out_date (date)
- hotel_confirmation_url (string)
- itinerary (JSON) - day-by-day schedule
- transportation_details (JSON)
- booking_status (enum: pending, confirmed, completed, cancelled)
- created_at (datetime)
- updated_at (datetime)

### Payment
- id (UUID)
- investor_id (foreign key)
- investor_property_id (foreign key)
- transaction_id (string, unique)
- payment_gateway (string: checkout.com)
- gateway_transaction_id (string)
- payment_type (enum: down_payment, installment, other)
- installment_number (integer, nullable)
- amount_sar (decimal)
- amount_paid (decimal)
- currency_paid (string)
- exchange_rate (decimal)
- payment_date (datetime)
- due_date (date)
- status (enum: pending, completed, failed, refunded, overdue)
- payment_method (string: card, bank_transfer, etc.)
- receipt_url (string)
- notes (text)
- created_at (datetime)
- updated_at (datetime)

### InstallmentSchedule
- id (UUID)
- investor_property_id (foreign key)
- installment_number (integer)
- due_date (date)
- amount_sar (decimal)
- status (enum: upcoming, due, paid, overdue)
- payment_id (foreign key, nullable)
- reminder_sent (boolean)
- created_at (datetime)
- updated_at (datetime)

### Document
- id (UUID)
- user_id (foreign key)
- document_type (enum: passport, national_id, visa, contract, title_deed, other)
- document_category (string)
- file_name (string)
- file_url (string)
- file_size (integer)
- file_type (string)
- verification_status (enum: pending, verified, rejected)
- verified_by (foreign key to User, nullable)
- verified_at (datetime)
- rejection_reason (text)
- uploaded_at (datetime)
- created_at (datetime)
- updated_at (datetime)

### AccountManager
- id (UUID)
- user_id (foreign key)
- name (string)
- photo_url (string)
- email (string)
- phone (string)
- whatsapp_number (string)
- department (string)
- working_hours (string)
- bio (text)
- is_active (boolean)
- created_at (datetime)
- updated_at (datetime)

### Lead
- id (UUID)
- name (string)
- email (string)
- phone (string)
- country (string)
- investment_interest (text)
- status (enum: new, contacted, qualified, converted, lost)
- source (string: landing_page, referral, etc.)
- assigned_manager_id (foreign key)
- notes (text)
- converted_to_investor_id (foreign key, nullable)
- created_at (datetime)
- updated_at (datetime)

### FAQ
- id (UUID)
- question (text, multi-language)
- answer (text, multi-language)
- category (string)
- sort_order (integer)
- is_published (boolean)
- created_at (datetime)
- updated_at (datetime)

### Article
- id (UUID)
- title (string, multi-language)
- slug (string, unique)
- content (text, multi-language)
- excerpt (text, multi-language)
- featured_image_url (string)
- category (string)
- tags (JSON array)
- author_id (foreign key to User)
- published_at (datetime)
- view_count (integer)
- is_published (boolean)
- meta_title (string)
- meta_description (text)
- created_at (datetime)
- updated_at (datetime)

### Testimonial
- id (UUID)
- investor_name (string)
- investor_photo_url (string)
- testimonial_text (text, multi-language)
- video_url (string, nullable)
- rating (integer, 1-5)
- is_published (boolean)
- sort_order (integer)
- created_at (datetime)
- updated_at (datetime)

### Notification
- id (UUID)
- user_id (foreign key)
- title (string)
- message (text)
- notification_type (enum: payment_reminder, journey_update, document_required, general)
- is_read (boolean)
- link (string, nullable)
- sent_at (datetime)
- created_at (datetime)

### SupportTicket
- id (UUID)
- user_id (foreign key)
- subject (string)
- category (string)
- message (text)
- status (enum: open, in_progress, resolved, closed)
- assigned_to (foreign key to User, nullable)
- attachments (JSON array)
- created_at (datetime)
- updated_at (datetime)

### TicketReply
- id (UUID)
- ticket_id (foreign key)
- user_id (foreign key)
- message (text)
- attachments (JSON array)
- is_staff_reply (boolean)
- created_at (datetime)

### SystemSettings
- id (UUID)
- key (string, unique)
- value (text/JSON)
- description (text)
- updated_at (datetime)

### AuditLog
- id (UUID)
- user_id (foreign key)
- action (string)
- entity_type (string)
- entity_id (UUID)
- changes (JSON)
- ip_address (string)
- user_agent (string)
- created_at (datetime)

## Multi-Language Support

### Supported Languages (Phase 1)
1. **English (en)** - Primary, default
2. **Arabic (ar)** - RTL support required
3. **Russian (ru)**
4. **Chinese (zh)** - Simplified Chinese

### Implementation Strategy
- **Frontend**: Use `react-i18next` for React portal and admin, `next-i18next` for Next.js landing page
- **Backend**: Store translations in database for dynamic content (projects, articles, FAQs)
- **Translation Files**: JSON files for static UI strings
- **Database Schema**: 
  - Multi-language fields stored as JSON: `{en: "text", ar: "نص", ru: "текст", zh: "文本"}`
  - Or separate translation tables with foreign keys
- **Content Management**: Admin panel allows content managers to input content in all languages
- **User Preference**: Users select language in settings, stored in user profile
- **Dynamic Loading**: Load language bundle on demand to optimize performance

### RTL (Right-to-Left) Support for Arabic
- Use CSS logical properties
- Ant Design supports RTL via `direction="rtl"` in ConfigProvider
- Mirror layouts and icons where appropriate
- Test all forms, tables, and complex layouts in RTL mode

## Multi-Currency Support

### Supported Currencies
- **SAR** (Saudi Riyal) - Base currency, all data stored in SAR
- **USD** (US Dollar)
- **AUD** (Australian Dollar)
- **AED** (UAE Dirham)
- **GBP** (British Pound)
- **CAD** (Canadian Dollar)
- **QAR** (Qatari Riyal)
- **INR** (Indian Rupee)
- **PKR** (Pakistani Rupee)

### Implementation
- **Storage**: All financial data stored in SAR in database
- **Display**: Convert to user's preferred currency on the fly
- **Exchange Rates**: 
  - Fetch from external API (e.g., exchangerate-api.io, fixer.io)
  - Cache rates for 24 hours
  - Update daily via scheduled job
  - Store historical rates for accurate historical data
- **User Preference**: User selects preferred currency in settings
- **Conversion**: 
  - Display prices in selected currency
  - Show SAR equivalent for transparency
  - At payment time, charge in SAR via Checkout.com
  - Display converted amount for reference
- **Formatting**: Use proper currency symbols and formatting per locale

## Third-Party Integrations

### 1. Keycloak (Authentication)
**Purpose**: User authentication and authorization
**Integration Type**: OAuth 2.0 / OpenID Connect
**Flow**:
1. User clicks login/signup
2. Redirect to Keycloak authentication page
3. User completes authentication
4. Keycloak redirects back with authorization code
5. Exchange code for JWT access token
6. Frontend stores token (secure HttpOnly cookie or localStorage)
7. Backend validates JWT on each API request

**MVP**: Hardcode a test user, implement full integration in Phase 2

### 2. Checkout.com (Payment Gateway)
**Purpose**: Process international payments
**Integration Type**: RESTful API
**Implementation**:
- Use Checkout.com SDK (Node.js or direct API calls from Rails)
- Payment flow:
  1. Frontend initiates payment
  2. Backend creates payment session via Checkout.com API
  3. Return session ID to frontend
  4. Frontend opens Checkout.com payment widget (iframe/redirect)
  5. User completes payment
  6. Checkout.com sends webhook to backend
  7. Backend validates webhook, updates payment status
  8. Frontend polls or uses WebSocket to get status update
- **Security**: Store API keys in environment variables, use webhook signature validation
- **Currencies**: Charge in SAR, but Checkout.com supports multi-currency display

### 3. WhatsApp Business API
**Purpose**: Direct communication with investors
**Integration Type**: RESTful API (via official WhatsApp Business API provider)
**Use Cases**:
- Send notifications (payment reminders, journey updates)
- One-click WhatsApp button (opens chat with account manager)
- Two-way messaging (optional)
**Implementation**:
- Use official WhatsApp Business API provider (Twilio, MessageBird, etc.)
- Send template messages (pre-approved by WhatsApp)
- Backend triggers messages via API
- Handle delivery status via webhooks

### 4. Unifonic (SMS Provider)
**Purpose**: Send SMS notifications
**Integration Type**: RESTful API
**Use Cases**:
- OTP verification (phone verification)
- Payment reminders
- Critical journey updates
**Implementation**:
- Unifonic API endpoints for sending SMS
- Backend service to queue and send SMS
- Handle delivery reports

### 5. MoEngage (Email Marketing)
**Purpose**: Send transactional and marketing emails
**Integration Type**: RESTful API or SMTP
**Use Cases**:
- Welcome emails
- Payment confirmations and receipts
- Journey milestone emails
- Newsletter and announcements
**Implementation**:
- Integrate MoEngage SDK/API
- Create email templates in MoEngage dashboard
- Backend triggers email campaigns
- Track opens, clicks, conversions

### 6. In-house CRM
**Purpose**: Sync investor data, manage leads and payments internally
**Integration Type**: RESTful API (to be provided by Bayut)
**Data to Sync**:
- New leads from landing page
- Investor details and status
- Payments and transactions
- Journey milestones
**Implementation**:
- Backend makes API calls to CRM on specific events
- Use background jobs (Sidekiq) for async processing
- Handle authentication (API keys, OAuth)
- Implement retry logic for failed syncs

### 7. Currency Exchange API
**Purpose**: Fetch real-time exchange rates
**Options**: exchangerate-api.io, fixer.io, currencylayer, etc.
**Integration Type**: RESTful API
**Implementation**:
- Scheduled job (daily) fetches latest rates
- Store rates in database (CurrencyExchangeRate model)
- Cache rates in Redis for fast access
- Fallback to last known rates if API fails

### 8. AWS S3 (File Storage)
**Purpose**: Store uploaded documents, images, videos
**Integration Type**: AWS SDK (aws-sdk gem for Rails)
**Implementation**:
- Use Active Storage with S3 adapter
- Generate presigned URLs for secure uploads
- Set appropriate bucket policies (private for documents, public for project images with CloudFront)
- Organize by folders: `/documents/`, `/projects/`, `/profiles/`, etc.

### 9. Google Maps API (Optional)
**Purpose**: Display project locations, map picker in admin
**Integration Type**: JavaScript API
**Implementation**:
- Embed maps on project detail pages
- Map picker for adding project locations in admin
- Store latitude/longitude in database

## Security Considerations

### Authentication & Authorization
- JWT token validation on every API request
- Refresh token mechanism (if supported by Keycloak)
- Role-based access control (RBAC) for different user types
- Session management and timeout

### Data Protection
- Encrypt sensitive data at rest (passwords, documents)
- Use HTTPS/TLS for all communications
- Secure file uploads (validate file types, scan for malware)
- PII (Personally Identifiable Information) handling per regulations

### Payment Security
- PCI DSS compliance via Checkout.com (they handle card data)
- Never store full credit card details
- Validate payment webhooks using signature verification
- Prevent duplicate payments (idempotency)

### API Security
- Rate limiting to prevent abuse
- Input validation and sanitization (prevent SQL injection, XSS)
- CORS configuration (allow only trusted domains)
- API authentication for third-party integrations

### Document Security
- Private S3 buckets for sensitive documents
- Presigned URLs with expiration for document access
- Access control: users can only view their own documents
- Admin access logging

### Admin Panel Security
- Strong authentication for admin users
- Activity audit logs (who did what, when)
- IP whitelisting (optional, for super admin)
- Two-factor authentication (future enhancement)

## Performance Optimization

### Frontend
- Code splitting and lazy loading (React.lazy)
- Image optimization (WebP format, responsive images)
- CDN for static assets (CloudFront)
- Minimize bundle size (tree shaking, remove unused libraries)
- Caching strategies (service workers for PWA, future)

### Backend
- Database indexing on frequently queried fields
- N+1 query prevention (use eager loading)
- Redis caching for:
  - Currency exchange rates
  - Project listings
  - User sessions
- Background jobs for:
  - Email/SMS sending
  - CRM sync
  - Payment processing
  - Report generation
- API response pagination
- Database connection pooling

### Infrastructure
- Auto-scaling EC2 instances based on load
- RDS read replicas for read-heavy operations
- CloudFront CDN for global content delivery
- Load balancer for distributing traffic
- Database query optimization and monitoring

## Testing Strategy

### Frontend Testing
- **Unit Tests**: Jest + React Testing Library for components
- **Integration Tests**: Test user flows (Cypress or Playwright)
- **Visual Regression**: Storybook + Chromatic (optional)
- **Accessibility**: axe-core for WCAG compliance

### Backend Testing
- **Unit Tests**: RSpec for models, services
- **Controller Tests**: RSpec for API endpoints
- **Integration Tests**: Request specs
- **Test Coverage**: Aim for >80% coverage (SimpleCov)

### End-to-End Testing
- Cypress for critical user journeys:
  - Lead submission
  - User signup and login
  - Project browsing and filtering
  - Payment flow (using test mode)
  - Document upload

### Manual Testing
- Cross-browser testing (Chrome, Firefox, Safari, Edge)
- Mobile responsive testing (iOS, Android)
- Multi-language testing (all 4 languages)
- RTL layout testing (Arabic)
- Payment gateway testing (Checkout.com test mode)

### Performance Testing
- Load testing (JMeter, k6) for API endpoints
- Frontend performance audits (Lighthouse)
- Database query performance (Rails query logs, database slow query logs)

## Deployment & DevOps

### Environments
1. **Development**: Local machines
2. **Staging**: AWS staging environment (mirrors production)
3. **Production**: AWS production environment

### CI/CD Pipeline
- **Version Control**: Git (GitHub, GitLab, or Bitbucket)
- **CI/CD Tool**: GitHub Actions, GitLab CI, or AWS CodePipeline
- **Pipeline Steps**:
  1. Code push to repository
  2. Run linters (RuboCop for Rails, ESLint for JS)
  3. Run automated tests
  4. Build frontend (npm run build)
  5. Build Docker images (optional)
  6. Deploy to staging on merge to `develop` branch
  7. Deploy to production on merge to `main` branch (manual approval)
- **Deployment Strategy**: Blue-green or rolling deployment

### Monitoring & Logging
- **Application Monitoring**: New Relic, Datadog, or AWS X-Ray
- **Error Tracking**: Sentry or Rollbar
- **Logging**: AWS CloudWatch Logs, ELK stack
- **Uptime Monitoring**: Pingdom, UptimeRobot
- **Alerts**: Slack/email notifications for critical errors

### Backup & Disaster Recovery
- Automated daily database backups (RDS snapshots)
- S3 versioning for documents
- Backup retention policy (30 days)
- Disaster recovery plan and runbook

## Development Phases

### Phase 1: MVP (Minimum Viable Product)
**Duration**: 12-16 weeks
**Goal**: Launch with core features to start acquiring investors

**Scope**:
- Landing page (Next.js):
  - Hero, projects showcase, packages, FAQs, lead form
  - English language only initially
  - Basic responsive design
- Investor Portal (React):
  - Hardcoded authentication (test user)
  - Projects section (list, detail, filters)
  - Basic investor tracker (manual updates via admin)
  - Portfolio section (basic)
  - Profile section
  - Help center (FAQs, account manager card, contact)
  - English language only
- Admin Panel:
  - Super admin login
  - Projects CRUD (content manager)
  - Property types CRUD
  - Investors list and detail view
  - Basic lead management
  - Document verification
  - Basic payment tracking
- Backend:
  - Rails API with core endpoints
  - MySQL database with key models
  - Checkout.com integration (test mode)
  - Basic email notifications (MoEngage)
  - File upload to S3
- Deployment:
  - AWS infrastructure setup
  - Staging and production environments
  - Basic CI/CD pipeline

**Not in Phase 1**:
- Keycloak integration (use hardcoded user)
- WhatsApp Business API
- SMS notifications
- CRM integration
- Multi-language support (add in Phase 2)
- Complete investor tracker automation
- Advanced reporting and analytics

### Phase 2: Full Feature Set
**Duration**: 8-12 weeks after MVP launch
**Goal**: Complete all planned features

**Additions**:
- Keycloak authentication integration
- Multi-language support (Arabic, Russian, Chinese)
- Multi-currency display
- WhatsApp Business API integration
- SMS notifications via Unifonic
- CRM integration
- Complete investor tracker automation
- Travel booking management
- Real-time currency exchange rates
- Advanced analytics and reporting
- Enhanced admin panel features
- Email templates and automation

### Phase 3: Enhancements & Optimizations
**Duration**: Ongoing
**Goal**: Improve based on user feedback and business needs

**Potential Features**:
- Mobile apps (iOS, Android)
- Live chat support
- Video consultation booking
- AI-powered investment recommendations
- Investor community forum
- Referral program
- Advanced property management module
- Payment installment calculators
- Investment portfolio analytics and forecasting
- VR/AR property tours
- Blockchain-based ownership records (future tech)

## Success Metrics & KPIs

### Business Metrics
- Number of leads generated (monthly)
- Lead to signup conversion rate
- Signup to first investment conversion rate
- Average investment amount per investor
- Revenue per package tier
- Customer lifetime value (CLV)
- Investor retention rate
- Number of properties sold through platform

### Product Metrics
- Monthly active users (MAU)
- Average session duration
- Pages per session
- Bounce rate on landing page
- Feature adoption rates:
  - Investors using tracker
  - Investors viewing portfolio
  - Investors contacting account manager
- Document upload completion rate
- Payment success rate
- Customer satisfaction score (CSAT)
- Net Promoter Score (NPS)

### Technical Metrics
- Page load time (aim for <3 seconds)
- API response time (aim for <500ms)
- Error rate (aim for <1%)
- Uptime (aim for 99.9%)
- Test coverage (aim for >80%)

## Compliance & Legal

### Terms & Conditions
- User agreement for portal access
- Investment terms and disclaimers
- Refund and cancellation policy
- Service level agreements for each package tier

### Privacy Policy
- Data collection and usage
- Cookie policy
- Third-party data sharing (payment processors, CRM)
- User rights (access, deletion, portability)
- Data retention policy

### Regulatory Compliance
- Bayut.sa is a certified real estate platform in Saudi Arabia
- Compliance with Saudi real estate investment regulations
- Free Zone investment laws and requirements
- KYC (Know Your Customer) basic verification:
  - Email and phone verification for portal access
  - National ID and passport required for visa process
  - Admin moderation of submitted documents

### Legal Documents
- Property purchase contracts (digital signature)
- Visa application forms
- Travel booking terms
- Property management agreements
- Data processing agreements (for third-party services)

## Risks & Mitigation

### Technical Risks
- **Risk**: Third-party API downtime (Keycloak, Checkout.com)
  - **Mitigation**: Implement retry logic, fallback mechanisms, clear user communication
- **Risk**: Data breach or security vulnerability
  - **Mitigation**: Regular security audits, penetration testing, bug bounty program
- **Risk**: Database performance issues at scale
  - **Mitigation**: Proper indexing, query optimization, read replicas, caching

### Business Risks
- **Risk**: Low investor adoption
  - **Mitigation**: Strong marketing, compelling USPs, early adopter incentives
- **Risk**: Payment fraud or chargebacks
  - **Mitigation**: KYC verification, fraud detection tools, clear refund policies
- **Risk**: Regulatory changes in Saudi Arabia
  - **Mitigation**: Legal team monitoring, flexible platform architecture to adapt

### Operational Risks
- **Risk**: Account managers overwhelmed with inquiries
  - **Mitigation**: Adequate staffing, self-service features, automated FAQs
- **Risk**: Document processing delays
  - **Mitigation**: Clear timelines, automated workflows, status transparency
- **Risk**: Travel/visa service issues
  - **Mitigation**: Partner with reliable service providers, contingency plans

## Future Considerations

### Scalability
- Microservices architecture (if monolith becomes bottleneck)
- Database sharding (if data grows significantly)
- Multi-region deployment (for global investors)

### Advanced Features
- AI/ML for investment recommendations
- Predictive analytics for property value forecasting
- Blockchain for transparent ownership records
- VR property tours
- Investor mobile app with push notifications
- Social features (investor community, forums)

### Market Expansion
- Expand beyond Free Zones to other Saudi properties
- Support for other GCC countries
- Commercial real estate investments
- REITs (Real Estate Investment Trusts) integration

## Conclusion

Investor's Hub is a comprehensive, end-to-end platform designed to democratize and simplify real estate investment in Saudi Arabia's Free Zones for international investors. By combining transparency, expert guidance, and white-glove services, Bayut aims to build trust and become the go-to platform for diaspora and expat investors.

The platform's phased approach ensures a timely MVP launch while allowing for continuous improvement and feature additions based on user feedback and business growth.

---

**Document Version**: 1.0  
**Last Updated**: October 4, 2025  
**Author**: Bayut.sa Product Team  
**Status**: Approved for Development

