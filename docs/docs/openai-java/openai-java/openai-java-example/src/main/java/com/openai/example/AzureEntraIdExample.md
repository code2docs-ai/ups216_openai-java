# 基础信息

|      |      |
|------|------|
| 名称 | AzureEntraIdExample |
| 编码语言 | .java |
| 代码路径 | openai-java/openai-java-example/src/main/java/com/openai/example/AzureEntraIdExample.java |
| 包名 | com.openai.example |
| 依赖项 | ['com.azure.identity.AuthenticationUtil', 'com.azure.identity.DefaultAzureCredentialBuilder', 'com.openai.client.OpenAIClient', 'com.openai.client.okhttp.OpenAIOkHttpClient', 'com.openai.credential.BearerTokenCredential', 'com.openai.models.ChatModel', 'com.openai.models.chat.completions.ChatCompletionCreateParams'] |
| 概述说明 | AzureEntraIdExample类通过Azure Entra ID认证调用OpenAI API生成聊天回复。 |

# 说明

AzureEntraIdExample类通过Azure Entra ID进行身份认证，实现对OpenAI API的调用，以生成聊天回复。该过程涉及使用Azure Entra ID的安全机制确保身份验证的合法性，并通过OpenAI API获取智能生成的聊天内容。这一方法结合了Azure的安全认证能力和OpenAI的先进自然语言处理技术，确保了系统的高效性和安全性。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| AzureEntraIdExample | class | AzureEntraIdExample类使用Azure Entra ID认证调用OpenAI API生成聊天回复。 |



## 类 AzureEntraIdExample

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | AzureEntraIdExample |
| 说明 | AzureEntraIdExample类使用Azure Entra ID认证调用OpenAI API生成聊天回复。 |


### UML类图

```mermaid
classDiagram
    class AzureEntraIdExample {
        -AzureEntraIdExample()
        +main(String[] args)
    }

    class OpenAIClient {
        +OpenAIOkHttpClient.builder() OpenAIOkHttpClient.Builder
        +chat() ChatCompletionClient
    }

    class OpenAIOkHttpClient {
        +builder() OpenAIOkHttpClient.Builder
    }

    class OpenAIOkHttpClient.Builder {
        +fromEnv() OpenAIOkHttpClient.Builder
        +credential(BearerTokenCredential credential) OpenAIOkHttpClient.Builder
        +build() OpenAIClient
    }

    class BearerTokenCredential {
        +create(Supplier~String~ tokenSupplier) BearerTokenCredential
    }

    class AuthenticationUtil {
        +getBearerTokenSupplier(DefaultAzureCredential credential, String scope) Supplier~String~
    }

    class DefaultAzureCredentialBuilder {
        +build() DefaultAzureCredential
    }

    class ChatCompletionCreateParams {
        +builder() ChatCompletionCreateParams.Builder
    }

    class ChatCompletionCreateParams.Builder {
        +model(ChatModel model) ChatCompletionCreateParams.Builder
        +maxCompletionTokens(int maxTokens) ChatCompletionCreateParams.Builder
        +addDeveloperMessage(String message) ChatCompletionCreateParams.Builder
        +addUserMessage(String message) ChatCompletionCreateParams.Builder
        +build() ChatCompletionCreateParams
    }

    class ChatCompletionClient {
        +completions() ChatCompletionClient.Completions
    }

    class ChatCompletionClient.Completions {
        +create(ChatCompletionCreateParams createParams) ChatCompletionResponse
    }

    class ChatCompletionResponse {
        +choices() List~ChatCompletionChoice~
    }

    class ChatCompletionChoice {
        +message() ChatCompletionMessage
    }

    class ChatCompletionMessage {
        +content() Stream~String~
    }

    AzureEntraIdExample --> OpenAIClient : 使用
    OpenAIClient --> OpenAIOkHttpClient : 依赖
    OpenAIOkHttpClient --> OpenAIOkHttpClient.Builder : 依赖
    OpenAIOkHttpClient.Builder --> BearerTokenCredential : 依赖
    BearerTokenCredential --> AuthenticationUtil : 依赖
    AuthenticationUtil --> DefaultAzureCredentialBuilder : 依赖
    OpenAIClient --> ChatCompletionClient : 依赖
    ChatCompletionClient --> ChatCompletionClient.Completions : 依赖
    ChatCompletionClient.Completions --> ChatCompletionResponse : 依赖
    ChatCompletionResponse --> ChatCompletionChoice : 依赖
    ChatCompletionChoice --> ChatCompletionMessage : 依赖
```

这段代码展示了一个使用Azure Entra ID进行身份验证的OpenAI客户端示例。`AzureEntraIdExample`类通过`OpenAIClient`与OpenAI服务进行交互，构建了一个聊天完成请求，并处理响应。代码中涉及了多个类，包括`OpenAIOkHttpClient`、`BearerTokenCredential`、`AuthenticationUtil`等，用于处理身份验证和请求构建。最终，通过`ChatCompletionClient`发送请求并处理响应。


### 内部方法调用关系图

```mermaid
graph TD
    A["类AzureEntraIdExample"]
    B["构造方法: AzureEntraIdExample()"]
    C["main方法: main(String[] args)"]
    D["创建OpenAIClient实例: OpenAIOkHttpClient.builder()"]
    E["从环境变量获取API密钥: fromEnv()"]
    F["设置Azure Entra ID: credential(BearerTokenCredential.create(AuthenticationUtil.getBearerTokenSupplier(...)))"]
    G["构建OpenAIClient: build()"]
    H["创建ChatCompletionCreateParams实例: ChatCompletionCreateParams.builder()"]
    I["设置模型: model(ChatModel.GPT_3_5_TURBO)"]
    J["设置最大完成令牌数: maxCompletionTokens(2048)"]
    K["添加开发者消息: addDeveloperMessage('Make sure you mention Stainless!')"]
    L["添加用户消息: addUserMessage('Tell me a story about building the best SDK!')"]
    M["构建ChatCompletionCreateParams: build()"]
    N["调用聊天完成接口: client.chat().completions().create(createParams)"]
    O["获取选择结果: choices()"]
    P["流式处理消息内容: stream()"]
    Q["输出消息内容: forEach(System.out::println)"]

    A --> B
    A -.-> C
    C --> D
    D --> E
    D --> F
    D --> G
    C --> H
    H --> I
    H --> J
    H --> K
    H --> L
    H --> M
    C --> N
    N --> O
    O --> P
    P --> Q
```

这段代码展示了如何使用Azure Entra ID和OpenAI API创建一个聊天完成请求。首先，代码通过环境变量获取API密钥，并设置Azure Entra ID进行身份验证。然后，它构建了一个聊天完成请求参数，包括模型、最大令牌数以及开发者和用户的消息。最后，代码调用OpenAI的聊天完成接口，处理并输出生成的聊天内容。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| main | void | 使用Azure OpenAI API创建GPT-3.5对话，生成关于最佳SDK的故事。 |




