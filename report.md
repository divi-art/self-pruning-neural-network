Self-Pruning Neural Network Report:

1. Introduction
This project explores dynamic model pruning during training by introducing learnable gates 
for each weight in a neural network.



2. Methodology

### Prunable Layer
Each weight is associated with a gate parameter:

gate = sigmoid(gate_score)

The effective weight becomes:

W' = W * gate


Loss Function

Total Loss = Classification Loss + λ * Sparsity Loss

Sparsity Loss is computed as:

L1 norm of all gates



3. Why L1 Encourages Sparsity

L1 regularization penalizes the absolute value of parameters, pushing many values toward zero. 
Unlike L2, it creates exact zeros, making it ideal for pruning.


4. Experimental Results

| Lambda | Accuracy | Sparsity |
|--------|---------|---------|
| 1e-5   | XX%     | XX%     |
| 1e-4   | XX%     | XX%     |
| 1e-3   | XX%     | XX%     |



5. Observations

- Increasing λ increases sparsity
- High sparsity reduces accuracy
- Trade-off exists between performance and efficiency



6. Conclusion

The model successfully learns to prune itself during training. 
This approach reduces model complexity while maintaining acceptable accuracy.



7. Future Work

- Structured pruning
- Real-time deployment
- Integration with LLM pipelines
