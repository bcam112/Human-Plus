# EQ-Bench 3 Integration

**Human+ Performance: 1634 ELO Normalized (1st place)**

This directory contains the integration layer for running Human+ on EQ-Bench 3.

## Human+ is the System Under Test

**Human+ is NOT a wrapper or add-on.** When EQB3 tests `humanplus/engine`, it is evaluating:
- Human+'s ability to calculate consciousness, ethics, and emotions from scenarios
- Human+'s emotional intelligence demonstrated through consciousness metrics
- Human+'s capacity to generate emotionally resonant guidance

The base LLM (Claude) is a **tool for language generation**, not the system being evaluated.

## Structure

```
eqbench3_integration/
├── run_humanplus_eqbench3.py    # Benchmark runner
├── __init__.py                  # Imports from llm_backends/claude
├── eqbench3_repo/               # Official EQ-Bench 3 code
├── QUICK_START.md
└── README.md
```

**Note:** This directory contains integration documentation. Implementation code is proprietary.

## Quick Start

```bash
# Set your API key
$env:ANTHROPIC_API_KEY = "your-key-here"

# Run Human+ on EQ-Bench 3 (Human+ is the system being tested)
python run_humanplus_eqbench3.py --mode DEEP --model-name "Human+"
```

## How It Works

1. **Human+ Analysis**: Human+ analyzes input to calculate consciousness metrics (depth, resonance, level)
2. **Guidance Generation**: Human+ generates consciousness-level guidance based on calculated metrics
3. **LLM Generation**: Base LLM generates response WITH Human+ guidance (Human+ shapes the response)
4. **State Update**: Human+ processes the response and updates consciousness state

**EQB3 evaluates Human+'s emotional intelligence, not the base LLM's.**

## Features

- Detailed Human+ metrics in system messages
- Recursive insights passed to LLM
- Context-aware guidance for emotional scenarios
- EQ-Bench 3 role-play awareness
- Natural integration without meta-commentary

## Configuration

Set environment variables:
- `ANTHROPIC_API_KEY` or `TEST_API_KEY` - For base LLM calls
- `JUDGE_API_KEY` - For judge model (optional)
- `HUMANPLUS_MODE` - Processing mode (MINIMAL, STANDARD, DEEP, BENCHMARK)
- `HUMANPLUS_CLAUDE_MODEL` - Claude model name (default: claude-sonnet-4-5-20250929)

## Results

Results are automatically saved to:
- `results/eqbench3/eqbench3_runs.json` - Scenario transcripts and rubric scores
- `results/eqbench3/elo_results_eqbench3.json` - ELO ratings and leaderboard data
- `results/logs/eqbench3/eqbench3.log` - EQ-Bench 3 execution logs
- `results/logs/humanplus_runs/` - **Comprehensive Human+ logs** (NEW)

### Comprehensive Logging

Every interaction is now logged with full details:
- User input and context
- Mirror understanding (emotional state detection)
- Human+ analysis (SE, resonance, insights, felt state)
- Full guidance sent to LLM
- Full LLM response
- Processing time

Log files: `results/logs/humanplus_runs/humanplus_run_YYYYMMDD_HHMMSS.log`

## Performance

**Human+ v4.1 Achievement:**
- **ELO Normalized:** 1634 (1st place)
- **ELO Raw:** 1736
- **95% Confidence Interval:** 1609 - 1658
- **Sigma:** 6.8
- **Rank:** 1st of 47+ systems

See [examples/outputs/](examples/outputs/) for detailed results, judge feedback, and scenario breakdowns.
