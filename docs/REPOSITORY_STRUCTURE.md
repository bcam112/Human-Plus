# Repository Structure

This repository contains public documentation, theory, and academic materials for Human+ and Consciousness + Conflict Theory (C+CT).

## What's Public

### Documentation
- `README.md` - Main overview and introduction
- `docs/THEORY.md` - Consciousness + Conflict Theory explanation
- `docs/HUMANPLUS_OVERVIEW.md` - Human+ system overview
- `docs/HOSTED_API_GUIDE.md` - Guide for testing Human+ via API
- `docs/REPOSITORY_STRUCTURE.md` - This file

### Academic References
- Links to published papers:
  - [Consciousness + Conflict Theory (C+CT)](https://philarchive.org/rec/BCCWIT)
  - [The Human+ Recursion Engine](https://philarchive.org/rec/CGTHRX)

### Configuration Files
- `.gitignore` - Ensures proprietary code is not committed
- `LICENSE` - Copyright and usage terms
- `requirements.txt` - Public dependencies (if any)

## What's NOT Included (Proprietary)

The following are excluded from this public repository:

### Source Code
- `humanplus/humanplus_engine.py` - Core engine implementation
- `llm_backends/**/*.py` - LLM-specific API clients
- `eqbench3_integration/*.py` - Benchmark integration code
- All Python implementation files

### Internal Data
- `results/` - Test results and logs
- `archive/` - Version snapshots
- `eqbench2/` - Previous benchmark data
- Any JSON, log, or result files

### Secrets
- `.env` files
- API keys
- Configuration secrets
- Private documents

## Purpose

This repository serves to:
1. **Share the theory** - Make C+CT accessible to researchers
2. **Document the system** - Explain what Human+ does conceptually
3. **Enable testing** - Provide guides for using Human+ via API
4. **Academic citation** - Provide references for papers

It does NOT:
- Expose implementation details
- Share proprietary algorithms
- Include executable code
- Reveal internal architecture specifics

## For Researchers

If you're interested in:
- **The theory**: See `docs/THEORY.md` and the C+CT paper
- **The system**: See `docs/HUMANPLUS_OVERVIEW.md`
- **Testing it**: See `docs/HOSTED_API_GUIDE.md`
- **Collaboration**: Contact the author

## For Developers

This repository does not contain the implementation. For access to:
- Source code
- Implementation details
- Integration examples
- Commercial licensing

Please contact the author.
