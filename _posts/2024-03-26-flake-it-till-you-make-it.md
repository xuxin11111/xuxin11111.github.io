---
layout: post
title: EEG Cross-scenario Emtion Recognition 
subtitle: Based on Contrast Autoencoder (cAE)
cover-img: /assets/img/emotion decoding.png
thumbnail-img: /assets/img/emotion decoding.png
share-img: /assets/img/emotion decoding.png
tags: [affective computing]
author: Xu Xin
mathjax: true
---

We proposed a cross-contextual commonality EEG representation extraction method based on contrastive autoencoders, designed to decouple emotion-related cross-contextual common EEG representations from context-specific EEG representations, thereby enhancing the performance of cross-contextual emotional decoding.

The model comprises a cross-contextual common encoder $$f_e$$ for extracting common emotional representations, and several context-specific encoders $$f_s$$. Given an EEG input $$x$$, $$z_e = f_e(x)$$ and $$z_s = f_s(x)$$ represent the extracted common emotional and context-specific representations, respectively. The common emotional representation $$z_e$$ is trained through an emotional decoding branch; the context-specific representation $$z_s$$ is trained via a contextual information reconstruction task; their joint representation $$v = \text{concat}(z_e, z_s)$$ is trained through an EEG signal reconstruction task. This assumes that both common emotional and context-specific representations can collaboratively reconstruct the EEG signal, with $$z_e$$ primarily containing emotion-relevant information and $$z_s$$ holding context-specific details unrelated to emotions. To better decouple $$z_e$$ from $$z_s$$, a penalty term is added to the loss function to minimize the correlation between $$z_e$$ and $$z_s$$. Here, contextual information can be extracted from stimuli using pretrained models on video, audio, and text data.
