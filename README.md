# LLM Self-Consistency Experiment

Tests whether LLMs are consistent when evaluating their own recommendations.

## How it works

1. **Generate recommendations**: Models generate 10 business recommendations with confidence ratings (1-10)
2. **Self-evaluate**: Each model evaluates its own recommendations multiple times (good/bad)
3. **Analyze consistency**: Calculate what percentage of the time each recommendation gets the same evaluation

## What it measures

- **Consistency percentage**: How often a model gives the same evaluation for the same recommendation
- **Confidence correlation**: Whether higher confidence recommendations are more consistently evaluated

## Usage

```python
# Initialize experiment
experiment = SimplifiedConsistencyExperiment(
    anthropic_client, openai_client, 
    claude_model, openai_model, 
    earnings_statement, n_evaluation_reps=3
)

# Run experiment
experiment.generate_recommendations()
experiment.evaluate_own_recommendations()
experiment.analyze_consistency()

# View results
experiment.show_consistency_summary()
experiment.create_inconsistency_histogram()
```

## Requirements

- `anthropic`
- `openai` 
- `pandas`
- `matplotlib`
- `numpy`
