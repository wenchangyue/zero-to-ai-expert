---
published: true
layout: lesson
title: "How AI Actually Runs: Software, Memory, CPU, and GPU"
description: >-
  A source-linked explanation of how voice becomes numerical data, how software
  moves that data through memory, and how CPUs and GPUs execute an AI model.
date: '2026-08-11'
modified: '2026-08-11'
course: AI Foundations
level: Beginner
duration_label: 94 minutes
duration: PT1H33M50S
youtube_url: "https://youtu.be/ibCjylM9I6g"
video_id: "ibCjylM9I6g"
video_status: private
upload_date: "2026-08-11"
keywords:
  - how AI works
  - how AI runs on hardware
  - AI software and hardware
  - Python to GPU
  - CPU and GPU explained
  - audio samples and memory
  - machine instructions
  - AI inference
quick_answer: >-
  An AI system is software executed by physical hardware. A microphone converts
  sound pressure into an electrical signal, and an audio interface turns that
  signal into numerical samples. Software stores the samples in memory and may
  transform them into features or send them to a remote service. During
  inference, compiled CPU or GPU programs combine the current input with learned
  model parameters. The resulting numbers are decoded into text, pixels, or
  audio that an application can present to the user.
learning_outcomes:
  - Distinguish source code, bytecode, native code, machine instructions, and data.
  - Trace voice from a microphone to PCM samples, buffers, features, and model input.
  - Explain what RAM, GPU memory, drivers, runtimes, and kernels contribute.
  - Separate current input, learned model parameters, and temporary activations.
  - Explain where Python ends and compiled framework code begins in a representative path.
  - Distinguish local AI execution from a request sent to a cloud service.
  - Rebuild the complete route from physical input to visible or audible output.
faq:
  - q: Is artificial intelligence a type of software?
    a: An AI application is software, but the word AI can also refer to a trained model, a learning method, or the complete product. The software still needs a processor, memory, and input and output devices to run.
  - q: Does Python perform all of the numerical work in an AI model?
    a: Usually not. Python often coordinates the task. Framework dispatchers, native libraries, device runtimes, drivers, and compiled CPU or GPU kernels perform much of the numerical computation.
  - q: What numbers come from a microphone?
    a: A common route produces signed PCM sample values measured at regular time intervals. Other microphones can expose analog voltage, PDM, or another digital format before the audio stack converts the signal into the form an application needs.
  - q: Is audio created inside an application and then moved into RAM?
    a: No. The application, driver, and hardware normally exchange access to buffers that already occupy memory. The exact path can use shared buffers, DMA, mapping, or copying, depending on the device and operating system.
  - q: What does a GPU receive from Python?
    a: The GPU does not receive Python source text as a command stream. A representative stack sends tensor data, launch parameters, and references to compiled device code through a runtime and driver.
  - q: Are model weights executable code?
    a: Model weights are numerical data. Runtime code interprets the model structure and applies operations that combine those weights with input tensors and temporary activations.
  - q: Does a cloud AI service use the GPU in my computer?
    a: Usually not for the remote model. The local device captures and prepares the request, while processors in the service's data center run the remote model. Some products also use local models, so the exact boundary must be checked for that product.
  - q: Do binary values themselves contain meaning?
    a: A bit records a physical state interpreted as zero or one. Meaning comes from the conventions and instructions that interpret groups of bits as samples, instructions, addresses, tensor values, text, or pixels.
sources:
  - '[STMicroelectronics, AN4426: Tutorial for MEMS Microphones](https://www.st.com/resource/en/application_note/an4426-tutorial-for-mems-microphones-stmicroelectronics.pdf).'
  - '[Apple, What Is Core Audio?](https://developer.apple.com/library/archive/documentation/MusicAudio/Conceptual/CoreAudioOverview/WhatisCoreAudio/WhatisCoreAudio.html).'
  - '[Microsoft, Understanding the WaveRT Port Driver](https://learn.microsoft.com/en-us/windows-hardware/drivers/audio/understanding-the-wavert-port-driver).'
  - '[Radford et al., Robust Speech Recognition via Large-Scale Weak Supervision](https://cdn.openai.com/papers/whisper.pdf).'
  - '[OpenAI, Whisper audio preprocessing source](https://github.com/openai/whisper/blob/main/whisper/audio.py).'
  - '[Python Developer’s Guide, The CPython Project](https://devguide.python.org/contrib/project/).'
  - '[Python documentation, Bytecode glossary](https://docs.python.org/3/glossary.html#term-bytecode).'
  - '[PyTorch, Extending PyTorch](https://docs.pytorch.org/docs/stable/notes/extending.html).'
  - '[PyTorch, CUDA semantics](https://docs.pytorch.org/docs/main/notes/cuda.html).'
  - '[NVIDIA, CUDA Programming Guide](https://docs.nvidia.com/cuda/cuda-programming-guide/index.html).'
  - '[NVIDIA, CUDA Compiler Driver NVCC](https://docs.nvidia.com/cuda/cuda-compiler-driver-nvcc/index.html).'
  - '[NVIDIA, Matrix Multiplication Background User’s Guide](https://docs.nvidia.com/deeplearning/performance/dl-performance-matrix-multiplication/index.html).'
  - '[Apple, Accelerated PyTorch Training on Mac](https://developer.apple.com/metal/pytorch/).'
  - '[AMD, HIP Programming Model](https://rocm.docs.amd.com/projects/HIP/en/latest/).'
  - '[Intel, Intel 64 and IA-32 Architectures Software Developer’s Manuals](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html).'
---

## Three things meet when an AI model runs

A processor needs instructions and data. AI inference adds a useful distinction inside the data: some numbers describe the current request, while other numbers are learned model parameters saved after training. Runtime software chooses operations that combine the input tensors with those parameters. Intermediate tensors, called activations, exist while the computation is in progress.

These objects have different jobs. Source code describes a program for people and language tools. Machine instructions tell a processor which operations to perform. Input samples represent the current request. Model parameters record numerical settings learned during training. Treating all four as “the AI” hides the route that connects them.

## From sound pressure to numerical samples

A microphone is a transducer. Its sensing element responds to changing air pressure and produces an electrical quantity. An analog microphone can expose a changing voltage that an analog-to-digital converter samples and quantizes. A digital MEMS microphone can perform part of this conversion inside the package and expose a pulse-density-modulated stream. A decimation filter can then produce multibit PCM samples.

PCM stores measurements taken at regular time intervals. A signed 16-bit sample uses an integer from -32768 through 32767. At 16,000 samples per second, one mono second contains 16,000 sample values. Those values are numerical measurements, not written decimal characters. Software can later convert the integers to floating-point values, resample the waveform, or transform it into model features.

## Buffers already occupy memory

Audio does not live inside an application before it moves into RAM. Drivers, audio engines, devices, and applications coordinate access to memory buffers. A device can write captured data through direct memory access. Some systems map a hardware buffer so another component can read it. Others copy data between buffers. The exact route depends on the operating system and hardware.

A buffer is an organized region of memory with rules about format, capacity, and read and write position. It does not understand speech. It holds values that later software interprets as samples, packets, features, or tensors.

## Where Python stops

Python is often the visible control layer in an AI program. In CPython, source code is compiled to Python bytecode, and the interpreter executes that bytecode. A framework call can then pass through a dispatcher that selects a CPU, CUDA, Metal, or another backend implementation.

The numerical operator is commonly implemented in native code or generated as a compiled kernel. Python coordinates objects and function calls, but it does not normally execute every multiply and addition as an individual Python operation. Graph capture, ahead-of-time compilation, operator fusion, and serving engines can change this route, so the dispatcher example is representative rather than universal.

## From compiled code to a CPU or GPU

A compiler converts source representations into lower-level instructions. In the CUDA toolchain, host code and device code follow related but separate paths. Device code can become PTX and then native GPU code for a target architecture. A runtime and driver load the code, prepare launch parameters, and submit work to the device.

For a discrete GPU, tensor data may need to cross from host memory to device memory. A kernel launch creates many GPU threads that apply the same compiled program to different data elements. Matrix multiplication divides output matrices into tiles and assigns work across the machine. Dependencies still matter: parallel hardware cannot compute a result before its required inputs exist.

CUDA is an NVIDIA stack, not a universal name for GPU execution. Apple uses Metal and MPS for its accelerator stack. AMD provides HIP and ROCm. The stable idea is that framework code reaches compiled operations for a particular device through a runtime and driver.

## Model parameters are data

A trained model file stores tensors such as weights and biases. Loading the file places those values into memory and associates them with a model structure. The runtime then applies operations that combine input tensors, parameter tensors, and temporary activations.

Weights do not become a behavior by themselves. Code defines how the tensors are connected and which operations run. Hardware executes the compiled instructions. The learned values change the numerical result of those operations.

## Local and cloud routes differ

A local model can run on the computer that captured the input. A cloud product can instead encode the request and send data across a network. The local GPU may draw the interface while a remote GPU runs the main model. Some products split work across local and remote components.

Public documentation rarely exposes every internal branch of a commercial service. An exact claim about its codec, sample rate, model placement, or device path needs product-specific evidence. The lesson therefore follows public representative systems and marks the points where implementations can differ.

## From model output to a screen or speaker

The model produces numerical outputs. A speech recognizer can decode token probabilities into text. A language model can generate additional token IDs. The application maps text to glyphs, and graphics software turns those glyphs into pixels. If the product speaks, a speech model or vocoder produces waveform samples that an audio device converts back into an electrical signal for a speaker.

The complete route crosses physical signals, numerical encodings, memory, software interfaces, compiled instructions, model parameters, and output devices. No single layer replaces the others.

## Boundary

This lesson uses transparent examples from PCM audio, Whisper, CPython, PyTorch, CUDA, Metal, and HIP. These examples do not describe the private internals of ChatGPT, Claude, Gemini, or another proprietary product. Hardware can share memory or use separate memory. Frameworks can execute eagerly or compile graphs. Speech systems can use engineered features or consume waveforms through learned frontends.

Correct execution also does not guarantee a correct AI answer. The computer can perform every instruction as designed while the model produces an unsupported result. Verifying the answer remains a separate task.

## Page status

This is a reviewed lesson companion based on the final narration, captions, and cited sources. It reorganizes the spoken explanation for reading and is not a verbatim transcript. Last reviewed: 2026-08-11.
