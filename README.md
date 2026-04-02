# NexisHealth.ai

**Automated Insurance Bill Double-Check for Physical Therapy & Vertebral Manipulation**

A secure, patient-first web application that allows users to upload a medical bill and automatically cross-check it against their real-time insurance benefits and Explanation of Benefit (EOB) using direct FHIR Patient Access APIs.

Built specifically for patients and clinics in Arizona (with Medicare as the initial focus), supporting the most common payers:  
- Medicare  
- Blue Cross Blue Shield of Arizona (BCBSAZ)  
- UnitedHealthcare (UHC)  
- AHCCCS (Arizona Medicaid)

---

## ✨ Core Features

- **Single Login** — Patients log in once to NexisHealth.ai
- **Bill Upload** — Drag & drop PDF or image of the provider bill
- **One-Time Consent** — Patient authorizes access via OAuth2 / SMART-on-FHIR (no repeated payer logins)
- **Direct FHIR Integration** — Pulls real-time **Coverage** (benefits, deductibles, therapy limits) and **ExplanationOfBenefit (EOB)** from payer APIs
- **Intelligent Cross-Check** — Compares billed services (CPT/HCPCS codes like 97140 manual therapy) against EOB adjudication and current benefits
- **Clear Results** — Line-by-line comparison, patient responsibility calculation, discrepancy flags, and appeal recommendations
- **Exportable Report** — Professional PDF summary for patients or PT clinics

---

## 🎯 Target Use Case

Designed for patients receiving manipulative therapy / physical therapy (e.g., Maitland Concept techniques) who frequently face complex billing, therapy visit limits, and surprise patient responsibility amounts.

---

## 🛠 Tech Stack

### Backend
- **Python** + **FastAPI** (async, modern, excellent OpenAPI docs)
- **FHIR Client**: `fhirclient` (SMART-on-FHIR support)
- **OCR / Bill Parsing**: pytesseract + pdf2image (local) or HIPAA-compliant service
- **Database**: PostgreSQL (encrypted)
- **Auth**: OAuth2 + SMART-on-FHIR flows

### Frontend
- **React** (TypeScript + Vite)
- **UI**: Tailwind CSS + shadcn/ui
- **State Management**: Zustand
- **File Upload**: React Dropzone

### DevOps
- Docker + docker-compose
- HIPAA-eligible hosting (AWS / Render with BAA)

---

## 📁 Project Structure
