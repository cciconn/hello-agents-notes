# Task04：智能体经典范式构建学习笔记

## 学习内容
1. 环境准备与基础工具定义
1.1 安装依赖库：openai和python-dotenv
1.2 配置API密钥：在项目根目录下创建名为.env的文件
1.3 封装基础LLM调用函数
2. ReAct：由ShunyuYao于2022年提出，其核心思想是模仿人类解决问题的方式，将推理 (Reasoning) 与行动 (Acting) 显式地结合起来，形成一个“思考-行动-观察”的循环。
2.1 ReAct的工作流程
   <img width="1496" height="536" alt="image" src="https://github.com/user-attachments/assets/cdcf6ad1-241b-46f5-a927-a215b98dc041" />
2.2 工具的定义与实现
   <img width="1896" height="1888" alt="image" src="https://github.com/user-attachments/assets/103e8ab4-89b8-413a-8116-af34bd0b70d7" />
2.3 ReAct智能体的编码实现
   <img width="1896" height="1888" alt="image" src="https://github.com/user-attachments/assets/1d0cf8b3-105f-4fb7-88c8-2bb1cce7c9eb" />
2.4 ReAct 的特点、局限性与调试技巧
   （1）ReAct 的主要特点：高可解释性，动态规划与纠错能力，工具协同能力
   （2）ReAct 的固有局限性：对LLM自身能力的强依赖，执行效率问题，提示词的脆弱性，可能陷入局部最优
   （3）调试技巧：检查完整的提示词，分析原始输出，验证工具的输入与输出，调整提示词中的示例，尝试不同的模型或参数
3. Plan-and-Solve：顾名思义，这种范式将任务处理明确地分为两个阶段：先规划 (Plan)，后执行 (Solve)。
3.1 Plan-and-Solve 的工作原理   
  <img width="1480" height="704" alt="image" src="https://github.com/user-attachments/assets/75e4088c-f915-417c-b2da-a89ed48a4423" />
3.2 规划阶段
3.3 执行器与状态管理
3.4 运行实例与分析
   <img width="1896" height="1888" alt="image" src="https://github.com/user-attachments/assets/d011983d-84f8-49f7-8d24-0d90d1b53a59" />
4. Reflection



