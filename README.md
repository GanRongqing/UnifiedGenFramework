# UnifiedGenFramework

## Project Overview

UnifiedGenFramework is a hierarchical, multimodal, and resolution-adaptive generation and understanding system. This framework introduces a layered tokenizer architecture, supporting unified image-text modeling and high-resolution generation for arbitrary input resolutions and aspect ratios. The system features dynamic multi-scale tokenization, a master-auxiliary tokenizer structure, unidirectional information flow via cross-attention, and joint RLHF and contrastive learning, making it suitable for advanced AIGC, multimodal retrieval, and unified vision-language tasks.

## Key Innovations

- Hierarchical Tokenizer Design: Master tokenizer encodes global structure from low-res inputs, while the auxiliary tokenizer encodes residuals for high-frequency, high-resolution details.
- Dynamic Multi-scale & Resolution Adaptation: Supports arbitrary image sizes and aspect ratios with flexible, adaptive tokenization.
- Unidirectional Cross-attention: Master and text tokens can attend to auxiliary tokens, but not vice versa, ensuring clear separation of responsibilities and efficient fusion.
- RLHF & Contrastive Learning: Combines reinforcement learning from human feedback and multimodal contrastive objectives to boost subjective quality and image-text alignment.
- Engineering Compatibility: Easily integrates with mainstream LLM/VLM architectures; scalable, extensible, and practical for diverse multimodal scenarios.

## Method Overview

Input: Images of any resolution/aspect ratio, text, or both.  
Master tokenizer: Resizes images to 256x256, encodes global token sequence capturing structure and low-frequency content.  
Auxiliary tokenizer: Computes residuals between the original high-res image and upsampled master-branch reconstructions, then encodes these as auxiliary tokens for high-frequency detail.  
Information fusion: Master and text tokens attend to auxiliary tokens via cross-attention (unidirectional); auxiliary tokens do not attend back, ensuring clear, efficient information flow.  
Training: Uses RLHF for overall generation quality, and multimodal contrastive losses for robust vision-language alignment, retrieval, and unified representation.

## Status

- Core architecture, key ideas, and method descriptions are public; code and experiments are under development.

## Priority Statement

This project was first made public on GitHub on 2025-06-13. The conceptual design and innovations are attributed to the author(s). Collaboration, discussion, and citation are welcome.
