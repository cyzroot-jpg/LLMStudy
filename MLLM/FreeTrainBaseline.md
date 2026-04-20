
2026 Arxiv
1. 一些方法通过构造输入图像或指令的正负视图，利用对比解码（contrastive decoding）来缓解幻觉
    （Leng et al., 2024；
    Wang et al., 2024b；
    Favero et al., 2024；
    Tong et al., 2025）；
2. 另一些方法通过增强图像注意力或修正异常注意力图来改进
    （Liu et al., 2024；
    Huang et al., 2023；
    Zhu et al., 2024b）；
3. 还有一些方法利用外部目标检测模型
    （Yin et al., 2024；
    Zhou et al., 2024），
    或使用稳定扩散模型生成用于对比解码的不同视图
    （Zhang et al., 2025；
    Cao et al., 2025）。


AAAI-25
1. OPERA 研究导致幻觉的聚合模式，并利用这些模式抑制相应 token 的生成。
2. VCD 利用这样一个特性：模型在面对失真图像时更倾向于使用语言先验而非视觉信息。因此，失真图像与原图的响应在幻觉 token 上存在显著差异，VCD 通过对比这些差异来减少幻觉。
3. HALC 发现，当输入具有不同视野（field of view）的图像时，真实 token 的概率变化远大于幻觉 token。基于这一观察，该方法识别出更可靠的视觉上下文候选，并通过对比这些候选来减少幻觉。


AAAI-26
一些方法侧重于缓解数据偏差、提升视觉分辨率以及优化对齐机制。

训练方法
1. Lovenia et al.（2024）提出了一种技术，通过将原始类别、属性或数量信息替换为相似但错误的替代项，构建了约95,000个负样本。这种细粒度方法有效丰富了训练中的对比信号，从而增强模型鲁棒性。
2. Chen et al.（2024）提出 InternVL，将视觉编码器扩展至60亿参数，并支持宽度在1,664到6,144像素之间的图像输入。
3. Bi et al.（2024）提出了一种表示引导（representation steering）方法，有效缓解多模态模型中的幻觉问题。

近年来，对比解码被证明是一种有效的、无需训练（training-free）的幻觉缓解方法（Xiao et al., 2025）。

1. Leng et al.（2023）提出 VCD，通过对输入图像进行扰动生成一个负向logit分支，并从原始预测中减去该分支，从而抑制幻觉。
2. Wang et al.（2024）使用负向提示（negative prompt）来引导模型远离幻觉内容。
3. Huo et al.（2024）提出一种“上下文与文本感知的token选择策略”，在早期解码层中选择最有信息量的视觉token，从而增强有用上下文并抑制虚假幻觉。


CVPR 2024
1. VCD

CVPR 2025
评估指标：
CHAIR 是最常用的 VH 评估基准之一。
POPE 通过二分类框架评估 VH，使用 precision、recall 和 accuracy 等指标。
HALC 提出了离线 POPE（OPOPE）以提升 VH 评估能力。
MME 提供了对对象、属性等多方面的综合评估。

为了缓解 VH，研究者提出了多种策略，目前主要分为三类：

1. 后处理技术与自我修正方法
[18, 54] 以及 [46]
2. 基于人类反馈的方法（human feedback-based methods）
[26, 48]
3. 解码策略方法（decoding strategies）
[7, 10, 20, 60]



----------------------------解码方法论文--------------------------
1. HALC: Object Hallucination Reduction via Adaptive Focal-Contrast Decoding    ICML 2024
2. DoLa: Decoding by Contrasting Layers Improves Factuality in Large Language Models ICLR 2024
3. Mitigating object hallucinations in large vision-language models through visual contrastive decoding     CVPR 2024
4. Game on tree: Visual hallucination mitigation via coarse-to-fine view tree and game theory   emnlp 2024
5. Mitigating hallucinations in large vision-language models with instruction contrastive decoding  ACL 2024
6. Multi-Modal Hallucination Control by Visual Information Grounding    CVPR 2024
7. Mitigating Hallucinations in Multi-modal Large Language Models via Image Token Attention-Guided Decoding     NAACL 2025
8. Paying More Attention to Image: A Training-Free Method for Alleviating Hallucination in LVLMs    Arxiv 2024
9. OPERA: Alleviating Hallucination in Multi-Modal Large Language Models via Over-Trust Penalty and Retrospection-Allocation    CVPR 2024
10. IBD: Alleviating Hallucinations in Large Vision-Language Models via Image-Biased Decoding   CVPR 2025
11. Woodpecker: Hallucination Correction for Multimodal Large Language Models   SCIS 一区TOP
12. CoFi-Dec: Hallucination-Resistant Decoding via Coarse-to-Fine Generative Feedback in Large Vision-Language Models   MM 2025