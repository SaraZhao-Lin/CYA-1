# Reflection Report - CYA-1

## Activity Description
The objective of this activity was to complete the development phases of **EzSqueeze**, a cross-platform audio compressor. My expectations were to move the project from a theoretical DSP concept to a "Release Candidate" state. I was responsible for implementing the dual-stage compression path (FET and Opto), integrating oversampling filters to reduce aliasing, and finalizing the CMake build system to ensure the project could be compiled across different environments.

## Technical and Professional Decisions
One key technical decision was choosing **C++17** and the **JUCE/HISE** framework. This was strategic; JUCE is the industry standard for audio, and C++17 provides the performance needed for sample-accurate processing. I opted for **polyphase filters** for the 4x/8x oversampling to balance audio quality with CPU efficiency—a critical trade-off in real-time audio. Professionally, I decided to implement a **GitHub Actions CI/CD pipeline** early on. This ensured that any code changes wouldn't break the build on macOS or Windows, reflecting a "DevOps-aware" approach to software development.

## Contributions
I worked as part of a two-person team (alongside Isaías Hernandez). My specific individual contributions focused on the **DSP backend** and the **Build System**. While we collaborated on the UI design (the Citrus theme), I independently wrote the C++ classes for the Compressor Detector and the Lookahead buffer. I also authored the `build.ps1` script to simplify the build process for other contributors.

## Quality Assessment
I assess my performance as **High**. The plugin successfully passes all Catch2 unit tests, and the "Vibe Wheel" provides the intended harmonic saturation without audible artifacts. However, if I were to repeat this experience, I would improve the **Memory Management** documentation. While the code is leak-free, the complex interaction between the HISE script and C++ backend could be better documented to help future open-source contributors.

## Career Alignment
This experience moved me significantly closer to my goal of becoming an Audio Software Engineer. It forced me to solve real-world problems like **latency compensation** and **thread safety** in audio callbacks—skills that are highly sought after by companies like Ableton, Apple, or Adobe. Completing a full-lifecycle project (from Phase 0 to Phase 8) proves I can manage complex software architectures and deliver a professional product.