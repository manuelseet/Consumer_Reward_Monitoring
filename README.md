# Consumer_Reward_Monitoring
#### Single-trial classification of reward-based product evaluations, to develop consumer prediction applications for industry neuromarketing. 

Proof-of-concept work published in IEEE EMBC 2021 [(Seet et al., 2021)]. 

Final solution with customized ML architecture and pipeline is proprietary. 


## EEG Processing

In this proof of concept study, wearable EEG signals were passed through an [automated preprocessing pipeline]. 
The preprocessed EEG signal underwent band-pass filtering to obtain signals in the following canonical bands: 
- Theta (θ : 4- 8 Hz)
- Alpha  (α : 8 - 12 Hz)
- Beta (β : 12 - 30 Hz)
- Gamma (γ : 30- 40 Hz). 

#### Neurometric Features
Two feature types were extracted:
1. Relative power spectral density (PSD) across the 4 frequency bands were estimated using Welch's method. PSD, which captures activation information in the frequency domain, showed differences most prominently in the α, β and γ band. 

2. Approximate entropy (ApEn) was calculated for each frequency band, in accordance to the procedure documented by [Bruhn et al. (2000)]. We used window size, m = 2, and noise filtering level, r = 0.2xSD of signal amplitude values. ApEn, which captures nonlinear dynamic information in the time domain, showed differences most prominently in the θ, α, β bands.

These scalp topoplots (heatmaps) below illustrate the mean difference between the two consumer reward-decision classes: 

<img src="https://github.com/manuelseet/Consumer_Reward_Monitoring/blob/main/EMBC_newtopoplots_db.png" alt="topoplots" width = 850/>


## References
Seet, M.S., Devarajan, A.V., Low, J.J.L., Hamano., J., Saba, M., Thakor, N. & Dragomir, A. (2021). Wearable EEG Entropy and Spectral Measures for Classification of Consumer Reward-Based Evaluation of Odor Stimuli. *43rd Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC2021)*. November 2021.

Bruhn, J., Röpcke, H., & Hoeft, A. (2000). Approximate entropy as an electroencephalographic measure of anesthetic drug effect during desflurane anesthesia. The Journal of the American Society of Anesthesiologists, 92(3), 715-726.

[(Seet et al., 2021)]: https://www.semanticscholar.org/paper/Wearable-EEG-Entropy-and-Spectral-Measures-for-of-Seet-Devarajan/012f5b55427881e847c578cab6786bdfa9a66a84

[automated preprocessing pipeline]: https://github.com/manuelseet/wearableEEG_preprocessing

[Bruhn et al. (2000)]: https://pubs.asahq.org/anesthesiology/article/92/3/715/39710/Approximate-Entropy-as-an-Electroencephalographic 
