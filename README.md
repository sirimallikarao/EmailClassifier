# Gmail Automation Workflow

This is an automated email response workflow built using [n8n](https://n8n.io),  designed to classify and respond to incoming Gmail messages using AI.

## 🧠 Workflow Overview

- Triggers on new **unread emails** via **Gmail Trigger**.
- Uses **OpenAI** to extract the sender's name and classify the message into categories.
- Personalizes the greeting based on the extracted name.
- Sends templated responses depending on the classification:
  - Course Requests
  - Consultation Requests
  - Payments
  - Miscellaneous
- Applies corresponding labels to each email for better organization.

## 🔧 Key Nodes Used

| Node | Purpose |
|------|---------|
| `n8n-nodes-base.gmailTrigger` | Listens for new unread emails |
| `@n8n/n8n-nodes-langchain.informationExtractor` | Extracts sender name using OpenAI |
| `@n8n/n8n-nodes-langchain.textClassifier` | Classifies email content into predefined categories |
| `n8n-nodes-base.if`, `set`, `merge` | Logic for handling dynamic data |
| `n8n-nodes-base.gmail` | Send replies and apply labels |

![Screenshot 2025-06-09 233152](https://github.com/user-attachments/assets/9c901a4a-c4c5-4a0a-a0f5-5540a7aec812)

## 📤 Responses Sent

Depending on the classification, one of the following responses is sent:

- **Course Request**: General acknowledgment reply
- **Consultation Request**: Scheduling instructions
- **Payment Inquiry**: Billing support reply
- **Miscellaneous**: Default follow-up

## 🏷️ Labels Applied

Each email gets labeled accordingly:
- `Course Requests`
- `Consultation Requests`
- `Payments`
- `Miscellaneous`

## ⚙️ Setup Instructions

1. Import this workflow into your **n8n instance**.
2. Set up credentials:
   - Gmail OAuth2 for sending/receiving emails
   - OpenAI API key for classification and extraction
3. Ensure the correct Gmail labels exist or update their IDs in the nodes.
4. Activate the workflow.

For any details or collaborations dm me or mail me :
www.linkedin.com/in/basaveni-sirimallika-rao-b9b88a323
sirimallikarao.basaveni@gmail.com
