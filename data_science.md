# Data Science
## [Nijman et al., 2021](https://pubmed.ncbi.nlm.nih.gov/34798287/)
### Takeaways
- In clinical diagnosis / prognosis prediction model studies, nulls are majorly treated as follows;
    - Insufficient information in literature
    - Methodologies
        - CCA (complete-case-analysis): Remove all samples which have nulls in any of the variables
            - Lessen # of samples
        - Single (mostly mean) imputation
        - Missing value indicator
            - Affect clinician's decision-making, which affects predictive power of the model
                - "They say missing value is important, so let's fill it"
            - Reasoning behind missing must be monitored
- Should be treated with;
    - Proper way of disclosure
    - Consideration of available approaches, such as;
        - Multiple imputation (using Rubin's rule)
        - Methodologies which can directly deal with null, such as ;
            - trees with surrogate splits, which use another variable for splitting samples with null values
            - sparsity-aware splitting, pattern-mixture model

### Questions & Comments
- Other than clinical settings, approaces to nulls should be carefully designed when it could be potentially a bias
    - e.g. Questions in questionnaire which is sensitive for answerer
- Also important if the model details will be given to "those who generate the data"
- What happens if likelihood in multiple imputation is not high "enough"?

### Notes
- [refernce 21 for pattern submodel](https://academic.oup.com/biostatistics/article/21/2/236/5092384)

## [Alayrac et al., 2022](https://www.deepmind.com/blog/tackling-multiple-tasks-with-a-single-visual-language-model)
### Where am I?
- 3.1.2
### Takeaways
#### Related Works
- Hoffmann et al. (2022)
    - shows # of tokens scale with model size, which explains large-model-better trend
    - Flamingo (80B) is built upon Chinchilla (70B)
- Multiple lines of works have been done on Multimodal BERT-like models but Flamingo is different in that fine-tuning is not needed
- Contrastive dual encoder is strong in small samples but applicable type of tasks is limited, and Flamingo can learn from even smaller samples (significant improvement with 4 samples)
- Autoregressive generative multimodal model is most similar to this work
    - Usage of frozen language model, mapping between vision encoder, cross-attention layers across language model layers
    - Still differentiated in its capability in small data and its flexibility
- In this work, multimodal task-agnostic web scraped data is used for pretraining
- Few-shot learning including "in-context" learning (e.g. in sequence #1 learn basic math, in #2 learn typo and correct spelling, ...) is studied and recently applied to multimodal learning, and this work is first application for video learning
#### Approach
- vision encoder
    - Normalizer-Free ResNet (NFNet) F6
        - performance-efficacy tradeoff
        - frozen in main training
        - pretrained to match with text 
- text encoder
    - BERT
- encoder -> sample tokens -> interleaved attention -> feedfoward
- gated xattn-dense: "conditioning" for training-phase representation
### Questions & Comments
### Notes


## [Yu et al., 2022](https://arxiv.org/abs/2205.01917)
### Where am I?
- Figures at a glance
### Takeaways
- Training
    1-1. Image feeded to image encoder
    1-2. Text feeded to text decoder
    2. Contrastive loss for CLS of 1-1/1-2 outputs for image-text matching
    3. Multimodal text decoder - cross-attention between modalities to get capptioning
- Downstream tasks
    - Image encoder with classifier can be used for visual-only tasks
    - Image-text matching can be done with image encoder / text decoder, thanks to matching learnt CLS
    - Other multimodal tasks could be addressed with entire model
### Questions & Comments
- Why text decoder, not encoder?
### Notes

## [Jaegle et al., 2021](https://arxiv.org/abs/2103.03206)
### Where am I?
- 1. Introduction / 3. Methods
### Takeaways
#### 1. Introduction
- Byte-level input array is passed to K/V of attention to be queried by latent array, which provides input-format independent representation
#### 3. Methods
- Clustering with latent factor as centre
    - No masks, no causal relationship
- How can quadratic complexity in transformer directly fed with visiual/audio inputs addressed?
    - Number of latent factor dimensions is much smaller
- Latent factor used as Transformer input
- Overlayed cross-attention/Transformer blocks with optional weight sharing deal with latent factor dimension bottleneck
- Position embedding hired for spatial information
    - Fourier features
### Questions & Comments
- 
### Notes



## template
### Where am I?
### Takeaways
### Questions & Comments
### Notes
