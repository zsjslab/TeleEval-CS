# KDGC-Knowledge-Computing-Laboratory
## 客服领域大模型测评论文（v1.0版本）
题目：XXX：A Chinese Operator Customer Service Large Language Models Benchmark 
### 摘要
大型语言模型 (LLM) 的最新进展在各种自然语言处理 (NLP) 任务中展现出广泛的前景。LLM 在特定领域的应用，例如运营商领域，越来越受到关注。但是【llm在运营商领域的问题】
1.运营商领域测评基准缺乏，目前开源的大模型基本都是通用大模型，因此评测基准也都是在通用领域上的评测，缺乏对行业尤其是对运营商行业的效果探索。
2.通用大模型没有注入运营商领域知识难以投入实际生产场景应用。
为了能够评估在运营商客服领域多类特定场景任务上的效果，我们构建了【论文题目】。
【我们的工作】在工作中，我们收集整理仿真了运营商领域【多少】类场景数据，包括客服话前、话中、话后三大类场景，并通过构造运营商领域微调数据集，将行业知识注入大模型，微调训练运营商NLP任务、运营商多轮对话、运营商检索问答3类任务大模型。
【实验结果】为了评估这些任务，我们通过对【多少大模型】上测试zero shot，few shot以及微调表现。我们的benchmark is releasde at【链接】。
### 引言（为什么选择测试这些大模型）
（1）大模型发展迅速，引出运营商领域：
随着ChatGPT和GPT4相继提出，大模型（比如chatGPT、LLaMA、GLM、 ERNIE BOt、Baichuan）在很多NLP任务上都取得了令人惊喜的效果和广泛的关注。而且由于这些大模型不需要标注数据，使用zero-shot/few-shot即可取得显著效果，因此更广泛的场景和行业（法律、医疗、金融、生物等）中大模型的效果如何都引起了大家积极的探索，运营商客服也不例外。

（2）当前的测评体系和运营商大模型有哪些以及问题

【国内外测评体系】目前国内外提出了很多大模型测评基准。不同的基准关注不同的能力维度。例如MMLU，BIgbench、MMCU等主要关注通用领域的NLP能力。C-eval，AGIEval等关注在人类真实任务上的表现。还有一些面向各个领域的测评基准吧，例如医疗（taiyi）、金融（DISC-FinLLM）、法律（LAiW）等。但是这些基准难以真正了解在真实运营商场景上，大模型的表现。

【运营商大模型】在中文运营商客服领域，中国三大运营商陆续提出了垂直领域研发的大模型。中国电信发布Telechat大模型，中国联通提出“鸿湖“图文大模型，中国移动推出“九天客服大模型”。以上模型虽然是针对运营商领域，尤其是中国电信和和中国移动推出面向客服场景的大模型，但是这些模型目前都是闭源，而且重点是测评了大模型的对话能力，也没有将测评任务数据开源，缺乏对客服话前、话中、话后全场景多任务的科学系统评测。

（3）运营商客服领域特定，难点
【运营商客服描述】此外，运营商客服领域任务具有区别于其他领域的独特性，也使得难以通过开源的大模型和测评基准进行合理评估。（1）场景复杂，涵盖话前主动营销、话中坐席辅助以及话后运营分析3大类场景，每一大类场景又包含多类不同业务子场景；（2）服务对象多样化：不仅仅是用户，还包括一线人员、运营人员等，每一类对象都要根据需求提供不同的服务。（3）任务多元化：有多级联意图识别、信息抽取等NLP任务，也有话术推荐、知识问答等对话任务。（4）数据质量难控：由于在话中阶段主要是客服与用户的对话数据，受限于方言和语音转文本技术，导致获取的文本质量差异性较大，真实场景数据中不可避免存在错别字，语义不清等现象。（5）数据敏感性，对话数据中会涉及手机号、地址等敏感信息。考虑到运营商客服领域以上的独特性表现，为了真正了解在一系列真实运营商场景上大模型的表现，构建系统全面的运营客服领域测评基准不必可少。

（4）我们的工作
本文，我们率先提出了一个运营商客服领域全面的测评体系。（1）首先通过业务专家按照客服服务话前、话中、话后三个时间顺序维度划分【多类】场景真实客服场景，再归纳总结多类场景为客服NLP、知识问答、多轮问答三类能力（2）基于 chatGPT 按照运营商客服任务特征，我们仿真生成了 4000 多条的评估数据集。再针对真实数据通过处理构建多任务微调数据集，用于微调专注于客户服务 NLP、基于知识的问答和多轮问答的 LLM。（3）最后，我们评估了各种 LLM 在客户服务领域场景中的性能，包括开源模型、闭源模型和领域微调模型。我们还探讨了将客户服务领域知识通过微调注入到不同大模型的表现。
（5）我们的贡献
1.本文推出的运营商客服领域测评体系是第一个可以用于综合评估不同大模型在运营商客服领域话前、话中、话后能力的基准，是促进运营商客服领域高质量发展的重要驱动力。
2.我们梳理仿真21类任务【4000多条】测评数据集，以及【10多万条】微调数据，构建运营商客服NLP任务微调大模型、多轮对话大模型以及知识问答指令微调大模型。此外我们还专门针对运营商领域特定场景多级联标签分类任务构建多级联分类微调大模型。
3.在【多少大模型上】测评了运营商客服领域大模型，为指导客服领域实际落地应用提供了重要的参考价值。
## related work（加一下很多测评都有对话但是没有用运营商数据）-友志
### 1. 运营商领域大模型
先进大型语言模型（LLM）如ChatGPT系列（引用），在处理通用和专业领域的各种问题方面表现出了卓越的能力，许多研究人员开始尝试试复制 GPT 系列来开发 LLaMA（引用）、Bloom（引用）、GLM（引用）和 Qwen（引用）等开源基础模型。这些LLMs在各种自然语言处理 (NLP) 任务上表现出强大的性能，包括零样本和少样本学习场景。大模型的巨大潜能引发了各个领域的广泛兴趣和大量研究，例如医学（引用）和金融 （引用）。与这些领域非常相似，运营商领域也面临着大模型可能带来的潜在影响。
运营商领域拥有丰富的文本资源和应用场景，传统的NLP任务模型在运营商领域的应用存在一系列独特的挑战。首先，运营商领域知识错综复杂，充满了繁杂的术语和规则，导致专业知识的短缺（引用）。其次，标注数据的缺乏，加上注释过程成本高昂，阻碍了进展。第三，当前的自然语言处理模型的推理能力有限，难以完成长文本对话的理解和推理任务。最后，许多 NLP 模型的适应性较差，是为单任务性能而设计的，缺乏跨任务泛化能力（引用）。这些挑战强调了未来研究需要为不断发展的运营商领域开发更强大、适应性更强的 NLP 模型。
尽管LLM已经在各个领域展示了其潜力，但其在运营商行业的应用却相对匮乏。目前，在中文运营商客服领域，中国三大运营商陆续提出了垂直领域研发的大模型。中国电信发布Telechat大模型（引用），涵盖模型赋能数据中台、智能客服和智慧政务三个方向，主要是展现大模型在多轮对话，逻辑推理方面的内容。中国联通提出“鸿湖“图文大模型（引用），主要面向运营商增值业务，拥有8亿训练参数和20亿训练参数两个版本，可以实现以文生图、视频剪辑、以图生图等功能。中国移动推出“九天客服大模型”（引用），可根据用户提供的自然语言描述，解析问题并提供答案；还可与人工客服协作，分析历史沟通内容的语义和上下文，总结和归纳对话的重点和关键信息，为人工客服提供回复建议。以上模型虽然是针对运营商领域，尤其是中国电信和和中国移动特别推出面向客服场景的大模型。但是这些模型目前都是闭源，而且重点只测评了大模型的对话能力，没有从客服多任务多场景角度客观全面系统的搭建测评任务。
### 2. 领域大模型评测
LLMs的成功很大程度上取决于旨在用于评估其在特定领域的熟练程度的基准数据集。这些数据集在确定LLMs的最佳架构设计和指导这些专业领域的预训练和微调过程方面也发挥着关键作用。在预训练语言模型Bert时代，英文领域GLUE（引用）和superGLUE（引用）被提出，中文领域提出CLUE（引用），主要是用于测评各类传统的NLP任务，如情感分析、新闻文本分类、阅读理解等。在医学和金融等其他领域也可以观察到同样的情况，通过引入了 MultiMedQA（引用）和 FinFE （引用）等基准数据集来评估LLMs在这些领域的熟练程度。
尽管应用广泛，但传统的NLP评测基准已经不适合最近在复杂推理和解决问题任务上表现出强大能力的大型语言模型，如GPT3.5（引用）已经可以在典型的文本摘要任务中生成比"glod answer"更理想的摘要。为了评估LLM的优势和局限性，一些新的基准被提出用来评估LLM更广泛的知识和高级能力，主要是从传统NLP任务测评基准过渡到了AGIEval（引用）、CEval（引用）等模拟人类考试的评测基准。其中，[C-Eval](https://arxiv.org/abs/2305.08322) 由涵盖从人文到科学和工程等 52 个不同学科的考试题组成，旨在全面评估中国背景下LLM的高级知识和推理能力。TeleQnA（https://arxiv.org/abs/2310.15051）涵盖电信领域的各个学科包含 10000 个问题和答案，第一个公开的旨在评估电信领域大型语言模型 (LLM) 知识的基准数据集。，并没有使用电信客服真实的场景任务数据，也缺乏对客服话前、话中、话后全场景多任务的科学系统评测。
另外，一些研究人员建议，具有多轮交互的自然语言生成（NLG）应该成为核心评估方法。[llm_judge](https://arxiv.org/abs/2306.05685)构建了MT-bench一个开放式问题的英文多轮对话数据集，用来评估大模型多轮对话能力，并设计了Chatbot Arena一个聊天机器人竞技场，允许用户同时与两个LLM进行对话，然后利用GPT-4作为判官进行打分，验证LLM判别器和人类偏好之间的一致性，弥补了现有的基准测试在衡量人类偏好方面的不足。然而，以上这些基准鲜有包含运营商领域真实场景任务数据，亟需开发一个运营商领域大模型评估套件，以满足运营商领域大模型日益发展的需求。
## 客服领域评估任务基准（benchmark construction）

动机：
1.探测不同大模型包含的运营商客服领域知识情况。真正了解在一系列真实运营商场景上，大模型的表现以及优缺点；
2.探索对运营商多任务理解能力，构建的运营商客服评估基准包含广泛的客服领域任务，可以用于探索大模型对运营商客服多任务应用的能力
3.探索不同大模型提示/微调数据集对客服领域应用的影响，构建客服微调多任务数据集，微调客服任务大模型

我们在 运营商客服领域专家与人工智能专家 的共同努力下，从客服服务时间线角度和可实现性上对运营商客服领域的能力进行划分，创建了可扩展的客服多场景多任务测试体系。如图所示，目前我们将其分成了话前、话中、话后三大场景，共计15个基础任务，总结为3大类能力包括NLP能力、知识问答能力以及多轮对话能力：
![7313c6ebc28b4b27d371fa3e6f79478](https://github.com/zsjslab/KDGC-Knowledge-Computing-Laboratory/assets/155947032/2064eda0-6214-476c-99e3-9b101d037036)
