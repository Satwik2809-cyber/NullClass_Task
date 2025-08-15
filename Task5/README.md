# Task 5 — Text → Embedding (BERT) → Conv-CGAN → Image

This project implements a complete text-to-image pipeline that:
1) Preprocesses text with a pretrained tokenizer  
2) Creates text embeddings using BERT (CLS vector)  
3) Generates images with a Conv-CGAN (DCGAN-style) conditioned on those embeddings  

We train on a small synthetic dataset of shapes (circle, square, triangle, star) that is generated on the fly as PNGs.

 What’s inside
Real dataset creation: draws clean 28×28 PNG shapes into an ImageFolder layout
- Text preprocessing: BERT tokenizer (lowercasing, truncation, padding)
- Text embeddings: BERT `last_hidden_state[:, 0, :]` (CLS) → 768-d
- Conditional GAN:
  - G: noise + projected embedding → transposed convs → 28×28 image (tanh)
  - D: conv features + projected embedding → real/fake
- Periodic sample grids saved per label, plus a combined grid
