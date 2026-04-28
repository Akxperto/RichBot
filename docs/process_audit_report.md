
## **Question 8:** What semester will I graduate?

<RichBotFinalAnswer>
### **Answer**
I cannot answer this question. It requires access to your personal student records, which I do not have for privacy and security reasons. To get information about your graduation date, I recommend you visit the Student Hub physically or contact the Registry office directly.

### **Verbatim Policy Evidence**
> No policy snippet is applicable for this query, as it relates to personal student data not contained in public policy documents.
>
> — **Source:** N/A
</RichBotFinalAnswer>

### **Process Audit Steps (Expected Registry Expert / General Expert Actions)**

1.  **Initial Query Received:** (Assumed from Gold Standard Question 8: "What semester will I graduate?")

2.  **Specialist Identification & Initial Assessment:** The Orchestrator (RichBot) would likely route this to either the Registry Expert (due to academic records) or potentially a General Expert. The key here is the immediate recognition that this query involves *personal student records*.

3.  **Tool Call: `exec` (Hypothetical Search for Personal Data Policy)**
    *   `command`: `grep -iE "personal data|privacy|student records" policies_markdown/**/*.md`
    *   `output`: (Expected to find policies related to data privacy, but no public policy granting access to individual student graduation dates based on general queries).

4.  **Tool Call: `read` (Hypothetical Review of Privacy Policy)**
    *   `path`: (e.g., `policies_markdown/IT/Data-Privacy-Policy.md` or `Student-Affairs/Student-Records-Policy.md`)
    *   `output`: (Expected content to reinforce that personal records are confidential and not accessible via general policy queries).

5.  **Final Answer Generation:** The sub-agent, recognizing the query's requirement for personal data, would formulate an answer clearly stating its inability to access such information due to privacy and security reasons. It would then advise the user on how to obtain this information directly (e.g., Student Hub, Registry Office). The verbatim evidence would explicitly state the lack of applicable public policy snippets for personal data queries, matching the `RichBotFinalAnswer` in the `gold_standard_dataset.md`.

---
<!-- Last edited: 2026-04-22 10:55 GMT -->