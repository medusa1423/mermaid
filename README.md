# mermaid

## Underwriting AI engine

```mermaid
flowchart TD;
A[start] -->|Input| B(ID card, SSN);
A[start] -->|Input| C(Pay stubs from the last 30 days);
A[start] -->|Input| D(W-2s or I-9s from the past two years);
A[start] -->|Input| E(Proof of any other sources of income);
A[start] -->|Input| F(Recent bank statements or proof of other assets);
A[start] -->|Input| G(Details on long-term debts such as car or student loans);
A[start] -->|Input| H(Real estate property informatino/Accepted Offer to Purchase-signed by all parties-);
B -->|parameter| K[KYC validation system];
B -->|parameter| L[Document validation system];
C -->|parameter| L[Document validation system];
D -->|parameter| L[Document validation system];
E -->|parameter| L[Document validation system];
F -->|parameter| L[Document validation system];
G -->|parameter| L[Document validation system];
H -->|parameter| L[Document validation system];

B -->|parameter| M[Market Checking system];
C -->|parameter| M[Market Checking system];
D -->|parameter| M[Market Checking system];
E -->|parameter| M[Market Checking system];
F -->|parameter| M[Market Checking system];
G -->|parameter| M[Market Checking system];
H -->|parameter| M[Market Checking system];

B -->|parameter| N[Risk Assessment and Stress Testing System];
C -->|parameter| N[Risk Assessment and Stress Testing System];
D -->|parameter| N[Risk Assessment and Stress Testing System];
E -->|parameter| N[Risk Assessment and Stress Testing System];
F -->|parameter| N[Risk Assessment and Stress Testing System];
G -->|parameter| N[Risk Assessment and Stress Testing System];

B -->|parameter| O[Real Estate Property Valuation System];
C -->|parameter| O[Real Estate Property Valuation System];
D -->|parameter| O[Real Estate Property Valuation System];
E -->|parameter| O[Real Estate Property Valuation System];
F -->|parameter| O[Real Estate Property Valuation System];
G -->|parameter| O[Real Estate Property Valuation System];
H -->|parameter| O[Real Estate Property Valuation System];


K -->|output| P[KYC valuation report];
L -->|output| Q[Document valuation report];

P -->|parameter| R{KYC passed & Document passed};
Q -->|parameter| R{KYC passed & Document passed};

R -->|yes| M[Market Checking system];
R -->|yes| N[Risk Assessment and Stress Testing System];
R -->|yes| O[Real Estate Property Valuation System];

R -->|no| A[start];

M --> |output| S[Market Report];
N --> |output| T[Risk Report];
O --> |output| U[Real Estate Valuation Report];
S --> |parameter| V[User interaction];
T --> |parameter| V[User interaction];
U --> |parameter| V[User interaction];
```



## CRM AI Assistant
```mermaid
flowchart TD;
A[Start] -->|User interact| B(User Interface);
B -->|User Behavior| C(Main Processing Engine);
C -->|Display| B(User Interface);
```


## Generative Docs
```mermaid
flowchart TD;
A[start] -->|Input| B(Borrower Data);
A[start] -->|Input| C(Templates);
A[start] -->|Input| D(Compliance rules);

B --> |parameter| E[Ingest & Validate,
KYC/Income/Property,
Apply compliance rules];
C --> |parameter| E;
D --> |parameter| E;

E --> |parameters| F[Generate Documents];

F --> |output| G[Loan Application Summary -URLA/1003,
Pre-approval/Commitment Letter,
Disclosures-TILA/RESPA, Closing Disclosure,
Promissory Note,
Mortgage/Deed of Trust];

G --> H[_Closing Package Automation_
,Loan Agreement Bundle -note+mortgage+riders,
Compliance Certificates- AML/KYC, credit, appraisal,
eSignature Packets -DocuSign-ready];

H -->|output| I[Document Outputs,
PDF/Word exports,
Versioned & audit-ready];

H -->J{Human legal review required?};

J --> |changes needed| F;
J --> |pass| K[Blockchain Integration,
Smart contract equivalents-escrow triggers,
ERC-20/721 loan tokens,
Chainlink oracles-valuation feeds];
K --> L[Mint tokens & contracts,
Immutable audit trail];
L --> M[end];
```


## Business Loan & Credit Agent
```mermaid
flowchart TD;
A[start] -->  B[Loan Application& Pre-qualification]; 
B --> C[Submit documents: application, IDs, financials, business plan];

C --> D[Consent-TCPA/FCRA & KYC checks-];
D --> E[pre-qualification assessment];
E --> F[Pull credit report];
F --> G[Preliminary LTV calculation];
G --> H{Preliminary DSCR check};
H --> |No| I[End];
H --> |Yes| J[Property Appraisal & Valuation];
J --> K[Order appraisal];
K --> L[Market Value Assessment];
L --> M[Comparable and income approach analysis];
M --> N{Value supports LTV?};
N --> |No| I;
N --> |Yes| O[Due Diligence & Underwriting];
O --> P[Title records & Liens review];
P --> Q[Verify income sources-W2s, paystubs, tax returns, bank statements];
Q --> R[Insurances & inspections];
R --> S[Document verification];
S --> T{Missing documents?};
T --> |Yes| U[Request Additional Documents];
U --> C;
T --> |No| V[Credit history review];
V --> W{DSCR adequate & docs verified?};
W --> |No| I;
W --> |Yes| X[Loan Approval & Documentation];
X --> Y[Draft term sheet];
Y --> Z[Finalize interest rate & repayment schedule];
Z --> AA[Set prepayment penalties];
AA --> AB[Provide required disclosures];
AB --> AC{Approved?};
AC --> |No| I;
AC --> |Yes| AD[Loan Closing & Funding];
AD --> AE[Sign closing documents];
AE --> AF[Pay closing costs & legal fees];
AF --> AG[Disburse funds];
AG --> AH[Register & deliver final file];
AH --> I;
```


## API & XML Data Agent
```mermaid
erDiagram
    LOS_INTEGRATION_API_AGENT {
        string syncs "Encompass/Blend/nCino" 
    }
    PROPERTY_VALUATION_API_AGENT {
        string fetches "CoreLogic/ATTOM/Zillow/MLS" 
    }
    SERVICING_HANDOVER_API_AGENT {
        string transfers "Black Knight/LoanCare" 
    }
    CREDIT_BUREAU_API_AGENT {
        string retrieves "Equifax/TransUnion/Experian" 
    }
    COMPLIANCE_AUDIT_XML_AGENT {
        string creates "AML/KYC & HMDA XML" 
    }
    LOS_INTEGRATION_XML_AGENT {
        string translates "REST↔XML for LOS" 
    }
    CLOSING_DISCLOSURE_XML_AGENT {
        string produces "TRID-compliant CD XML" 
    }
    UNDERWRITING_DECISION_XML_AGENT {
        string outputs "Eligibility XML with DU/LP codes" 
    }
    LOAN_APPLICATION_XML_GENERATOR {
        string generates "MISMO 3.4 XML" 
    }
    DOCUMENT_ESIGNATURE_API_AGENT {
        string orchestrates "DocuSign/Adobe Sign" 
    }
    KYC_AML_API_AGENT {
        string verifies "Plaid/Persona/LexisNexis" 
    }
    PRICING_RATE_SHEET_API_AGENT {
        string calculates "Rates & pricing grids" 
    }
    ENGINE5 {
        string name "AI Engine 5" 
        string purpose "Extraction, normalization, orchestration" 
    }
    XML_AGENT {
        string type 
    }
    API_AGENT {
        string type 
    }
    CLOSING_DISCLOSURE_XML_AGENT o{--|| DOCUMENT_ESIGNATURE_API_AGENT : sends CD
    ENGINE5 ||--o{ LOS_INTEGRATION_XML_AGENT : uses
    ENGINE5 ||--o{ LOAN_APPLICATION_XML_GENERATOR : uses
    ENGINE5 ||--o{ PROPERTY_VALUATION_API_AGENT : integrates
    ENGINE5 ||--o{ API_AGENT : includes
    ENGINE5 ||--o{ LOS_INTEGRATION_API_AGENT : integrates
    ENGINE5 ||--o{ PRICING_RATE_SHEET_API_AGENT : integrates
    ENGINE5 ||--o{ KYC_AML_API_AGENT : integrates
    PROPERTY_VALUATION_API_AGENT ||--o{ UNDERWRITING_DECISION_XML_AGENT : provides AVM
    ENGINE5 ||--o{ UNDERWRITING_DECISION_XML_AGENT : uses
    ENGINE5 ||--o{ CLOSING_DISCLOSURE_XML_AGENT : uses
    ENGINE5 ||--o{ COMPLIANCE_AUDIT_XML_AGENT : uses
    ENGINE5 ||--o{ XML_AGENT : includes
    ENGINE5 ||--o{ DOCUMENT_ESIGNATURE_API_AGENT : integrates
    PRICING_RATE_SHEET_API_AGENT ||--o{ UNDERWRITING_DECISION_XML_AGENT : pricing inputs
    ENGINE5 ||--o{ CREDIT_BUREAU_API_AGENT : integrates
    UNDERWRITING_DECISION_XML_AGENT o{--|| CREDIT_BUREAU_API_AGENT : consumes scores
    LOS_INTEGRATION_XML_AGENT ||--o{ LOS_INTEGRATION_API_AGENT : bidirectional sync
    COMPLIANCE_AUDIT_XML_AGENT o{--|| KYC_AML_API_AGENT : logs verification
    LOAN_APPLICATION_XML_GENERATOR o{--|| LOS_INTEGRATION_API_AGENT : posts MISMO
    SERVICING_HANDOVER_API_AGENT o{--|| LOS_INTEGRATION_API_AGENT : post-closing transfer
    ENGINE5 ||--o{ SERVICING_HANDOVER_API_AGENT : integrates

```


## Crypto Payment Assistant
```mermaid
flowchart TD;
A[Global Investors] --> B[Multi-Crypto Wallets
BTC/ETH/USDC/USDT];
B --> C[Crypto payments Assistant Payment Layer];
B --> D[Wallet Gateway ];
B --> |data| D;
D --> E[AML/KYC Compliance Orchestrator];
C --> E;

E --> F[KYC/AML Services];
E --> |Verify KYC/AML| G{Risk Screening Router};
G --> |Block if High-Risk| H[Chainalysis API Wallet Risk Scoring];
G --> |Process if Low-Risk| I[Rate Oracle &amp; Locking
&lt;5s latency];
C --> I;
I --> J[Instant Crypto-to-Fiat Converter];
C --> J;
J --> K[Coinbase Commerce API
On/Off Ramps];
J --> L[Stripe Crypto API
On/Off Ramps];
J --> |Convert Crypto→Fiat| M[Settlement Manager
ACH/Wire];
J --> |Locked Rate| M;
C -->M;

M --> O[Banking Rails
ACH • Wire];
C --> |Execute & Settle| O;
O --> P[Seller Bank Account];
M --> |Settle &lt;30min| P;

C --> Q[Compliance & Audit Trails
Travel Rule • SAR];
Q --> |Audit Logs| R[Lending Platform];

C --> |QR Codes • One-click Connect| P[Refund & Dispute Workflows];
C --> |Payment Confirmed Webhook| R;
R --> C;
C --> S[Transaction Tracking Dashboard
Timeline • Alerts • Disputes];
S --> |Status & Receipts| R;

T[Investor Conversations] --> |Payment Intent|C;
T --> C;
C --> U[Blockchain Settlement Tracker
Immutable Proofs];

U --> |Settlement Proofs| S;

U --> V[Ethereum];
U --> W[Stablecoin Ledgers
USDC/USDT];
U --> X[Bitcoin];
```


## Graphic & SEO Content Agent
```mermaid
flowchart TD;
A(Start)--> B[Property & Loan Data];
B --> C{Orchestrator};
C --> D[Investment -Specific Graphics-Cap rate/IRR charts];
C --> E[Social Graphics-branded images/carousels];
C --> F[SEO Content Engine-blogs, keywords, schema];
C --> G[Listing Generation-SEO descriptions+ meta];

D --> H[Aggregated Marketing Package];
E --> H;
F --> H;
G --> H;

H --> I{Approved?};
I --> |No| J[Edit/Regeneration];
J --> C;
I --> |Yes| K[Publish to website, Social, Investor Networks];

K --> L{Track Engagement & SEO performance};

L --> M[A/B Test Creatives];
L --> N[Prioritize High-interest Priorities for Funding];
M --> O(end);
N --> O;
```


## Compliance & Risk Monitor
```mermaid
flowchart TD;
A(Start: Transaction Event)--> B{Monitor Post/Monitor Real-time compliance check};
B --> C{Unified Risk Scoring
AML 40% + Behavioral 30% + Velocity 30%};
B--> D{Compliance Dashboard
Risk feeds, heatmaps, alerts};

B --> E[CREquity.ai Lending Platform
Txn stream, parties, amounts];

B --> F[Regulatory Rulesets
FinCEN Travel Rule, MiCA];
B --> G[Interfaces
REST APIs + Webhooks
 holds/proceed];
B --> I[Performance
&lt;500ms scoring
99.99% uptime
10K tx/day];
B --> J[Supportability
Self-serve queries
24/7 reporting
Quarterly model updates];

B --> K[Security
E2E PII encryption
MFA + RBAC
Zero-knowledge proofs];

D --> L[Exports & Audit Views
Regulator-ready, drill-downs];
D --> M[Remediation Workflow
Escalations, approvals];

C --> N[KYC
>98% completeness];
C --> O[Chainalysis API
Wallet screening];

C --> P{Risk Score >= Threshold?
-e.g., SAR > 0.8};

P --> |Yes| Q{Actions
, Hold via Webhook to Engine 6
,Flags -e.g., Travel Rule
, One-click SAR
POST /engine8/sar};

P --> |No| R{Proceed to Settlement
Engine 6 blockchain settlement};

Q --> |Webhook: hold| R;

Q --> S{Automated Audit Trail
Immutable log: KYC → Payment → Settlement → Reporting
GET /engine8/audit/audit_id};

R --> |Webhook: clean| S;

R --> S;

R --> T[Blockchain Proofs
Immutable compliance events];
R --> U[Regulatory Reporting
FinCEN CTR/SAR, MiCA
SOC2-ready exports];

U --> V[End: Audit-ready, compliant transaction];
```
