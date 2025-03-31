# 基础信息

|      |      |
|------|------|
| 名称 | example |
| 编码语言 | .java |
| 代码路径 | openai-java/openai-java-example/src/main/java/com/openai/example |
| 包名 | openai-java.openai-java-example.src.main.java.com.openai.example |
| 概述说明 | Java示例展示如何集成OpenAI API，涵盖数学助手、对话生成、内容审核、流式处理、异步调用等功能，实现高效自动化任务处理。 |

# 说明

## 概述
该代码模块是一个基于Java的OpenAI API集成示例集合，展示了如何通过Java代码与OpenAI服务进行交互，实现多种功能，包括文本生成、对话管理、内容审核、音频转录、图像处理等。模块中的每个示例都展示了不同的OpenAI API功能，并通过异步、流式处理等技术优化了性能和用户体验。该模块旨在为开发者提供清晰的参考，帮助他们快速集成OpenAI的强大功能到Java应用程序中。

## 主要业务场景
1. **数学问题解决**：通过创建专门的OpenAI助手，接收并解析数学问题，调用算法或模型进行计算，最终返回结果并清理资源。
2. **对话生成与管理**：实现多轮对话生成，支持连续对话和流式响应，适用于聊天机器人、客服系统等场景。
3. **内容审核**：调用OpenAI的内容审核功能，检测文本中的不当内容，确保平台内容的安全性和合规性。
4. **音频转录**：将音频文件转换为文本，适用于语音助手、会议记录等场景。
5. **图像处理与描述生成**：加载并编码图片，通过GPT-4生成与图片相关的描述或分析。
6. **文本生成与补全**：生成故事、文本补全，支持流式生成和异步处理，适用于内容创作和自动化文本生成。
7. **异步与流式处理**：通过异步调用和流式处理技术，优化大规模数据处理和实时响应场景，如智能客服、实时聊天系统等。
8. **身份认证与安全**：通过Azure Entra ID进行身份认证，确保与OpenAI API的交互安全可靠。
9. **模型管理与配置**：通过环境变量配置OpenAI客户端，灵活管理API密钥和模型列表，确保系统的高效性和可维护性。

该模块涵盖了多种OpenAI API的应用场景，适合需要集成自然语言处理、图像处理、音频处理等功能的Java应用程序开发者。


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

该流程图展示了`example`目录下的所有Java文件及其层级关系。每个节点代表一个Java文件，根节点为`example`，所有文件都直接挂载在`example`下，没有进一步的子目录结构。这些文件涵盖了OpenAI Java示例项目的各种功能模块，如助手、模型列表、响应流、审核、音频转录等。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [CompletionsExample.java](CompletionsExample.md) | file | Java代码通过OpenAI客户端生成聊天故事内容。 |
| [CompletionsStreamingCancellationAsyncExample.java](CompletionsStreamingCancellationAsyncExample.md) | file | Java示例演示OpenAI API流式响应及提前关闭功能。 |
| [AssistantAsyncExample.java](AssistantAsyncExample.md) | file | Java示例：创建数学助手，处理线程消息，轮询状态，删除助手。 |
| [ModerationsAsyncExample.java](ModerationsAsyncExample.md) | file | Java示例展示如何使用OpenAI异步客户端进行内容审核。 |
| [CompletionsStreamingCancellationExample.java](CompletionsStreamingCancellationExample.md) | file | Java示例：OpenAI客户端流式处理聊天，支持条件提前关闭。 |
| [ResponsesStreamingExample.java](ResponsesStreamingExample.md) | file | Java代码通过OpenAI API流式生成响应并输出文本。 |
| [ModerationsExample.java](ModerationsExample.md) | file | Java示例展示如何利用OpenAI API进行内容审核。 |
| [FunctionCallingAsyncExample.java](FunctionCallingAsyncExample.md) | file | Java异步调用OpenAI API，评估SDK质量并分析原因。 |
| [StructuredOutputsAsyncExample.java](StructuredOutputsAsyncExample.md) | file | Java示例：异步调用OpenAI客户端，配置JSON模式，查询员工信息并输出结果。 |
| [Main.java](Main.md) | file | Main类执行Completions、CompletionsStreaming和AudioTranscriptions示例。 |
| [AzureEntraIdExample.java](AzureEntraIdExample.md) | file | AzureEntraIdExample类通过Azure Entra ID认证调用OpenAI API生成聊天回复。 |
| [CompletionsConversationExample.java](CompletionsConversationExample.md) | file | Java示例：使用OpenAI客户端循环生成并打印聊天回复。 |
| [ModelListAsyncExample.java](ModelListAsyncExample.md) | file | Java异步获取OpenAI模型并输出ID。 |
| [EmbeddingsExample.java](EmbeddingsExample.md) | file | Java示例：利用OpenAI API生成文本嵌入，支持环境变量配置。 |
| [AudioTranscriptionsAsyncExample.java](AudioTranscriptionsAsyncExample.md) | file | 使用OpenAI客户端将音频文件异步转录为文本。 |
| [ResponsesAsyncExample.java](ResponsesAsyncExample.md) | file | Java异步调用OpenAI API生成故事并输出。 |
| [CompletionsStreamingAsyncExample.java](CompletionsStreamingAsyncExample.md) | file | 异步流式生成GPT-3.5-Turbo对话，通过环境变量配置客户端。 |
| [EmbeddingsAsyncExample.java](EmbeddingsAsyncExample.md) | file | 配置OpenAI客户端，生成文本嵌入并输出结果。 |
| [CompletionsConversationAsyncExample.java](CompletionsConversationAsyncExample.md) | file | Java代码示例，通过OpenAI API实现异步对话生成，支持多轮交互。 |
| [CompletionsAsyncExample.java](CompletionsAsyncExample.md) | file | 异步调用OpenAI API生成聊天，配置客户端，请求GPT-3.5，输出至控制台。 |
| [FunctionCallingExample.java](FunctionCallingExample.md) | file | Java示例代码演示调用OpenAI API、配置客户端、定义函数及处理对话和工具调用。 |
| [AudioTranscriptionsExample.java](AudioTranscriptionsExample.md) | file | Java示例：利用OpenAI API实现音频转文本。 |
| [CompletionsImageUrlExample.java](CompletionsImageUrlExample.md) | file | Java代码调用OpenAI API，处理图片并获取GPT-4响应。 |
| [StructuredOutputsExample.java](StructuredOutputsExample.md) | file | Java代码示例：配置OpenAI环境变量，构建JSON，发送聊天请求并输出结果。 |
| [ResponsesExample.java](ResponsesExample.md) | file | Java代码通过环境变量配置OpenAI客户端，生成故事并输出结果。 |
| [ResponsesStreamingAsyncExample.java](ResponsesStreamingAsyncExample.md) | file | Java代码示例：异步流式生成GPT-4故事。 |
| [CompletionsStreamingExample.java](CompletionsStreamingExample.md) | file | Java示例演示如何通过OpenAI客户端流式生成GPT-3.5对话。 |
| [ResponsesConversationExample.java](ResponsesConversationExample.md) | file | Java代码示例：利用OpenAI客户端生成对话响应并进行循环迭代。 |
| [ModelListExample.java](ModelListExample.md) | file | Java代码通过环境变量配置OpenAI客户端并列出模型ID。 |
| [AssistantExample.java](AssistantExample.md) | file | Java代码实现OpenAI助手解决数学问题后删除。 |


