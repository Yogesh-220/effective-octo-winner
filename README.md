# Commission Calculation System 

## 🎯 Project Overview

We are looking for talented interns to develop a comprehensive **Commission Calculation System** for insurance/financial services companies. This is a **technical assessment project** to evaluate your problem-solving skills, coding ability, and understanding of complex business requirements.

### Project Focus Areas

#### **Frontend Development (React/TypeScript)**
- **Focus**: React frontend development with TypeScript
- **Skills**: React, TypeScript, Tailwind CSS, UI/UX design
- **Responsibilities**: Build responsive UI, data visualization, user experience
- **UI/UX is EQUALLY IMPORTANT** - We need beautiful, professional interfaces

#### **Backend Development (Python/Flask)**
- **Focus**: Python backend development with Flask
- **Skills**: Python, Flask, SQLAlchemy, SQLite, API development
- **Responsibilities**: Build REST APIs, database design, business logic
- **Backend is EQUALLY IMPORTANT** - Robust, scalable architecture

### Selection Process
- **Submit your solution** within 7 days
- **Technical interview** to discuss your approach
- **Code review** of your implementation
- **Selection based on** code quality, problem-solving, and interview performance

### What You'll Build
A full-stack web application that demonstrates sophisticated commission calculation logic with:
- **Agent hierarchy management** (4 levels: Agent → Team Lead → Manager → Director)
- **Volume-based bonus calculations** (Monthly, Quarterly, Annual)
- **Override bonuses** for management levels
- **Advanced clawback system** for policy cancellations
- **Real-time analytics dashboard** with visualizations

---

## 🏢 Insurance Industry Primer

### What is Insurance?
Insurance is a financial product that protects people and businesses from financial losses. When you buy insurance, you pay a premium (monthly/yearly payment) to an insurance company. In return, the company promises to pay for covered losses.

**Example**: You buy life insurance for $200/month. If you die, the insurance company pays $500,000 to your family instead of them facing financial hardship.

### Types of Insurance Products
- **Life Insurance**: Pays money to your family when you die (PRIMARY FOCUS - this is where FYC is most common)
- **Health Insurance**: Covers medical expenses
- **Auto Insurance**: Covers car accidents and damage
- **Home Insurance**: Covers house damage from fires, storms, etc.
- **Business Insurance**: Protects companies from various risks

### How Insurance Companies Make Money
1. **Premiums**: Customers pay monthly/yearly fees
2. **Investments**: Company invests the premium money
3. **Claims Management**: Paying out less in claims than collected in premiums

---

## 💰 Understanding Commissions in Insurance

### What is FYC (First Year Commission)?
**FYC = First Year Commission** - This is the commission an insurance agent earns when they sell a new insurance policy.

**Key Points:**
- **Only paid ONCE** - when the policy is first sold
- **Not recurring** - agent doesn't get paid every month
- **Based on policy value** - higher value policies = higher commission
- **Subject to clawback** - if policy cancels, commission must be returned

### Commission Structure Example
```
Life Insurance Policy Premium: $2,400/year ($200/month)
FYC Rate: 50% (varies by company)
Agent Commission: $2,400 × 50% = $1,200

This $1,200 is paid ONCE when the life insurance policy is sold.
Agent does NOT get $1,200 every year.
```

### Why FYC Exists
- **Motivates sales** - agents earn money for selling new policies
- **Covers sales costs** - agent's time, marketing, office expenses
- **One-time reward** - for bringing in new customers
- **Risk sharing** - agent gets paid upfront, company gets ongoing premiums

---

## 🏗️ Insurance Agent Hierarchy

### The Sales Organization Structure
Insurance companies organize their sales teams in a hierarchy (like a pyramid):

```
                    DIRECTOR (Level 4)
                         |
                    MANAGER (Level 3)
                         |
                   TEAM LEAD (Level 2)
                         |
                    AGENT (Level 1) ← Sells policies to customers
```

### Role Responsibilities

#### **Agent (Level 1)** - The Salesperson
- **Primary Role**: Sells life insurance policies to customers
- **Earns**: Direct FYC commission + volume bonuses
- **Example**: Sarah sells a $500,000 life insurance policy
- **Commission**: $500,000 × 50% = $250,000 FYC

#### **Team Lead (Level 2)** - Supervises Agents
- **Primary Role**: Manages 3-5 agents, helps with sales
- **Earns**: Own FYC + volume bonus + override bonus from team
- **Example**: Bob manages Sarah and 4 other agents
- **Override**: Gets 2% of all team sales as bonus

#### **Manager (Level 3)** - Manages Team Leads
- **Primary Role**: Manages multiple team leads
- **Earns**: Own FYC + volume bonus + override from entire team
- **Example**: Lisa manages Bob and 3 other team leads
- **Override**: Gets 1.5% of all manager's team sales

#### **Director (Level 4)** - Top Management
- **Primary Role**: Manages multiple managers, strategic planning
- **Earns**: Own FYC + volume bonus + override from entire region
- **Example**: Mike manages Lisa and 5 other managers
- **Override**: Gets 1% of all regional sales

---

## 🎯 The Business Problem We're Solving

### Current Industry Challenges

#### **Problem 1: Complex Commission Calculations**
**The Issue**: Insurance companies struggle to calculate commissions accurately because:
- Agents earn different rates based on their performance tier
- Managers earn overrides from their entire team
- Commissions are calculated monthly, quarterly, and annually
- Rates change based on volume thresholds

**Real Example**:
```
Sarah (Agent) sells $500,000 life insurance policy → Gets $250,000 FYC
Bob (Team Lead) gets 2% override → Gets $10,000 bonus
Lisa (Manager) gets 1.5% override → Gets $7,500 bonus
Mike (Director) gets 1% override → Gets $5,000 bonus

Total paid out: $272,500 for one $500,000 life insurance policy sale!
```

#### **Problem 2: The Clawback Nightmare**
**The Issue**: When customers cancel their insurance policies, companies must "claw back" (adjust) commissions from everyone who earned money from that sale.

**How Clawbacks Work**:
- Customer cancels life insurance policy after 6 months
- Company already paid $272,500 in commissions
- Company adjusts future bonuses to recover the money
- Must find ALL people who earned from this policy
- Must recalculate ALL bonuses affected by this cancellation
- **Clawbacks are deducted from current and future bonuses, not returned as cash**

**The Challenge**:
```
Life insurance policy cancelled after 6 months:
- Sarah's $250,000 FYC → Must be clawback from any new bonus at future month
- Bob's $10,000 override → Must be clawback from any new bonus at future month
- Lisa's $7,500 override → Must be clawback from any new bonus at future month
- Mike's $5,000 override → Must be clawback from any new bonus at future month
- PLUS: All volume bonuses affected by this policy
- PLUS: Recalculate tiers for all affected agents
```

#### **Problem 3: Manual Process Errors**
**Current Reality**: Most insurance companies use:
- Excel spreadsheets for calculations
- Manual data entry
- Human error in complex calculations
- Difficulty tracking policy cancellations
- Slow clawback processing (weeks/months)

**Result**: 
- Incorrect commission payments
- Lost money from unprocessed clawbacks
- Agent disputes and complaints
- Regulatory compliance issues

---

## 🚀 Our Solution: Automated Commission System

### What We're Building
A sophisticated software system that:

#### **1. Automates Commission Calculations**
- Calculates FYC commissions instantly
- Determines agent tiers based on volume
- Computes override bonuses for managers
- Handles monthly/quarterly/annual bonuses

#### **2. Tracks Everything**
- Records every policy sale with unique policy numbers
- Links each policy to all people who earned from it
- Maintains complete audit trail
- Stores hierarchy snapshots at time of sale

#### **3. Handles Clawbacks Automatically**
- Instantly finds all affected commissions when policy cancels
- Recalculates all bonuses across all time periods
- Creates clawback transactions automatically
- Maintains complete audit trail

#### **4. Provides Real-Time Analytics**
- Visual hierarchy representation
- Commission reports and summaries
- Volume tracking charts
- Clawback impact analysis

### Business Impact
**Before Our System**:
- Manual calculations take days/weeks
- Errors cost thousands of dollars
- Clawbacks take months to process
- Agents dispute payments

**After Our System**:
- Calculations complete in seconds
- 99.9% accuracy rate
- Clawbacks processed in minutes
- Complete transparency and audit trail

---

## 📊 Real-World Example Scenario

### The Sales Story
**January 2024**: Sarah (Agent) sells a $500,000 life insurance policy to John Smith.

**What Happens**:
1. **Immediate**: Sarah gets $250,000 FYC commission
2. **End of January**: Volume bonuses calculated
   - Sarah's January volume: $1,250,000 (including this policy)
   - Sarah's tier: Silver (2% bonus rate)
   - Sarah's monthly bonus: $1,250,000 × 2% = $25,000
3. **End of Q1**: Quarterly bonuses calculated
   - Sarah's Q1 volume: $4,000,000 (including this policy)
   - Sarah's tier: Gold (3% bonus rate)
   - Sarah's quarterly bonus: $4,000,000 × 3% = $120,000
4. **End of 2024**: Annual bonuses calculated
   - Sarah's 2024 volume: $15,000,000 (including this policy)
   - Sarah's tier: Platinum (5% bonus rate)
   - Sarah's annual bonus: $15,000,000 × 5% = $750,000

**Meanwhile, Sarah's Managers Also Earn**:
- Bob (Team Lead): Gets override bonuses on Sarah's volume
- Lisa (Manager): Gets override bonuses on entire team volume
- Mike (Director): Gets override bonuses on entire region volume

### The Cancellation Nightmare
**June 2025**: John Smith cancels his $500,000 life insurance policy after 18 months.

**The Clawback Challenge**:
Our system must find and adjust:
1. Sarah's original $250,000 FYC commission → Deduct from future bonuses
2. Sarah's January 2024 monthly bonus (affected by this policy) → Recalculate
3. Sarah's Q1 2024 quarterly bonus (affected by this policy) → Recalculate
4. Sarah's 2024 annual bonus (affected by this policy) → Recalculate
5. Bob's override bonuses from all affected periods → Adjust future bonuses
6. Lisa's override bonuses from all affected periods → Adjust future bonuses
7. Mike's override bonuses from all affected periods → Adjust future bonuses
8. Recalculate tiers for all affected agents
9. Create audit trail for compliance

**How Clawbacks Work**:
- **Not cash returns**: Money is deducted from current/future bonuses
- **Adjustment system**: Future earnings are reduced to recover past payments
- **Tier recalculation**: Agent tiers may drop due to reduced volume
- **Audit trail**: Complete record of all adjustments made

**Traditional System**: This would take weeks of manual work and likely have errors.

**Our System**: Completes this in seconds with 100% accuracy.

---

## 🎓 Why This Project Matters

### For Your Learning
- **Real Business Logic**: You'll learn how complex financial systems work
- **Full-Stack Development**: Backend APIs + Frontend interfaces
- **Database Design**: Complex relationships and data integrity
- **Problem Solving**: Handling edge cases and business rules

### For the Industry
- **Saves Money**: Reduces calculation errors and processing time
- **Improves Accuracy**: Eliminates human error in complex calculations
- **Ensures Compliance**: Maintains complete audit trails
- **Enhances Trust**: Agents trust accurate, transparent payments

### For Your Career
- **Portfolio Project**: Demonstrates complex business logic skills
- **Industry Knowledge**: Understanding of financial services
- **Technical Skills**: Full-stack development with real-world complexity
- **Problem-Solving**: Handling sophisticated business requirements

---

## 🛠️ Technical Stack

### Backend (Python/Flask) - EQUALLY IMPORTANT
- **Framework**: Flask (Python)
- **Database**: SQLite
- **ORM**: SQLAlchemy
- **API**: RESTful endpoints
- **Authentication**: JWT tokens

### Frontend (React/TypeScript) - EQUALLY IMPORTANT
- **Framework**: React 18+
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: Headless UI or Material-UI
- **Charts**: Chart.js or Recharts
- **State Management**: Redux Toolkit or Zustand
- **UI/UX Focus**: **Beautiful, professional, responsive design**

### Development Tools
- **Version Control**: Git
- **Package Manager**: npm/yarn (frontend), pip (backend)
- **Testing**: Jest (frontend), pytest (backend)
- **Code Quality**: ESLint, Prettier, Black (Python formatter)

---

## 📋 Project Requirements

### Core Features to Implement

#### 1. Agent Hierarchy Management
- Create, read, update, delete agents
- 4-level hierarchy: Agent (Level 1) → Team Lead (Level 2) → Manager (Level 3) → Director (Level 4)
- Self-referencing parent-child relationships
- Visual hierarchy tree display

#### 2. Sales Transaction System
- Record FYC (First Year Commission) sales
- Track policy numbers for clawback purposes
- Associate sales with selling agents
- Store hierarchy snapshots at time of sale

#### 3. Commission Calculation Engine
- **Direct FYC Commission**: Immediate payment to selling agent
- **Volume Bonuses**: Monthly, Quarterly, Annual based on total volume
- **Override Bonuses**: Management levels earn % of downline volume
- **Tier-based calculations**: Bronze/Silver/Gold/Platinum tiers per level

#### 4. Clawback System
- Handle policy cancellations
- Recalculate affected bonuses across all time periods
- Maintain audit trail of clawback transactions
- Fast lookup system using contribution tracking

#### 5. Analytics Dashboard
- Visual hierarchy representation
- Commission reports and summaries
- Volume tracking charts
- Clawback impact analysis

---

## 🎨 UI/UX Requirements (EQUALLY IMPORTANT)

### Design Principles
- **Clean and Professional**: Business-appropriate design
- **Responsive**: Works perfectly on desktop, tablet, and mobile
- **Intuitive Navigation**: Easy to understand hierarchy and data flow
- **Data Visualization**: Clear charts and graphs for analytics
- **Modern UI**: Use current design trends and best practices

### UI/UX Evaluation Criteria
- **Visual Appeal**: Beautiful, modern interface design
- **User Experience**: Intuitive navigation and interactions
- **Responsive Design**: Perfect on all device sizes
- **Data Presentation**: Clear, readable charts and tables
- **Professional Look**: Suitable for business environment

### Key Pages/Screens

#### 1. Dashboard
- Overview of total commissions paid
- Recent sales activity
- Hierarchy summary
- Quick stats cards
- **Beautiful charts and visualizations**

#### 2. Agent Management
- List of all agents with hierarchy visualization
- Add/Edit agent forms
- **Interactive hierarchy tree view**
- **Modern form designs**

#### 3. Sales Management
- Record new sales transactions
- View sales history
- Policy lookup functionality
- **Clean, user-friendly forms**

#### 4. Commission Reports
- Monthly/Quarterly/Annual reports
- Agent-specific commission history
- Volume bonus calculations
- **Professional data tables and charts**

#### 5. Clawback Management
- Policy cancellation interface
- Clawback impact analysis
- Approval workflow
- **Clear impact visualization**

---

## 📊 Sample Data & Scenarios

### Volume Tier Configuration
```python
# Agent Level 1 (Agents)
BRONZE: $0-$25K (0%), SILVER: $25K-$50K (2%), GOLD: $50K-$100K (3%), PLATINUM: $100K+ (5%)

# Agent Level 2 (Team Leads)  
BRONZE: $0-$100K (0%), SILVER: $100K-$250K (3%), GOLD: $250K-$500K (5%), PLATINUM: $500K+ (7%)

# Agent Level 3 (Managers)
BRONZE: $0-$500K (0%), SILVER: $500K-$1M (4%), GOLD: $1M-$2M (6%), PLATINUM: $2M+ (8%)

# Agent Level 4 (Directors)
BRONZE: $0-$1M (0%), SILVER: $1M-$3M (5%), GOLD: $3M-$5M (7%), PLATINUM: $5M+ (10%)
```

### Sample Hierarchy
```
Director (Level 4)
├── Manager 1 (Level 3)
│   ├── Team Lead 1 (Level 2)
│   │   ├── Agent 1 (Level 1)
│   │   └── Agent 2 (Level 1)
│   └── Team Lead 2 (Level 2)
│       ├── Agent 3 (Level 1)
│       └── Agent 4 (Level 1)
└── Manager 2 (Level 3)
    └── Team Lead 3 (Level 2)
        └── Agent 5 (Level 1)
```

---

## 🚀 Development Timeline - 1 Week Sprint

### Day 1: Foundation Setup
- [ ] Set up Flask backend with SQLAlchemy
- [ ] Create SQLite database with all 7 tables
- [ ] Set up React frontend with TypeScript
- [ ] Implement basic CRUD operations for agents
- [ ] Create simple hierarchy visualization

### Day 2-3: Core Features
- [ ] Implement sales transaction recording
- [ ] Build commission calculation engine
- [ ] Create volume bonus calculations
- [ ] Add override bonus logic
- [ ] Implement tier-based calculations

### Day 4-5: Advanced Features
- [ ] Build clawback system
- [ ] Implement volume contributions tracking
- [ ] Create analytics dashboard
- [ ] Add reporting functionality
- [ ] Implement policy cancellation workflow

### Day 6-7: Polish & Testing
- [ ] Add comprehensive error handling
- [ ] Write unit tests
- [ ] Implement data validation
- [ ] Add loading states and user feedback
- [ ] Performance optimization
- [ ] Documentation

---

## 📝 Deliverables

### Code Deliverables
1. **Complete Flask backend** with all API endpoints
2. **React frontend** with all required pages
3. **Database schema** with sample data
4. **Unit tests** for critical functions
5. **API documentation** (Swagger/OpenAPI)

### Documentation Deliverables
1. **Setup instructions** for running the application
2. **Database schema documentation**
3. **API endpoint documentation**
4. **User guide** for using the application
5. **Technical architecture overview**

---

## 🎓 Learning Outcomes

By completing this project, you will gain experience in:

### Technical Skills
- **Full-stack development** with Flask and React
- **Database design** and SQL optimization
- **RESTful API development**
- **Complex business logic implementation**
- **Data visualization** and analytics
- **Git version control** and collaboration

### Business Understanding
- **Financial services** commission structures
- **Hierarchical organization** management
- **Audit trail** and compliance requirements
- **Performance optimization** for business applications

---

## 🔧 Development Environment Setup

### Prerequisites
- Python 3.8+
- Node.js 16+
- Git
- VS Code (recommended)

### Backend Setup
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install flask sqlalchemy flask-cors python-jose-cryptodome

# Run Flask app
python app.py
```

### Frontend Setup
```bash
# Create React app
npx create-react-app commission-frontend --template typescript
cd commission-frontend

# Install dependencies
npm install axios react-router-dom @types/react-router-dom
npm install tailwindcss @headlessui/react @heroicons/react
npm install chart.js react-chartjs-2

# Start development server
npm start
```

---

### Questions & Help
- **Make your own assumptions** when requirements are unclear
- **Design your own solution** based on your understanding  
- **No additional help provided** - this is a self-directed project
- **Use your best judgment** for any ambiguous requirements
- **Document your assumptions** in your README.md
---

## 🏆 Success Criteria

### Technical Success
- [ ] All core features implemented and working
- [ ] Clean, maintainable code with proper documentation
- [ ] Comprehensive test coverage (>80%)
- [ ] Performance optimized for 1000+ agents
- [ ] Responsive design works on all devices

### Business Success
- [ ] Accurate commission calculations
- [ ] Reliable clawback system
- [ ] Intuitive user interface
- [ ] Complete audit trail
- [ ] Scalable architecture

---

## 💰 Selection & Recognition

### Selection Criteria (Both Frontend & Backend EQUALLY Important)

#### **Frontend Development**
- **UI/UX Design**: Beautiful, modern, professional interface
- **Code Quality**: Clean, maintainable React/TypeScript code
- **Responsive Design**: Perfect on all device sizes
- **Data Visualization**: Clear charts and interactive elements
- **User Experience**: Intuitive navigation and interactions

#### **Backend Development**
- **Code Quality**: Clean, maintainable, well-documented code
- **Problem-Solving**: How you approach complex business logic
- **Technical Skills**: Flask, SQLAlchemy, API development
- **Database Design**: Efficient schema and relationships
- **Business Logic**: Accurate commission calculations

### Portfolio Benefits
- **Real-world project** for your portfolio
- **Complex business logic** experience
- **Full-stack development** showcase
- **Professional code quality** examples
- **Fast-paced development** experience

---

## 🔧 Submission Process

### How to Submit Your Solution

#### 1. Create Repository
```bash
# Create a private repository on GitHub
# Repository name: commission-calculation-system
# Add collaborator: qmin-warrior (Write access)
```

#### 2. Commit Your Work
```bash
# Make commits as you develop
git add .
git commit -m "feat: add agent management system"
git push origin main

# Create pull requests for major features
# Document your solution in README.md
```

#### 3. Submit for Review
- **Complete project** within 7 days
- **Push all code** to your repository
- **Document assumptions** and design decisions
- **Prepare for technical interview**

---

## 🚀 Getting Started

### Step-by-Step Setup

#### 1. Repository Setup
```bash
# Create private repository on GitHub/GitLab
# Add project manager as collaborator
# Clone the repository
git clone [REPOSITORY_URL]
cd commission-calculation-system
```

#### 2. Backend Setup
```bash
# Navigate to backend directory
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install flask sqlalchemy flask-cors python-jose-cryptodome
pip freeze > requirements.txt

# Initialize database
python -c "from app import create_tables; create_tables()"

# Run Flask development server
python app.py
```

#### 3. Frontend Setup
```bash
# Navigate to frontend directory (new terminal)
cd frontend

# Install dependencies
npm install axios react-router-dom @types/react-router-dom
npm install tailwindcss @headlessui/react @heroicons/react
npm install chart.js react-chartjs-2

# Start development server
npm start
```

#### 4. Verify Setup
- Backend running on: http://localhost:5000
- Frontend running on: http://localhost:3000
- Database file: backend/commission.db

### First Commit
```bash
# After initial setup, make your first commit
git add .
git commit -m "feat: initial project setup with Flask backend and React frontend"
git push origin main
```

### Submission Process
1. **Complete the project** within 7 days
2. **Submit code** via GitHub repository
3. **Create pull requests** for each major feature
4. **Document your solution** in README.md
5. **Prepare for technical interview** to discuss your approach

---


*This project will challenge you technically while providing real business value. We're excited to see what you'll create!*
