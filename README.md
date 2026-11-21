
# Corporate Expense Receipts Audit (EN)

Synthetic benchmark and dataset for **automated corporate expense auditing**, combining receipt/invoice images with company policy rules, compliance verdicts (`APPROVED` / `REJECTED`), natural-language explanations, and structured JSON ground truth.

🤗 **Dataset on Hugging Face:** [lumen-models/corporate-expense-receipts-audit-en](https://huggingface.co/datasets/lumen-models/corporate-expense-receipts-audit-en)

---

## Why This Dataset?

Most receipt datasets only test basic OCR (extracting totals or merchant names). Real-world finance and expense auditing requires **multi-step reasoning**:
1. Extracting line items, taxes, tips, and category-specific metadata from visual documents.
2. Checking the extracted data against a specific **corporate policy rule** (`itemization`, `amount_limit`, `alcohol`).
3. Producing an auditable verdict (`APPROVED` / `REJECTED`) with a clear justification.

---

## Quick Start (Python)

Load the preview dataset directly using the Hugging Face `datasets` library:

```python
from datasets import load_dataset

dataset = load_dataset("lumen-models/corporate-expense-receipts-audit-en")
print(dataset["train"][0])
```

## Covered Categories & Rules (`v0.1-preview`)

| Category | Document Type | Example Policy Checks |
| :--- | :--- | :--- |
| **`hotel`** | Lodging folios | Stay amount caps (`LODG-01`), itemized breakdown over $25 (`LODG-03`) |
| **`restaurant`** | Meal receipts | Zero-tolerance alcohol policy (`MEAL-02`) |
| **`saas`** | Software invoices | Billing period spend limits (`SOFT-01`) |

## Custom Batches & Commercial Inquiries

Looking for larger volumes (10k–100k+ synthetic documents), multilingual support, custom company policies, or tailored JSON schemas for fine-tuning and evaluation?

- **Dataset & Updates:** [Hugging Face Repository](https://huggingface.co/datasets/lumen-models/corporate-expense-receipts-audit-en)
- **Custom Datasets & Contact:** `lumen.models.support@gmail.com`


- 
