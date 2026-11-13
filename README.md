# Claude models and effort

Two small interactive pages about how model tier (Haiku, Sonnet, Opus, Fable), effort level (low to max), and your own preparation trade off.

- `index.html`: the model and effort grid. Pick a task difficulty and see which combinations fit.
- `better-prep.html`: the preparation ladder. Pick a work task, climb the ladder, and watch the cheapest good fit change.

Both pages are illustrations of the concept, not benchmark data. The spend numbers are rough, relative guesses, and the preparation minutes are illustrative.

## Want real dollar or token numbers?

These pages teach the idea. They can't tell you what a specific task will cost. These tools can.

### Find the current prices

[Anthropic's pricing page](https://platform.claude.com/docs/en/about-claude/pricing) lists the rate for every model. Prices are quoted per million tokens, with input and output priced separately, and they change, so check the page instead of trusting a number you saw in a blog post. Output tokens, which include the model's thinking, usually cost more than input tokens.

### Count the tokens in your prompt

Anthropic's [token counting endpoint](https://platform.claude.com/docs/build-with-claude/token-counting) tells you how many input tokens a prompt will use before you send it. It is free to use, and Anthropic describes the result as an estimate. It does need an API key and a small amount of code, so a developer colleague may be the easiest route.

Token counts differ by model. According to the docs, a prompt counts roughly 30 percent higher on Fable and Mythos models than on models before Claude Opus 4.7, so count with the model you plan to use.

### See what you actually spent

- **API users:** the Anthropic Console shows usage and spend for your account.
- **Claude Code:** type `/usage` (the aliases `/cost` and `/stats` open the same screen) to see the current session's cost, your plan limits, and activity. On a Pro or Max plan you get usage limits rather than a per-token bill.
- **Over time:** [ccusage](https://github.com/ryoppippi/ccusage) is a free, community-built command line tool that reads the usage files Claude Code saves on your computer and reports daily, monthly, and per-session cost estimates. It is not an Anthropic product, and its figures are estimates.

### Do a quick estimate by hand

Cost is roughly:

(input tokens × input rate + output tokens × output rate) ÷ 1,000,000

Higher effort mostly raises the output side, because the effort setting affects all tokens in the response, including thinking.

Here is a made-up example with hypothetical rates of $2 per million input tokens and $10 per million output tokens. A request with 20,000 input tokens and 4,000 output tokens costs $0.04 plus $0.04, or $0.08. If a higher effort setting doubles the output to 8,000 tokens, the cost rises to $0.12. Swap in the real rates from the pricing page to get your own answer.

### Read more on effort

[Anthropic's effort documentation](https://platform.claude.com/docs/build-with-claude/effort) explains each level and which models support it.
