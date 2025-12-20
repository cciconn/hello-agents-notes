# Task02：智能体发展史学习笔记

## 学习内容
1. 基于符号与逻辑的早期智能体：符号主义，也被称为“逻辑AI”或“传统AI”，核心是基于一套明确规则对符号进行操作，其“智慧”非通过自主学习获得。
1.1 物理符号系统假说
  - 两个核心论断：充分性论断和必要性论断
  - 物理符号系统假说（PhysicalSymbol SystemHypothesis, PSSH）大胆地宣称：智能的本质，就是符号的计算与处理。
  - 这个假说具有深远的影响。它将对人类心智这一模糊、复杂的哲学问题的研究，转化为了一个可以在计算机上进行工程化实现的具体问题。
1.2 专家系统
  - 核心目标，是模拟人类专家在特定领域内解决问题的能力。它通过将专家的知识和经验编码成计算机程序，使其能够在面对相似问题时，给出媲美甚至超越人类专家的结论或建议。
  - 核心组件：知识库和推理机
    - 知识库：用于存放领域专家的知识和经验。知识表示是构建知识库的关键，包括产生式规则，例如一系列“IF-THEN”形式的条件语句。
    - 推理机：它是一个通用的程序，其任务是根据用户提供的事实，在知识库中寻找并应用相关的规则，从而推导出新的结论。它有两种工作方式：正向链（数据驱动）和反向链（目标驱动）。
1.3 SHRDLU
  - 旨在构建一个能在“积木世界”这一微观环境中，通过自然语言与人类流畅交互的综合性智能体。它首次将多个独立的人工智能模块（如语言解析、规划、记忆）集成在一个统一的系统中，并使它们协同工作：自然语言理解、规划与行动、记忆与回答。
1.4 符号主义面临的根本性挑战
  - 常识知识与知识获取瓶颈：完全依赖于其知识库的质量和完备性
  - 框架问题与系统脆弱性：在处理动态变化的世界时也遇到了逻辑上的困境
2. 构建基于规则的聊天机器人
3. 马文明斯基的心智社会
3.1 对单一整体智能模型的反思：该类模型试图用一种统一的表示和推理机制来解决所有问题，但这与我们观察到的自然智能（尤其是人类智能）的运作方式相去甚远。
3.2 作为协作体的智能：简单的智能体被组织起来，形成功能更强大的机构（Agency）。一个机构是一组协同工作的智能体，旨在完成一个更复杂的任务。
3.3 对多智能体系统的理论启发
  - 如果一个心智内部的智能，是通过大量简单智能体的协作而涌现的，那么，在多个独立的、物理上分离的计算实体（计算机、机器人）之间，是否也能通过协作涌现出更强大的“群体智能”？
  - 去中心化控制、涌现式计算、智能体的社会性
4. 学习范式的演进与现代智能体
4.1 从符号到联结
  - 联结主义（Connectionism）在20世纪80年代重新兴起。与符号主义自上而下、依赖明确逻辑规则的设计哲学不同，联结主义是一种自下而上的方法，其灵感来源于对生物大脑神经网络结构的模仿。
  - 知识的分布式表示、简单的处理单元、通过学习调整权重
4.2 基于强化学习的智能体：是专注于解决序贯决策问题的学习范式。它并非直接从标注好的静态数据集中学习，而是通过智能体与环境的直接交互，在“试错”中学习如何最大化其长期收益。是专注于解决序贯决策问题的学习范式。它并非直接从标注好的静态数据集中学习，而是通过智能体与环境的直接交互，在“试错”中学习如何最大化其长期收益。
4.3 基于大规模数据的预训练
  - 从特定任务到通用模型
    - 预训练阶段：自监督学习海量文本数据库，训练出一个超大规模的神经网络模型。
    - 微调阶段：针对特定的下游任务，只需使用少量该任务的标注数据对模型进行微调，即可让模型适应对应任务。
  - 大型语言模型的诞生与涌现能力
    - 上下文学习
    - 思维链推理
4.4 基于大语言模型的智能体
  <img width="1512" height="680" alt="image" src="https://github.com/user-attachments/assets/636de2eb-1fef-45a4-8a44-6363026d4454" />
4.5 智能体发展关键节点概览
    三大思潮主导着不同时期的研究范式：符号主义、联结主义、行为主义
  



        
## 习题
1.
- 充分性论断：符号操作足以实现智能。
  必要性论断：智能必须通过符号操作来实现。
- 知识获取的瓶颈、常识无法用简单的符号逻辑来表示、用符号推理来表示现实世界的模糊和不确定性需要无限的计算资源
- LLM驱动的智能体在严格意义上并不符合物理符号系统假说，因为它并非基于该假说预设的显式符号逻辑体系。相反，它的成功削弱了该假说的“必要性”论断，并展示了一种超越经典符号主义的智能实现路径。
2.
- 从技术角度，简单的“ifthen”的模式无法解决需要多维度思考的复杂问题；从法律角度，任何决策的法律责任主体无法明确
- “知识图谱+深度学习+概率推理”的混合系统，强调可解释性、人机协同与持续安全学习。
- 在法规明确、安全至上或需完全透明决策的领域（如金融合规、税务审核）规则系统仍更可靠。
3.
import re
import random

# 定义规则库：模式(正则表达式) -> 响应模板列表
rules = {
    r'I need (.*)': [
        "Why do you need {0}?",
        "Would it really help you to get {0}?",
        "Are you sure you need {0}?"
    ],
    r'Why don\'t you (.*)\?': [
        "Do you really think I don't {0}?",
        "Perhaps eventually I will {0}.",
        "Do you really want me to {0}?"
    ],
    r'Why can\'t I (.*)\?': [
        "Do you think you should be able to {0}?",
        "If you could {0}, what would you do?",
        "I don't know -- why can't you {0}?"
    ],
    r'I am (.*)': [
        "Did you come to me because you are {0}?",
        "How long have you been {0}?",
        "How do you feel about being {0}?"
    ],
    r'.* mother .*': [
        "Tell me more about your mother.",
        "What was your relationship with your mother like?",
        "How do you feel about your mother?"
    ],
    r'.* father .*': [
        "Tell me more about your father.",
        "How did your father make you feel?",
        "What has your father taught you?"
    ],
    # 新规则1：处理工作相关话题
    r'.* (job|work|career|profession) .*': [
        "Tell me more about your {0}.",
        "How do you feel about your {0}?",
        "What challenges do you face in your {0}?",
        "Does your {0} fulfill you?"
    ],
    
    # 新规则2：处理学习/教育相关话题
    r'.* (study|learn|education|school|university|class) .*': [
        "What are you studying?",
        "How do you find your studies?",
        "What do you hope to achieve through learning?",
        "Tell me more about your educational experiences."
    ],
    
    # 新规则3：处理爱好和兴趣
    r'.* (hobby|hobbies|interest|like to|enjoy) .*': [
        "Why do you enjoy {0}?",
        "How did you get interested in {0}?",
        "What do you like most about {0}?",
        "How does {0} make you feel?"
    ],
    
    # 新规则4：处理未来计划/目标
    r'I want to (.*)': [
        "Why do you want to {0}?",
        "What would it mean to you if you could {0}?",
        "How would your life change if you {0}?",
        "What's stopping you from {0}?"
    ],
    
    # 新规则5：处理日常活动
    r'.* (today|yesterday|this week) .*': [
        "What happened {0}?",
        "How did that make you feel?",
        "Tell me more about what you did {0}.",
        "What was the most significant thing that happened {0}?"
    ],
    r'.*': [
        "Please tell me more.",
        "Let's change focus a bit... Tell me about your family.",
        "Can you elaborate on that?"
    ]
}

# 扩展的规则：专门用于捕获关键信息
memory_capture_rules = {
    r'my name is (.*)': 'name',
    r'I am called (.*)': 'name',
    r'you can call me (.*)': 'name',
    r'I\'m (.*) years old': 'age',
    r'I am (.*) years old': 'age',
    r'my age is (.*)': 'age',
    r'I work as a (.*)': 'job',
    r'I am a (.*)': 'job',
    r'my job is (.*)': 'job',
    r'I work at (.*)': 'company',
    r'I study (.*)': 'study',
    r'I\'m studying (.*)': 'study',
    r'I live in (.*)': 'location',
    r'I\'m from (.*)': 'location'
}

# 定义代词转换规则
pronoun_swap = {
    "i": "you", "you": "i", "me": "you", "my": "your",
    "am": "are", "are": "am", "was": "were", "i'd": "you would",
    "i've": "you have", "i'll": "you will", "yours": "mine",
    "mine": "yours", "myself": "yourself", "yourself": "myself", "i'm": "you are", "you're": "I am", "we": "you", "us": "you",
    "our": "your", "we're": "you are", "myself": "yourself",
    "yourself": "myself", "my job": "your job", "my work": "your work"
}

# 上下文记忆系统
class ElizaMemory:
    def __init__(self):
        self.memory = {
            'name': None,
            'age': None,
            'job': None,
            'company': None,
            'study': None,
            'location': None,
            'recent_topics': []
        }
        self.conversation_history = []
    
    def capture_info(self, user_input):
        """从用户输入中提取并存储关键信息"""
        captured_info = False
        
        for pattern, key in memory_capture_rules.items():
            match = re.search(pattern, user_input, re.IGNORECASE)
            if match:
                value = match.group(1).strip()
                self.memory[key] = value
                print(f"[DEBUG] Captured {key}: {value}")
                captured_info = True
                
                # 记录到对话历史
                self.conversation_history.append(f"User mentioned their {key}: {value}")
        
        return captured_info
    
    def get_memory_response(self):
        """基于记忆生成个性化响应"""
        responses = []
        
        # 如果有名字，使用名字称呼
        if self.memory['name']:
            name_responses = [
                f"{self.memory['name']}, tell me more about that.",
                f"I'm listening, {self.memory['name']}. Please continue.",
                f"That's interesting, {self.memory['name']}. What makes you feel that way?"
            ]
            responses.append(random.choice(name_responses))
        
        # 基于已知信息提问
        if self.memory['job']:
            job_responses = [
                f"As a {self.memory['job']}, how does that affect your perspective?",
                f"Does being a {self.memory['job']} influence how you feel about this?",
                f"How does this relate to your work as a {self.memory['job']}?"
            ]
            responses.append(random.choice(job_responses))
        
        if self.memory['age'] and random.random() > 0.7:  # 30%概率提及年龄
            age_responses = [
                f"At {self.memory['age']} years old, what do you think about this stage of your life?",
                f"How does being {self.memory['age']} affect your outlook on this?"
            ]
            responses.append(random.choice(age_responses))
        
        if responses:
            return random.choice(responses)
        return None
    
    def remember_context(self, user_input):
        """记住对话上下文"""
        # 简单的关键词提取
        keywords = ['work', 'family', 'friend', 'love', 'hate', 'happy', 'sad', 'angry']
        for word in keywords:
            if word in user_input.lower():
                if word not in self.memory['recent_topics']:
                    self.memory['recent_topics'].append(word)
                break
        
        # 保持最近话题列表大小合理
        if len(self.memory['recent_topics']) > 5:
            self.memory['recent_topics'] = self.memory['recent_topics'][-5:]
    
    def reference_memory(self):
        """引用记忆中的信息"""
        references = []
        
        if self.memory['name']:
            references.append(f"I remember you're {self.memory['name']}")
        
        if self.memory['job']:
            references.append(f"you work as a {self.memory['job']}")
        
        if self.memory['age']:
            references.append(f"you're {self.memory['age']} years old")
        
        if self.memory['location']:
            references.append(f"you're from {self.memory['location']}")
        
        if references:
            return "I know " + ", ".join(references) + ". "
        return ""
    
    def summarize_memory(self):
        """显示当前记忆内容"""
        summary = "What I remember about you:\n"
        for key, value in self.memory.items():
            if value and key != 'recent_topics':
                summary += f"- {key}: {value}\n"
        
        if self.memory['recent_topics']:
            summary += f"- Recent topics: {', '.join(self.memory['recent_topics'])}\n"
        
        return summary

# 初始化记忆系统
memory = ElizaMemory()

def swap_pronouns(phrase):
    """对输入短语中的代词进行第一/第二人称转换"""
    words = phrase.lower().split()
    swapped_words = [pronoun_swap.get(word, word) for word in words]
    return " ".join(swapped_words)

def respond(user_input):
    """根据规则库和记忆生成响应"""
    # 1. 首先尝试捕获关键信息
    memory.capture_info(user_input)
    
    # 2. 记住对话上下文
    memory.remember_context(user_input)
    
    # 3. 每3-5轮对话，尝试引用记忆（30%概率）
    if len(memory.conversation_history) > 0 and random.random() > 0.7:
        memory_response = memory.get_memory_response()
        if memory_response:
            return memory_response
    
    # 4. 匹配标准规则
    for pattern, responses in rules.items():
        match = re.search(pattern, user_input, re.IGNORECASE)
        if match:
            # 捕获匹配到的部分
            captured_group = match.group(1) if match.groups() else ''
            # 进行代词转换
            swapped_group = swap_pronouns(captured_group)
            # 从模板中随机选择一个并格式化
            base_response = random.choice(responses).format(swapped_group)
            
            # 随机决定是否添加记忆引用（20%概率）
            if random.random() > 0.8:
                memory_ref = memory.reference_memory()
                return memory_ref + base_response
            else:
                return base_response
    
    # 如果没有匹配任何特定规则，使用最后的通配符规则
    return random.choice(rules[r'.*'])

# 主聊天循环
if __name__ == '__main__':
    print("=" * 50)
    print("Enhanced ELIZA Therapist with Memory")
    print("Type 'quit' to exit, 'memory' to see what I remember")
    print("=" * 50)
    print("\nTherapist: Hello! How can I help you today?")
    
    conversation_count = 0
    
    while True:
        user_input = input("\nYou: ").strip()
        
        # 特殊命令
        if user_input.lower() == 'quit':
            print(f"Therapist: Goodbye. It was nice talking to you, {memory.memory['name'] if memory.memory['name'] else ''}.")
            break
        elif user_input.lower() == 'memory':
            print(f"Therapist: {memory.summarize_memory()}")
            continue
        elif user_input.lower() == 'what do you know about me?':
            print(f"Therapist: {memory.reference_memory()}")
            continue
        
        conversation_count += 1
        
        # 生成响应
        response = respond(user_input)
        
        # 每5轮对话后，尝试主动使用记忆
        if conversation_count % 5 == 0 and memory.memory['name']:
            personalized_greeting = f"\nTherapist: By the way {memory.memory['name']}, "
            print(personalized_greeting + response)
        else:
            print(f"Therapist: {response}")

- 架构本质：ELIZA是基于规则的模式匹配器，ChatGPT是基于数据的神经网络生成器。智能水平：ELIZA只能机械反射预定义模式，ChatGPT具备深层语义理解和创造性生成能力。学习方式：ELIZA的知识需人工编码且无法进化，ChatGPT能从海量数据中自主学习并持续优化。

4.
- 可能会任务中断或者从失效开始重复某一层的搭建；去中心化的优势：单点故障不影响整体功能、易于单个模块的更换或增删，去中心化的劣势：难以保证全局的一致性、无法迅速识别单点故障对全局的影响。
- 关联：都强调通过任务分解和分工协作来协同处理负责问题；区别：现代系统是拥有强大认知能力的LLM智能体，其协作是高效协同；而“心智社会”是由大量简单智能体通过交互涌现出智能。
- 在大语言模型时代，“心智社会”理论的核心思想“智能源于协作而非单体全能”依然适用，只是协作的基本单元从简单智能体升级为拥有强大认知能力的智能体。
5.
- 通过与自我对弈，不断探索各种走法，仅以最终胜负为反馈信号，反向优化每一步的决策策略。
- 适合序贯决策，因其核心是优化长期回报，能处理延迟奖励。数据本质区别：监督学习依赖预先标注的静态数据，强化学习依赖与环境交互产生的动态序列数据。
- 玩马里奥游戏的智能体
  - 监督学习：需要人类游玩录像及对应的操作标签。
  - 强化学习：仅需游戏模拟器和定义好的奖励规则。
  - 强化学习明显更合适。理由：监督学习受限于人类演示，而强化学习能通过试错自主发现更优策略，更符合游戏学习的本质。
- 大语言模型中强化学习的作用：关键作用是与人类价值观对齐。通过基于人类反馈的强化学习，利用人类对答案的偏好反馈作为奖励，微调模型生成更有帮助的回应。
6.
- 预训练范式的突破：它通过在海量原始数据上的自监督学习，让模型从数据分布中自行“涌现”出对世界的隐式理解。本质区别：预训练将知识获取从一项人力密集的“软件工程”，转变为一项计算密集的“数据挖掘”，从而跨越了规模和成本的壁垒。
- 问题：互联网数据包含真假掺半、偏见、暴力等有害内容；大量错误、过时、矛盾信息。缓解方法：进行严格的清洗、去重、过滤和分级，构建高质量核心数据集。
- “预训练-微调”作为构建通用智能基座的有效方法论，其核心地位在可预见的未来难以动摇。但它将被不断完善、扩展和超越。它不太可能像符号主义那样被彻底抛弃，而更可能演进为未来更强大、更通用范式的一个关键组成部分或初始阶段。
7.
- 方案：基于规则和逻辑的专家系统。手工编码代码规范、常见bug模式等规则库，通过语法分析和模式匹配进行审查。困难：规则爆炸，无法覆盖复杂场景；知识获取完全依赖专家，难以维护和扩展；缺乏对代码意图和业务逻辑的理解。
- 方案：进行端到端学习，将代码转为向量，训练模型检测缺陷或生成摘要。困难：严重依赖大量标注数据；泛化能力差，对训练集外代码效果骤降；模型是“黑箱”，难以提供具体、可解释的改进建议。
- 架构设计：一个以LLM为核心控制器的智能体，包含四大模块：规划模块：制定分层审查策略，动态调整优先级。记忆模块：存储项目规范、历史bug和团队偏好。工具模块：调用静态分析、单元测试、安全扫描等专业工具。反思模块：进行自我验证和置信度评估，确保建议可靠性。核心能力：LLM提供深度代码理解、跨文件推理能力，并能以自然语言生成建设性建议和进行对话。
- 知识来源：从人工编码几条规则 → 需要数万标注数据 → 预训练吸收全网代码知识，覆盖度实现质的飞跃。系统形态：从孤立、脆弱的规则系统 → 单一、数据依赖的模型 → 协同、可对话的智能助手。


## 实践记录
习题3.<img width="2400" height="1892" alt="02100fd9-f160-439d-81d2-b1f9d0a1a6ce" src="https://github.com/user-attachments/assets/c1e0d250-9e58-4108-843a-90d805ce441f" />


## 我的理解
智能体的演进正日益趋近于人类的处事模式。这主要体现在两个层面：一是人类丰富多维的信息表达方式，二是现实世界复杂不确定的环境特征。从早期的符号主义到如今的大语言模型，智能体似乎经历了一条从“在确定规则中推导结论”向“在模糊语境中探寻规律”的演化路径。当前基于大语言模型的智能体仍主要处理语言信息，而人类却同时通过动作、神情、声音乃至意念等多维渠道进行表达与交互。因此，未来的智能体必将朝着更接近“完整人”的方向继续进化。
