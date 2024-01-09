 KDGC-Knowledge-Computing-Laboratory
# 客服领域大模型测评论文（v1.0版本）
题目：XXX：A Chinese Operator Customer Service Large Language Models Benchmark 
__摘要__
大型语言模型 (LLM) 的最新进展在各种自然语言处理 (NLP) 任务中展现出广泛的前景。LLM 在特定领域的应用，例如运营商领域，越来越受到关注。但是【llm在运营商领域的问题】
1.运营商领域测评基准缺乏，目前开源的大模型基本都是通用大模型，因此评测基准也都是在通用领域上的评测，缺乏对行业尤其是对运营商行业的效果探索。
2.通用大模型没有注入运营商领域知识难以投入实际生产场景应用。
为了能够评估在运营商客服领域多类特定场景任务上的效果，我们构建了【论文题目】。
【我们的工作】在工作中，我们收集整理仿真了运营商领域【多少】类场景数据，包括客服话前、话中、话后三大类场景，并通过构造运营商领域微调数据集，将行业知识注入大模型，微调训练运营商NLP任务、运营商多轮对话、运营商检索问答3类任务大模型。
【实验结果】为了评估这些任务，我们通过对【多少大模型】上测试zero shot，few shot以及微调表现。我们的benchmark is releasde at【链接】。
## 项目背景（为什么选择测试这些大模型）
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
__任务结构评测图__

![231cfea9224ea915887ef43401fd8e3](https://github.com/zsjslab/KDGC-Knowledge-Computing-Laboratory/assets/155947032/5dff7458-cc18-4273-91a8-4fb60235197a)

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

（2）分能力介绍（参考论文《LAiW: A Chinese Legal Large Language Models Benchmark A Technical Report》）
1）话前
话前的各类能力主要是在客服人员联系用户之前给用户主动提供服务，帮助解决一些简单常见问题，减少坐席接入话务量。
●话前NLP能力：主要是通过对之前的话务数据分析是否具备潜在商机可以挖掘。
●话前知识问答：用户出现一些例如宽带，流量等问题，先接入数字人。它们可以回答一些简单的查询话费、流量等问题，减轻坐席人员的压力。。
●多轮对话：用户在接入真正的坐席之前，会先接入语音导航多轮对话系统回答用户的一些简单问题。
2）话中
话中服务主要是指在客户与客服进行实际对话时提供各类服务能力，用于帮助后台坐席人员提高服务效率，减少每通话务处理时间。
●话中NLP能力：包括2大类，第一类是意图识别任务，主要是对各种用户与客服对话文本识别用户的意图，比如是业务办理时判断是想办理'宽带类'业务还是'积分类'业务，比如在用户询问套餐时判断想询问套餐的内容还是需要推荐套餐。第二类是信息抽取任务，主要是智能填单，将对话中的关键信息抽取出来，填入固定表单，减轻人工操作。
●话中知识问答：包括知识问答和能力调用。知识问答是针对用户的问题，参考相关知识库文档给用户回答。能力调用是指用户询问流量、套餐剩余等信息，通过调用后台的多个接口能力进行回复。
●话中多轮对话：主要是多轮对话中的话术推荐场景，通过用户与客服对话交流过程中向坐席人员提供针对性的回复话术。
3）话后
话后服务是指客户与客服结束对话之后提供的各类NLP服务能力，用于帮助后台运营人员分析话务数据和追踪投诉问题进展，确保客户问题可以得到满意解决。智能话务分析是通过对话务来源、关键信息、投诉倾向性、携号转网倾向性等常见问题的分析，探明用户集中需求，以期后续改进减少话务量。智能投诉分析重点是对客服投诉工单中的投诉热点以及投诉类型分析，提升用户满意度。

\subsection{Pre-call scenarios}

The capabilities required for the pre-call scenario are mainly to provide proactive service to the user before the customer service agent contacts the user. It helps to solve simple common problems and reduces the volume of agent access calls.

\begin{itemize}
   
    \item NLP capability: Mainly by analyzing the previous call data to see if there are potential business opportunities that can be tapped, such as potential business opportunity mining tasks.
   
    \item Knowledge QA:  Users will first access the digital person when some questions about broadband, traffic, etc. The digital person can answer some simple inquiries about the phone bill, traffic, etc., to reduce the pressure of the agent.
   
    \item Multi-round Dialog: Before users access the real agent, they will first access the voice navigation multi-round dialog system to answer some simple questions from users.

\end{itemize}

\subsection{In-call scenarios}

In-call services mainly refer to the ability to provide various types of services when users have actual conversations with customer service. In-session services are used to help back-office agents improve service efficiency and reduce the processing time of each call.

\begin{itemize}
   
    \item NLP capability: including 2 categories, the first is the intent recognition task, mainly to identify the user's intent on various users and customer service dialogue text, such as business processing to determine whether they want to apply for 'broadband class' business or 'points class' business. The second category is information extraction tasks, mainly intelligent form filling, extracting key information in the conversation and filling in fixed forms to reduce manual operations.
   
    \item Knowledge Q\&A capability: includes knowledge quizzes and capability calls. Knowledge quizzes is to respond to the user's question by referring to the relevant knowledge base document to give the user an answer. Capability calls refers to the user asking for information such as traffic, package remaining, etc., and responding by invoking multiple interface capabilities in the backend.
   
    \item Multi-round Dialog capability: the main purpose is to generate replies, through the user and customer service dialog process to provide targeted reference.

\end{itemize}


\subsection{Post-call scenarios}

Post-call service refers to all kinds of NLP service capabilities provided after the users have finished the conversation with the customer service. It is used to help back-office operators analyze call data and track the progress of complaint issues to ensure that customer issues can be resolved satisfactorily. Intelligent call analysis is used to analyze common problems such as call sources, key information, complaint tendency, and tendency to switch to a new network, etc., so as to find out the centralized needs of users, with a view to making subsequent improvements to reduce the call volume. Intelligent complaint analysis focuses on the analysis of complaint hotspots and complaint types in customer service complaint work orders to improve user satisfaction.
## 客服领域任务数据集构造
为了评估以上这些能力和对应的任务，我们整合构建了运营商客服测评数据和微调数据集，基于开源（open-source data）和真实业务仿真数据（private data）。测评数据和微调数据集具有类似的流程，如图2所示，都包括数据脱敏、数据清洗、答案/标签构造以及人工核对。第一数据脱敏：由于客服数据中存在多种用户的手机号、身份证号码等敏感信息，为了确保用户隐私安全，我们数值类文本通过正则表达式识别，并脱敏处理；针对字符型文本使qwen14B-chat识别例如姓名、地址等信息进行脱敏处理。第二数据清洗：对脱敏后文本去除下划线、空格等无实际意义的字符等。第三答案/标签数据构建：包括三种方法，1）专家标注，2）基于关键词筛选，3）通过场景描述让大模型仿真生成符合要求的数据。第四：人工核对，将所有的数据经过3个业务专家和3名NLP技术专家核对，确保数据的可靠性。
下面分别介绍运营商客服测评数据和微调数据集。

	To evaluate the above capabilities and corresponding tasks, we integrated and constructed operator customer service evaluation datasets and fine-tuning datasets, based on open source data and real business simulation data (private data). The evaluation datasets and fine-tuning datasets have a similar process, as shown in Figure 2, which includes data desensitization, data cleaning, answer/label construction, and manual verification. First, data desensitization: because there are sensitive information such as phone numbers and ID card numbers of multiple users in customer service data, in order to ensure user privacy and security, we identify and desensitize numerical texts through regular expressions. We utilize qwen-14B-chat for text recognition, such as name, address, and other information. Second, data cleaning: remove meaningless characters such as underline and spaces from the desensitized text. Third, answer/label construction: includes three methods: 1) expert annotation, 2) keyword filtering, 3) using scenario description to generate data that meets the requirements through simulation of the large model. Fourth, manual verification: all these datasets are verified by three business experts and three NLP technical experts to ensure the reliability of the data.
The following introduces the operator customer service evaluation datasets and fine-tuning datasets.

![28f67d2a2ccb6559938218f23d90127](https://github.com/zsjslab/KDGC-Knowledge-Computing-Laboratory/assets/155947032/51102477-dc55-40b5-a8ff-7f5e0c915613)

图2数据构造过程示例
### 1.测评数据集-许银
为了测评客服领域大模型的能力，我们整合开源和私域数据构建了运营商客服评估数据集，包括文本分类、信息抽取和多轮对话任务，共21个数据集。其中开源数据包括【CSDS】【MUSIED】，CSDS数据集由于包含多轮对话、意图以及摘要信息，又被拆分为多个任务数据集，包括CSDS-MRD、CSDS-IR和CSDS-AE。MUSIED数据集包含用户评论以及意图信息，因此我们将其构建为意图识别数据集MUSIED-IR。此外我们也通过图2的方法构造了私域数据集。具体统计信息如表XX所示。

To evaluate the capability of LLMs in the customer service domain, we integrated open-source and private data to construct  datasets for evaluating operator customer service, including text classification, information extraction, and multi-round dialogue tasks, totaling 21 datasets. The open-source data includes CSDS[X] and MUSIED[X]. The CSDS dataset, which contains multiple rounds of dialogue, intent, and summary information, has been split into multiple task datasets, including CSDS-MRD, CSDS-IR, and CSDS-AE. The MUSIED dataset contains user comments and intent information, so we construct it as the intent recognition dataset MUSIED-IR. In addition, we also constructed a private dataset using the method shown in Figure 2. The specific statistical information is shown in Table XX.



<table class="MsoNormalTable" border="0" cellspacing="0" style="border-collapse:collapse;width:405.8500pt;margin-left:1.1000pt;
mso-table-layout-alt:fixed;border:none;mso-padding-alt:0.7500pt 0.7500pt 0.7500pt 0.7500pt ;"><tbody><tr style="height:12.8000pt;"><td width="57" valign="center" style="width:34.4500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:1.0000pt solid rgb(203,205,209);
mso-border-left-alt:0.5000pt solid rgb(203,205,209);border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:1.0000pt solid rgb(203,205,209);mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Scenes</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:1.0000pt solid rgb(203,205,209);mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Dataset</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:1.0000pt solid rgb(203,205,209);mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:1.0000pt solid rgb(203,205,209);mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Major&nbsp;Task&nbsp;Type</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:1.0000pt solid rgb(203,205,209);mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Minor&nbsp;Task&nbsp;Type</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:1.0000pt solid rgb(203,205,209);mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Size</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:1.0000pt solid rgb(203,205,209);mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Metrics</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="57" valign="center" rowspan="2" style="width:34.4500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:1.0000pt solid rgb(203,205,209);
mso-border-left-alt:0.5000pt solid rgb(203,205,209);border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:none;border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Pre-call</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">PBO</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Potential&nbsp;Business&nbsp;Opportunities</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">100</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">DHMRD</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Digital&nbsp;Human&nbsp;Multi-Round&nbsp;Dialogue</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Multi-Round&nbsp;Q&amp;A&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Multi-Round&nbsp;Q&amp;A&nbsp;</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">20</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Uni,&nbsp;GT,&nbsp;ELO</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="57" valign="center" rowspan="10" style="width:34.4500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:1.0000pt solid rgb(203,205,209);
mso-border-left-alt:0.5000pt solid rgb(203,205,209);border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:none;border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">In-call</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CTIR</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Conversation&nbsp;Text&nbsp;Intent&nbsp;Recognition</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">225</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">PIRC</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Package&nbsp;Intent&nbsp;Recognition&nbsp;of&nbsp;&nbsp;Consumption</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">1013</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">PIR16</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Package&nbsp;Intent&nbsp;Recognition_16&nbsp;classes</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">277</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">PIR3</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Package&nbsp;Intent&nbsp;Recognition_3&nbsp;classes</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">310</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">IAKQA</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Intelligent&nbsp;Assistant-Knowledge&nbsp;Q&amp;A</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Knowledge&nbsp;Q&amp;A&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Knowledge&nbsp;Q&amp;A</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">54</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">RougeL</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">IACC</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Intelligent&nbsp;Assistant-Capability&nbsp;Call</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Knowledge&nbsp;Q&amp;A&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Capability&nbsp;call</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">20</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">RougeL</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">IFF</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Intelligent&nbsp;Form&nbsp;Filling&nbsp;for&nbsp;Installation&nbsp;and&nbsp;Maintenance</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Information&nbsp;extraction</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">100</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">f1_score</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CSDS-MRD</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CSDS-Multi-Round&nbsp;Dialogue</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Multi-Round&nbsp;Q&amp;A&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Multi-Round&nbsp;Q&amp;A&nbsp;</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">100</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Uni,&nbsp;GT,&nbsp;ELO</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CSDS-IR</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CSDS-Intent&nbsp;Recognition</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">1000</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">MUSIED-IR</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">MUSIED-Intent&nbsp;Recognition</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">1000</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="57" valign="center" rowspan="9" style="width:34.4500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:1.0000pt solid rgb(203,205,209);
mso-border-left-alt:0.5000pt solid rgb(203,205,209);border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:none;border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Post-call</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CTUD</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Call&nbsp;Traceability&nbsp;of&nbsp;User&nbsp;Demands</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">320</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CTT</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Call&nbsp;Traceability&nbsp;of&nbsp;Triggers</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">160</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CS</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Call&nbsp;Summary</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Information&nbsp;extraction</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">91</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">RougeL</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">COC-CR</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Complaint&nbsp;Order&nbsp;Classification&nbsp;for&nbsp;Complaint&nbsp;Reason</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">1000</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">COC</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Complaint&nbsp;Order&nbsp;Classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">1000</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CHD</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Complaint&nbsp;Hotspot&nbsp;Discovery</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Information&nbsp;extraction</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">100</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">f1_score</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CTA</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Complaint&nbsp;Tendency&nbsp;Analysis</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">100</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">ATNT</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Analysis&nbsp;on&nbsp;Tendency&nbsp;of&nbsp;Number&nbsp;Portability&nbsp;and&nbsp;Network&nbsp;Transfer</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Text&nbsp;classification</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">100</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">accuracy<font face="宋体">，</font><font face="Calibri">instruction_follow</font></span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr><tr style="height:12.8000pt;"><td width="71" valign="center" style="width:42.9500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CSDS-AE</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">CSDS-Abstract&nbsp;Extraction</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="136" valign="center" style="width:81.6500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">NLP&nbsp;task</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="91" valign="center" style="width:55.0500pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">Information&nbsp;extraction</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="84" valign="center" style="width:50.5000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">1000</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td><td width="99" valign="center" style="width:59.6000pt;padding:0.0000pt 4.3000pt 0.0000pt 4.3000pt ;border-left:none;
mso-border-left-alt:none;border-right:1.0000pt solid rgb(203,205,209);mso-border-right-alt:0.5000pt solid rgb(203,205,209);
border-top:none;mso-border-top-alt:0.5000pt solid rgb(203,205,209);border-bottom:1.0000pt solid rgb(203,205,209);
mso-border-bottom-alt:0.5000pt solid rgb(203,205,209);"><p class="MsoNormal"><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;">RougeL</span><span style="font-family:Calibri;mso-fareast-font-family:宋体;mso-bidi-font-family:'Times New Roman';
font-size:10.5000pt;mso-font-kerning:1.0000pt;"><o:p></o:p></span></p></td></tr></tbody></table>

There are various text-based tasks in the field of operator customer service. We divide these tasks into three categories, NLP task, Multi-round dialogue task and knowledge Q&A task. And we summarize the details of datasets for each task in Appendix B.

NLP Datasets 	We construct 17 NLP datasets. These datasets can be recognized by the following 2 tasks: 1) Text Classification, including 13 datasets, such as PBO and CTIR. 2) Information Extraction, including IFF, CS, CHD and CSDS-AE. 	

Multi-round Dialogue Datasets	To evaluate the generation ability in multiple-round dialogues of LLMs，we construct 2 multi-round dialogue datasets, DHMRD and CSDS-MDR, contain the conversations between users and agents in real-life scenarios.

Knowledge Q&A Dataset	We build 2 datasets to evaluate the question answering ability of LLMs. IAKQA requires answering the question according to the given reference, and IACC is for capability call.

## 评测代码


## 项目参与者


## 声明
本项目仅供学术研究使用，严禁用于商业。我们对使用该项目的任何问题，风险或不利后果不承担任何责任。

## 致谢
本项目在构建时，参考了以下开源项目，在此对相关项目和研究开发人员表示感谢。

## 引用


