# Video script — Cache, context, and specification-driven agents

Target duration: **4:30–4:50** at a calm teaching pace.

The narration below is also built into `dist/index.html`. Use the page's
**Practice narration** button to move through the same six scenes.

| Time | Page scene | Screen action |
|---|---|---|
| 0:00–0:40 | Start | Introduce the three helpers. Press **Start the explanation**. |
| 0:40–1:25 | Definitions | Point to token, context limit, and prompt cache. |
| 1:25–2:10 | One-million-token limit | Switch from **Fits** to **Does not fit**. |
| 2:10–3:05 | Specification selection | Switch from **Everything included** to **Only relevant sections**. |
| 3:05–4:15 | Harness | Press **Run the harness** and follow the five stages. |
| 4:15–4:50 | Final rules | Read the three rules, then open practice mode. |

## Scene 1 — Start

Here is a common idea. If a coding agent can reuse a cached prompt, perhaps we
can load every specification, every source file, and every decision into the
prompt. Then the agent should become faster and smarter.

Only the first half is true. A cache can make repeated model work faster and
sometimes cheaper. It does not give the model more input space, and it does not
make irrelevant information useful. Let us separate these ideas.

## Scene 2 — Definitions

First, three definitions. A token is a small piece of text stored as a number.
A context limit is the largest number of input and output tokens a model can use
in one request. A prompt cache stores calculation work for an unchanged beginning
of a prompt.

When a later request begins with the same token numbers, the model server can
reuse that work. The model still receives those tokens as input. Cached describes
how the calculations were obtained. It does not mean the text disappeared.

## Scene 3 — The input limit

Suppose a model accepts one million input tokens. Eight hundred fifty thousand
cached tokens plus one hundred thousand new tokens make nine hundred fifty
thousand input tokens. That can fit, although we must still reserve space for the
answer when the model has one combined limit.

Now try ten million cached tokens plus one hundred thousand new tokens. That is
ten million one hundred thousand input tokens. The request is too large. The
cache does not extend the model's limit.

## Scene 4 — Specification selection

Now consider specification-driven development. A specification is a written set
of requirements and rules. A precise, relevant specification can improve the
answer. Sending every document can make the answer worse.

Old rules may conflict with current rules. Unrelated features compete for the
model's attention. An important requirement can become difficult to find.
Caching the complete document collection makes that collection cheaper to repeat.
It does not make the collection clearer.

Use a small stable contract first. Select the specification sections needed for
the current task. Put current source code and test results after them. Keep the
complete document collection outside the request, where the agent can search it.

## Scene 5 — The harness

In this booking demonstration, the stable contract says that one slot can have
only one active booking, the same request key cannot create a second booking, and
a notification failure cannot cancel a confirmed booking. Those rules apply to
every task, so they form a useful stable beginning.

The Architect selects one task. The Implementer receives its acceptance criteria
and relevant design. The Validator independently checks executable evidence. A
rejection returns specific findings to the Implementer.

The harness should not maximize the number of input tokens. It should assemble
the smallest complete input each role needs, preserve a stable beginning for
cache reuse, and remain correct whether the cache is found or not.

## Scene 6 — Final rules

Remember three rules. A cache saves calculation, not input space. A relevant
specification can improve an answer, but irrelevant cached text can still hurt.
The harness keeps complete knowledge outside the model and sends the active part
inside.

Cache the stable beginning. Select material relevant to the task. Validate the
result. That is how a specification-driven agent becomes faster without confusing
more input with better reasoning.
