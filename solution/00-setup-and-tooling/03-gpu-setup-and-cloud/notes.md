# What I Learned: GPU Setup & Cloud

Phase 00: Setup & Tooling · Lesson 03

Source: [GPU Setup & Cloud](../../../phases/00-setup-and-tooling/03-gpu-setup-and-cloud/docs/en.md)

Completion: Reported complete by me; recorded on 2026-10-26.
These notes were drafted from the lesson content for my review and submission.
Exercise outputs and quiz scores have not been recorded yet.

## What I learned

I learned how GPU acceleration supports large matrix computations and how to
choose between local hardware and remote compute for a learning exercise.

- Local GPU execution, hosted notebooks, and rented cloud instances are
  different ways to access accelerated compute.
- `nvidia-smi` inspects NVIDIA GPU and driver information. PyTorch's
  `torch.cuda.is_available()` checks whether CUDA is usable from that runtime.
- Code can select CUDA when available and fall back to CPU otherwise.
- Tensors used together in a computation need to be on compatible devices.
- CUDA work is asynchronous, so accurate GPU timing requires synchronization
  before and after the measured operation.
- Warm-up and repeated measurements help separate startup overhead from
  steady-state performance. Transfer time should be identified separately
  when a benchmark measures only device computation.
- VRAM limits what fits on a GPU. At fp16, parameter storage alone uses about
  2 bytes per parameter; training also needs memory for gradients, optimizer
  state, activations, and other overhead.

## Worked example

A hypothetical model with 1 billion parameters needs approximately 2 billion
bytes (2 GB in decimal units) for fp16 weights alone. This is not an estimate
of its total training memory.

For a benchmark taking 4 seconds on CPU and 0.5 seconds on GPU, the speedup is
`4 / 0.5 = 8`. These numbers illustrate the calculation; they are not my
measured results.

## Practical takeaway

I should verify device availability, measure the actual workload, and record
hardware and memory details before drawing conclusions about speed or capacity.

## Evidence to add

My GPU or cloud environment, VRAM, CPU time, GPU time, and measured speedup
have not been recorded yet.
