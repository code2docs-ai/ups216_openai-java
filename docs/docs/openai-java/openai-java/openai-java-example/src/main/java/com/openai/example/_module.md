# 基础信息

|      |      |
|------|------|
| 名称 | example |
| 编码语言 | .java |
| 代码路径 | openai-java/openai-java-example/src/main/java/com/openai/example |
| 包名 | openai-java.openai-java-example.src.main.java.com.openai.example |
| 概述说明 | Java示例展示如何通过OpenAI API实现数学求解、对话生成、内容审核及音频转录等功能，涵盖创建、监控、输出和清理等步骤。 |

# 说明

## 概述
该代码模块是一个基于Java的OpenAI API集成示例集合，展示了如何通过Java编程语言与OpenAI的各种功能进行交互。模块涵盖了从配置客户端、调用API、处理响应到资源管理的完整流程。示例代码包括同步和异步操作，支持多种OpenAI功能，如文本生成、对话生成、内容审核、音频转录、数学求解、文本嵌入等。通过环境变量配置，模块确保了敏感信息的安全性和灵活性，适用于不同应用场景的开发和测试。

## 主要业务场景
1. **文本生成与对话**：通过GPT-3.5和GPT-4模型生成文本、故事和对话内容，支持流式处理和异步调用，适用于聊天机器人、内容创作工具等场景。
2. **内容审核**：调用OpenAI的内容审核接口，对文本内容进行审核，适用于社交媒体、在线论坛等需要实时或近实时审核的场景。
3. **音频转录**：将音频文件转换为文本，适用于语音识别、会议记录等场景。
4. **数学求解**：创建数学助手，求解方程问题，适用于教育、科研等需要数学计算的场景。
5. **文本嵌入**：生成文本的数值向量表示，适用于自然语言处理任务，如语义分析、文本相似度计算等。
6. **自定义函数调用**：通过OpenAI API调用自定义函数，评估SDK质量，适用于开发过程中的性能评估和问题分析。
7. **多模态交互**：整合图片和文本，调用OpenAI API实现多模态交互，适用于需要处理多种数据类型的应用场景。
8. **身份认证**：通过Azure Entra ID进行身份认证，确保安全访问OpenAI API，适用于需要高安全性的应用场景。

该模块通过丰富的示例代码，展示了如何高效、安全地集成OpenAI API到Java应用程序中，适用于多种实际应用场景。


### 包内部结构视图

```mermaid
graph TD
    example --> AssistantExample.java
    example --> ModelListExample.java
    example --> ResponsesConversationExample.java
    example --> ModerationsExample.java
    example --> CompletionsStreamingExample.java
    example --> ResponsesStreamingAsyncExample.java
    example --> ResponsesExample.java
    example --> ResponsesStreamingExample.java
    example --> StructuredOutputsExample.java
    example --> CompletionsImageUrlExample.java
    example --> AudioTranscriptionsExample.java
    example --> CompletionsStreamingCancellationExample.java
    example --> FunctionCallingExample.java
    example --> CompletionsAsyncExample.java
    example --> ModerationsAsyncExample.java
    example --> CompletionsConversationAsyncExample.java
    example --> EmbeddingsAsyncExample.java
    example --> CompletionsStreamingAsyncExample.java
    example --> ResponsesAsyncExample.java
    example --> AssistantAsyncExample.java
    example --> AudioTranscriptionsAsyncExample.java
    example --> CompletionsStreamingCancellationAsyncExample.java
    example --> EmbeddingsExample.java
    example --> ModelListAsyncExample.java
    example --> CompletionsConversationExample.java
    example --> CompletionsExample.java
    example --> AzureEntraIdExample.java
    example --> Main.java
    example --> StructuredOutputsAsyncExample.java
    example --> FunctionCallingAsyncExample.java
```

该流程图展示了`example`目录下的所有Java文件及其层级关系。每个文件都直接隶属于`example`目录，没有进一步的子目录结构。这些文件涵盖了多种功能示例，如助手、模型列表、响应、审核、完成、音频转录、嵌入等，展示了不同功能的实现方式。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [EmbeddingsExample.java](EmbeddingsExample.md) | file | Java示例：通过环境变量配置OpenAI客户端，生成并输出文本嵌入。 |
| [CompletionsStreamingCancellationAsyncExample.java](CompletionsStreamingCancellationAsyncExample.md) | file | Java示例展示如何异步取消OpenAI聊天请求。 |
| [AudioTranscriptionsAsyncExample.java](AudioTranscriptionsAsyncExample.md) | file | 使用OpenAI客户端异步转录WAV文件为文本。 |
| [AssistantAsyncExample.java](AssistantAsyncExample.md) | file | 异步API创建数学助手，解答方程后删除。 |
| [EmbeddingsAsyncExample.java](EmbeddingsAsyncExample.md) | file | 异步调用OpenAI嵌入模型生成文本嵌入。 |
| [CompletionsAsyncExample.java](CompletionsAsyncExample.md) | file | 异步调用OpenAI API生成聊天完成，通过环境变量配置客户端。 |
| [AudioTranscriptionsExample.java](AudioTranscriptionsExample.md) | file | Java示例：使用OpenAI API将音频转录为文本。 |
| [ResponsesStreamingExample.java](ResponsesStreamingExample.md) | file | Java代码通过OpenAI API流式生成GPT-4响应并输出结果。 |
| [ModerationsExample.java](ModerationsExample.md) | file | Java示例：配置OpenAI API密钥并调用内容审核接口。 |
| [AssistantExample.java](AssistantExample.md) | file | Java代码创建数学助手，求解方程，轮询状态输出结果后删除。 |
| [CompletionsExample.java](CompletionsExample.md) | file | Java示例：用OpenAI客户端生成故事，环境变量配置，输出内容。 |
| [FunctionCallingAsyncExample.java](FunctionCallingAsyncExample.md) | file | Java异步调用OpenAI SDK，评估质量并跟进原因。 |
| [StructuredOutputsAsyncExample.java](StructuredOutputsAsyncExample.md) | file | 配置OpenAI客户端，定义JSON模式，发送异步聊天请求并输出结果。 |
| [Main.java](Main.md) | file | Java主类调用多个示例程序实现功能。 |
| [AzureEntraIdExample.java](AzureEntraIdExample.md) | file | Java代码通过Azure Entra ID认证调用OpenAI API生成GPT-3.5对话。 |
| [CompletionsConversationExample.java](CompletionsConversationExample.md) | file | Java代码利用OpenAI API生成对话，支持环境变量配置，循环输出四次对话内容。 |
| [ModelListAsyncExample.java](ModelListAsyncExample.md) | file | Java示例代码异步列出OpenAI模型并打印ID。 |
| [ResponsesAsyncExample.java](ResponsesAsyncExample.md) | file | Java异步调用OpenAI API生成故事并输出结果。 |
| [CompletionsStreamingAsyncExample.java](CompletionsStreamingAsyncExample.md) | file | Java代码示例演示OpenAI API流式生成聊天内容。 |
| [CompletionsConversationAsyncExample.java](CompletionsConversationAsyncExample.md) | file | Java示例展示异步对话生成，配置GPT-3.5模型并循环生成回复。 |
| [ModerationsAsyncExample.java](ModerationsAsyncExample.md) | file | Java示例：利用OpenAI异步客户端实现内容审核。 |
| [FunctionCallingExample.java](FunctionCallingExample.md) | file | Java示例演示通过OpenAI API调用自定义函数评估SDK质量。 |
| [CompletionsStreamingCancellationExample.java](CompletionsStreamingCancellationExample.md) | file | Java示例通过OpenAI流式API生成聊天内容，支持关键词检测并提前终止流。 |
| [CompletionsImageUrlExample.java](CompletionsImageUrlExample.md) | file | Java代码通过OpenAI API发送图文聊天请求。 |
| [StructuredOutputsExample.java](StructuredOutputsExample.md) | file | Java配置OpenAI客户端，定义JSON模式，创建聊天参数并获取响应。 |
| [ResponsesExample.java](ResponsesExample.md) | file | Java代码通过环境变量配置OpenAI客户端，使用GPT-4生成故事并输出。 |
| [ResponsesStreamingAsyncExample.java](ResponsesStreamingAsyncExample.md) | file | 配置环境变量调用OpenAI API，使用GPT-4模型生成异步流式故事。 |
| [CompletionsStreamingExample.java](CompletionsStreamingExample.md) | file | Java示例：通过OpenAI API流式生成GPT-3.5聊天补全。 |
| [ResponsesConversationExample.java](ResponsesConversationExample.md) | file | Java示例：四次循环生成对话，输出并追加用户问题。 |
| [ModelListExample.java](ModelListExample.md) | file | Java代码示例：通过环境变量配置OpenAI客户端并获取模型ID。 |


