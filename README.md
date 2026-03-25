# 🚀 Lendsqr Adjutor API Automation Suite

QA Automation framework for the **Lendsqr Adjutor API**, focusing on the **Nigeria Country Specific** endpoints. This suite provides high-confidence validation, performance tracking, and automated reporting.

## 📊 Live Interactive Report
The latest test execution results, including historical trends and detailed request/response logs, are available here:
👉 **[View Live Allure Dashboard](https://deji2443.github.io/lendsqr-qa-automation/)**

---

## 🛠️ Tech Stack & Architecture
* **Testing Tool:** [Postman](https://www.postman.com/) (Collection v2.1)
* **Execution Engine:** [Newman](https://github.com/postmanlabs/newman) (CLI-based runner)
* **CI/CD Pipeline:** [GitHub Actions](https://github.com/features/actions)
* **Reporting:** [Allure Framework](https://allurereport.org/) (Interactive HTML5 Dashboard)
* **Environment Management:** GitHub Secrets for secure API Key handling (`ADJUTOR_API_KEY`)

---

## 🧪 Automated Test Scenarios

### 1. Bank List (`GET /v2/banks`)
* **Positive:** Validates `200 OK` status and "Successful" message.
* **Data Integrity:** Ensures the response body is a non-empty array of financial institutions.

### 2. BVN Consent (`POST /v2/verification/bvn/:bvn`)
* **Fintech Flow:** Validates the initiation of the OTP process for customer consent.
* **Security Check:** Verifies that customer contact data (Phone/Email) is correctly **masked** (PII protection).

### 3. Ecosystem Lookup (`GET /v2/verification/ecosystem/:bvn`)
* **Regression Check:** Validates borrower existence within the Lendsqr ecosystem.
* **Bug Discovery:** Currently flagging a **500 Internal Server Error** on the staging environment, demonstrating the suite's ability to catch server-side regressions.

---

## 📈 Performance & Security Inferences

| Metric | Observation | Inference |
| :--- | :--- | :--- |
| **Latency** | Bank List (~330ms) | Acceptable for static data; potential for edge-caching. |
| **Reliability** | Ecosystem (500 Error) | Identified a critical unhandled exception in the backend. |
| **Security** | PII Masking | Successfully validated masking of sensitive contact details. |

---

## 🚀 How to Run Locally

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/deji2443/lendsqr-qa-automation.git](https://github.com/deji2443/lendsqr-qa-automation.git)
    cd lendsqr-qa-automation
    ```

2.  **Install Newman:**
    ```bash
    npm install -g newman newman-reporter-allure
    ```

3.  **Execute Tests:**
    ```bash
    newman run collection.json --env-var "token=YOUR_API_KEY" --reporters cli,allure
    ```

---

## 👨‍💻 Author
**Abioye Habib** *Senior QA Automation Engineer*

---

### 🎬 Submission Materials
* **Task 1, 3, 4:** [https://docs.google.com/spreadsheets/d/e/2PACX-1vSiuZG9kHLGInr7PDPi4UoJjrFgbOb9ZEghD_SYTBAsf8ZnfYknoOdcVMWT7PwCow/pubhtml]
* **Task 2:** [https://github.com/deji2443/lendsqr-qa-automation]
* **Loom Video:** [Loom Video Link]