# Should I Buy It?

## Original idea

**When someone enters the price of a non-essential purchase, how often they expect to use it, how long they have wanted it, and how much flexible money they have left, the experience should recommend whether to buy it, wait, or skip it—and explain why.**

The target user is a student or young adult who wants a quick pause before making an impulse purchase. The project is deliberately small: it tests one main interaction rather than trying to become a complete budgeting app.

## How to open it

No installation, account, or API key is required.

1. Download or clone this repository.
2. Open `dist/index.html` in a modern browser.
3. Change the sample item, price, optional-spending budget, expected use, and waiting time.
4. Select **Check this purchase** to receive an explained result.

## Decision logic

The tool compares four signals:

- the percentage of the user's flexible monthly budget the item would consume;
- expected uses per month;
- how long the user has already wanted the item; and
- estimated cost per use across six months.

It returns **BUY**, **WAIT**, or **SKIP**. A price above the available optional-spending budget always produces **SKIP**. Other cases use a small point system, so a frequent-use item that has survived a waiting period scores more strongly than an expensive item discovered today.

This is a reflection tool, not financial advice. The explanation is intentionally visible so the user can disagree with the recommendation rather than treating the score as objective truth.

## AI tool and selected prompts

I used **ChatGPT/Codex** as a design and coding partner. Important prompts and decisions included:

> “I want a practical small interactive experience similar in scope to our classroom exercise, but not another abstract or relaxing interaction.”

> “Build a browser-based ‘Should I Buy It?’ tool based on price, expected use, waiting time, and the user’s remaining optional-spending budget. Keep it to one main interaction and explain the result.”

> “Make the result feel like a decision receipt. Do not hide the reasoning behind a single score.”

AI helped turn the idea into HTML, CSS, JavaScript, and an initial scoring model. I still had to decide which questions were useful, which factors should have more weight, and whether the result should be framed as a command or as a prompt for reflection.

## Testing notes

Initial checks cover three deliberately different cases:

1. **Frequent, affordable, considered purchase:** price is a small part of the available budget, expected use is high, and the user has waited several weeks. Expected result: **BUY**.
2. **Possible but uncertain purchase:** price uses a noticeable part of the budget, expected use is moderate, or the waiting period is short. Expected result: **WAIT**.
3. **Unaffordable purchase:** price is higher than the user's remaining optional-spending budget. Expected result: **SKIP**, regardless of expected use.

The interface should also be tested at phone width, with keyboard-only input, with very large prices, and with singular values such as one use per month or one waiting day.

## Reflection draft

The first version matches my intention because it interrupts a fast purchasing decision with four concrete questions and returns more than a yes-or-no answer. The “decision receipt” makes the cost visible as both a percentage of the user’s available budget and an estimated cost per use. This was important because a $100 item can be reasonable for one person and unrealistic for another. A remaining uncertainty is that cost per use rewards frequent use but does not measure product quality, necessity, environmental impact, or whether the user’s estimate is realistic.

AI was useful for proposing a scoring structure and implementing the responsive interface, but the score still reflects human choices. For example, I chose to make an item that exceeds the optional-spending budget an automatic **SKIP**, while other factors can balance one another. Before submitting, I would test the tool with several purchases I actually considered, record where I disagreed with its result, and revise the thresholds based on those disagreements. The main unresolved question is whether three labels are nuanced enough: **WAIT** currently covers both “save for this” and “you probably do not need this,” which may need clearer language after user testing.
