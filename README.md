# autter-demo-python-worker

A Python job worker with FastAPI control routes, an internal queue, retries, job status, webhook callbacks, idempotency keys, file processing, and mock LLM tasks.

This is an **Autter Sandbox** repository. It intentionally contains realistic bugs and risky implementation patterns so design partners can test AI-editor workflows and Autter review quality.

## How to use this with Autter

1. Pick a challenge
2. Paste the suggested prompt into your AI code editor
3. Make the fix
4. Open a PR
5. Let Autter review it
6. Fix what Autter catches

## Challenges

| Challenge | Difficulty | Category | Expected Autter review angle |
| --- | --- | --- | --- |
| [Retry logic reprocesses successful jobs](./challenges/retry-logic-reprocesses-successful-jobs.md) | High | Reliability | idempotency and state transition risk |
| [Missing idempotency on job submission](./challenges/missing-idempotency-on-job-submission.md) | Medium | Reliability | duplicate side effects |
| [Webhook callback lacks signature verification](./challenges/webhook-callback-lacks-signature-verification.md) | High | Security | SSRF-style risk and trust boundary issue |
| [Failed jobs lose original error context](./challenges/failed-jobs-lose-original-error-context.md) | Medium | Observability | observability regression |
| [Worker processes jobs from wrong organization](./challenges/worker-processes-jobs-from-wrong-organization.md) | High | Authorization | tenant isolation bug |
| [File processing accepts unsafe paths](./challenges/file-processing-accepts-unsafe-paths.md) | Medium | Security | path traversal risk |
| [Queue visibility timeout causes double processing](./challenges/queue-visibility-timeout-causes-double-processing.md) | High | Reliability | concurrency risk |
| [LLM task prompt builder allows instruction injection](./challenges/llm-task-prompt-builder-allows-instruction-injection.md) | Medium | AI safety | prompt injection risk |

## Local development

Install dependencies, run the test suite, then pick a challenge. Some tests intentionally document broken behavior with expected-failure markers; they are part of the sandbox design.
