# Neural Sound Synthesis · Part 8 — Diffusion & Flow Models

Part eight of the [Neural Sound Synthesis](https://github.com/BrendanJamesLynskey/Neural_Sound_Synthesis) series. Derives denoising diffusion from the forward noising process to the reverse ε-prediction sampler, connects it to score matching and the score SDE, applies it to audio (DiffWave, WaveGrad, classifier-free guidance), tackles the many-step sampling problem (DDIM, distillation, consistency models), and links it to normalizing flows and flow matching (WaveGlow) to earn the "& Flow" title.

### [Launch App](https://brendanjameslynskey.github.io/Neural_Sound_Synthesis_08_Diffusion_and_Flow/)

Part of the [DSP & Music](https://github.com/BrendanJamesLynskey/DSP_and_Music) collection.

---

## What's inside

| Section | Content |
|---------|---------|
| **Forward Process** | The fixed Gaussian noising chain, the closed form `q(x_t|x_0)`, and the reparameterisation — with a **live forward/reverse diffusion demo** |
| **Reverse & Score** | ε-prediction, the simple training loss, the DDPM posterior mean, and the score-matching / score-SDE view |
| **Noise Schedules** | Linear vs cosine schedules, β_t, ᾱ_t and log-SNR — with a **live schedule explorer** |
| **Audio Diffusion** | DiffWave & WaveGrad as mel-conditioned vocoders, FiLM conditioning, classifier-free guidance |
| **The Step Problem** | Sampling-speed as the core weakness; DDIM, progressive distillation, consistency models, rectified flow — with a **steps-vs-quality demo** |
| **Flows** | Normalizing flows, WaveGlow, exact likelihood, continuous flows and flow matching / rectified flow |
| **Timeline** | Diffusion for audio, 2020 → 2023, cross-linked to the latent-diffusion parts |

## Live demos (all synthesised in-browser, no audio files)

1. **Forward/reverse diffusion** — slide the timestep to watch and hear a clean tone drown in Gaussian noise per the cosine schedule, then run the reverse process to sample it back from pure noise and play the recovered tone.
2. **Noise-schedule explorer** — plot β_t, the cumulative ᾱ_t, and the log-SNR curve for linear vs cosine schedules at any T, and see why cosine spends its budget where it matters.
3. **Sampling-steps vs quality** — pick 2 / 5 / 10 / 25 / 100 reverse steps and watch reconstruction error fall (and cost rise) with a DDIM-style deterministic sampler; ties fast sampling back to the autoregressive-slowness theme.

## Technology

Single-file HTML/CSS/JS · Web Audio API · HTML5 Canvas · KaTeX · Palatino + Lucida Console · No external dependencies · No build step
