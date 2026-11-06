I build evaluation environments for AI agents: tasks grounded in ML research, scored by
graders that are deterministic and hard to game.

### Featured: [paper2task](https://github.com/anandtradesmil-creator/paper2task)

Efficiency tasks built from research papers, in the open [Harbor](https://harborframework.com)
task format. In the first one, an agent has to fit Pythia-70M into **3 bits per weight,
metadata included**. The result is graded by KL divergence to the original model on hidden
text, in a separate verifier with no network access.

- **Calibrated with a seven-strategy ladder.** Naive rounding scores 0, the GPTQ-based
  reference scores 0.77, and there is still room above it.
- **58 adversarial tests run against the real grader.** They cover smuggled weights, hidden
  precision, malformed files and tampered inputs.
- **Verified end to end with `harbor run`.** Grading the same file twice gives a
  bit-identical result.

### How I build a task

1. Pick a claim that can be measured, not code that can be recited.
2. Write a contract that leaves nothing to guess.
3. Choose a metric where the only way up is the intended one.
4. Turn every way to cheat I can think of into a test.
5. Calibrate on a ladder of real strategies, then set the reward anchors.
6. Test every "this detail matters" claim, and drop the ones that don't hold.

### Interests

ML efficiency (quantization, data selection, optimizers), agent evaluation, reproducible grading.
