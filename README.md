# Thesisly

### Every market question deserves a test.

Thesisly is an experimental market research platform that transforms ambiguous natural-language trading questions into structured, testable experiments.

Instead of immediately running a backtest, Thesisly first identifies ambiguity, clarifies assumptions, and converts a market hypothesis into a well-defined experiment.

It combines natural-language understanding with deterministic backtesting to help users investigate market behavior through structured experimentation.

---

## The Problem

A question like:

> Does buying NIFTY after a sharp fall work?

sounds simple, but it leaves several important questions unanswered:

- What qualifies as a sharp fall?
- When should the position be entered?
- How long should it be held?
- When should the position be exited?
- What historical period should be tested?

Without clearly defining these parameters, a backtest can produce misleading results.

**Thesisly addresses this problem by making assumptions explicit before testing begins.**

---

## How It Works

Thesisly follows a five-stage workflow:

**ASK → CLARIFY → DEFINE → TEST → LEARN**

### 1. ASK — Express a market hypothesis
Users enter research questions in natural language without needing to define every technical parameter upfront.

### 2. CLARIFY — Identify ambiguity
The language model interprets the question and identifies missing experimental parameters, including:

- Instrument
- Timeframe
- Entry condition
- Entry timing
- Holding period
- Exit condition
- Test period

Suggested assumptions are presented for user review and modification.

### 3. DEFINE — Structure the experiment
The confirmed assumptions are converted into a structured experiment definition.
Users can review the conditions before proceeding.

### 4. TEST — Run a deterministic backtest
A JavaScript backtesting engine evaluates the experiment against the available dataset.
The language model does not calculate the numerical backtest results.

### 5. LEARN — Interpret the observations
Thesisly presents the results and explains what they indicate, along with their limitations.
A positive result is not automatically treated as evidence of a reliable trading strategy.

---

## Example Experiment

**Research Question:**

Does buying NIFTY after a sharp fall generate positive returns?

The prototype converts this question into the following experiment:

| Parameter | Definition |
|---|---|
| Instrument | NIFTY |
| Timeframe | Daily |
| Sharp fall | 2% or more |
| Entry | Next trading day's open |
| Holding period | 5 trading days |
| Exit | Close after holding period |
| Dataset | Local prototype sample |

### Prototype Results

| Metric | Result |
|---|---:|
| Qualifying events | 4 |
| Average return | 2.39% |
| Median return | 2.33% |
| Win rate | 100% |
| Best return | 3.35% |
| Worst return | 1.55% |

**Important:** These figures come from a small local prototype dataset. Four qualifying events are insufficient to establish statistical significance or demonstrate a reliable trading edge.

---

## Key Features

- Natural-language market research questions.
- AI-assisted interpretation and ambiguity detection.
- Interactive experiment parameter clarification.
- Structured experiment definitions.
- Deterministic JavaScript backtesting.
- Performance metric calculations.
- Result interpretation with explicit limitations.

---

## Technology Stack

### Frontend
- React.js
- Vite
- CSS

### Backend
- Node.js
- Express.js

### Language Model
- Google Gemini API

### Backtesting Engine
- JavaScript
- Deterministic experiment execution

---

## Architecture Overview

Thesisly separates natural-language interpretation from numerical backtest execution.

The language model assists with understanding and structuring experiments, while the deterministic engine handles calculations.

This separation helps keep numerical results reproducible and independent of language-model-generated calculations.

---

## Project Structure

```text
thesisly/
│
├── client/
│   └── src/
│       ├── components/
│       ├── services/
│       ├── App.jsx
│       └── App.css
│
└── server/
    ├── routes/
    ├── services/
    ├── utils/
    ├── data/
    └── server.js
```

---

## Getting Started

### Prerequisites

- Node.js
- npm
- Google Gemini API key

### Installation

Clone the repository:

```bash
git clone https://github.com/fuzail-sk/thesisly.git
cd thesisly
```

Install dependencies in the client and server directories:

```bash
cd client
npm install
```

```bash
cd ../server
npm install
```

Configure the required environment variables according to the server configuration.

Start the frontend and backend using the scripts defined in their respective `package.json` files.

---

## Current Project Status

**Experimental Prototype**

Thesisly demonstrates an approach to converting ambiguous market research questions into structured and testable experiments.

Current limitations include:

- Uses a local prototype dataset.
- Limited number of qualifying historical events.
- Not connected to a verified live market-data feed.
- Backtest results are not evidence of future performance.
- Transaction costs, slippage and other market frictions should be considered before drawing broader conclusions.

---

## Future Improvements

- Integration with reliable historical market-data sources.
- Support for additional instruments and timeframes.
- Expanded experiment conditions and exit strategies.
- More comprehensive backtesting and statistical analysis.
- Transaction costs and slippage modelling.
- Experiment history and comparison.
- Improved visualization of backtest results.

---

## Project Philosophy

A market hypothesis should never be tested without clearly defining what is being tested.

Thesisly aims to make market research more structured, transparent and reproducible.

---

**Built by Shaikh Fuzail**

[GitHub](https://github.com/fuzail-sk)
