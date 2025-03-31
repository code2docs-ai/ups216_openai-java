# 基础信息

|      |      |
|------|------|
| 名称 | FunctionCallingExample |
| 编码语言 | .java |
| 代码路径 | openai-java/openai-java-example/src/main/java/com/openai/example/FunctionCallingExample.java |
| 包名 | com.openai.example |
| 依赖项 | ['com.openai.core.ObjectMappers.jsonMapper', 'com.fasterxml.jackson.core.JsonProcessingException', 'com.openai.client.OpenAIClient', 'com.openai.client.okhttp.OpenAIOkHttpClient', 'com.openai.core.JsonObject', 'com.openai.core.JsonValue', 'com.openai.models.ChatModel', 'com.openai.models.FunctionDefinition', 'com.openai.models.FunctionParameters', 'com.openai.models.chat.completions', 'java.util.Collection', 'java.util.List', 'java.util.Map'] |
| 概述说明 | Java示例代码演示调用OpenAI API、配置客户端、定义函数及处理对话和工具调用。 |

# 说明

该内容展示了如何使用Java调用OpenAI API，包括配置客户端、定义函数、处理对话和工具调用。通过详细的步骤，用户能够了解如何设置API客户端，编写必要的函数来与OpenAI服务进行交互，以及如何处理对话和工具调用的响应。整个过程涵盖了从初始化客户端到实际调用的完整流程，确保用户能够顺利集成OpenAI API到Java应用程序中。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| FunctionCallingExample | class | Java示例代码展示如何调用OpenAI API，配置客户端，定义函数，处理对话和工具调用。 |



## 类 FunctionCallingExample

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | FunctionCallingExample |
| 说明 | Java示例代码展示如何调用OpenAI API，配置客户端，定义函数，处理对话和工具调用。 |


### UML类图

```mermaid
classDiagram
    class FunctionCallingExample {
        -FunctionCallingExample()
        +main(String[] args)
        -callFunction(ChatCompletionMessageToolCall~Function~ function) String
    }

    class OpenAIClient {
        +chat() ChatCompletionClient
    }

    class ChatCompletionClient {
        +completions() ChatCompletionClientCompletions
    }

    class ChatCompletionClientCompletions {
        +create(ChatCompletionCreateParams params) ChatCompletion
    }

    class ChatCompletion {
        +choices() List~ChatCompletion~Choice~
    }

    class ChatCompletion~Choice~ {
        +message() ChatCompletionMessage
    }

    class ChatCompletionMessage {
        +content() Optional~String~
        +toolCalls() List~ChatCompletionMessageToolCall~
    }

    class ChatCompletionMessageToolCall {
        +function() ChatCompletionMessageToolCall~Function~
        +id() String
    }

    class ChatCompletionMessageToolCall~Function~ {
        +name() String
        +arguments() String
    }

    class ChatCompletionCreateParams {
        +builder() ChatCompletionCreateParams~Builder~
    }

    class ChatCompletionCreateParams~Builder~ {
        +model(ChatModel model) ChatCompletionCreateParams~Builder~
        +maxCompletionTokens(int tokens) ChatCompletionCreateParams~Builder~
        +addTool(ChatCompletionTool tool) ChatCompletionCreateParams~Builder~
        +addUserMessage(String message) ChatCompletionCreateParams~Builder~
        +addMessage(ChatCompletionMessage message) ChatCompletionCreateParams~Builder~
        +build() ChatCompletionCreateParams
    }

    class ChatCompletionTool {
        +builder() ChatCompletionTool~Builder~
    }

    class ChatCompletionTool~Builder~ {
        +function(FunctionDefinition function) ChatCompletionTool~Builder~
        +build() ChatCompletionTool
    }

    class FunctionDefinition {
        +builder() FunctionDefinition~Builder~
    }

    class FunctionDefinition~Builder~ {
        +name(String name) FunctionDefinition~Builder~
        +description(String description) FunctionDefinition~Builder~
        +parameters(FunctionParameters parameters) FunctionDefinition~Builder~
        +build() FunctionDefinition
    }

    class FunctionParameters {
        +builder() FunctionParameters~Builder~
    }

    class FunctionParameters~Builder~ {
        +putAdditionalProperty(String key, JsonValue value) FunctionParameters~Builder~
        +build() FunctionParameters
    }

    class JsonValue {
        <<Interface>>
    }

    class JsonObject {
        +values() Map~String, JsonValue~
        +asStringOrThrow() String
    }

    class ChatCompletionToolMessageParam {
        +builder() ChatCompletionToolMessageParam~Builder~
    }

    class ChatCompletionToolMessageParam~Builder~ {
        +toolCallId(String id) ChatCompletionToolMessageParam~Builder~
        +content(String content) ChatCompletionToolMessageParam~Builder~
        +build() ChatCompletionToolMessageParam
    }

    FunctionCallingExample --> OpenAIClient : 依赖
    OpenAIClient --> ChatCompletionClient : 依赖
    ChatCompletionClient --> ChatCompletionClientCompletions : 依赖
    ChatCompletionClientCompletions --> ChatCompletion : 依赖
    ChatCompletion --> ChatCompletion~Choice~ : 依赖
    ChatCompletion~Choice~ --> ChatCompletionMessage : 依赖
    ChatCompletionMessage --> ChatCompletionMessageToolCall : 依赖
    ChatCompletionMessageToolCall --> ChatCompletionMessageToolCall~Function~ : 依赖
    FunctionCallingExample --> ChatCompletionCreateParams : 依赖
    ChatCompletionCreateParams --> ChatCompletionCreateParams~Builder~ : 依赖
    ChatCompletionCreateParams~Builder~ --> ChatCompletionTool : 依赖
    ChatCompletionTool --> ChatCompletionTool~Builder~ : 依赖
    ChatCompletionTool~Builder~ --> FunctionDefinition : 依赖
    FunctionDefinition --> FunctionDefinition~Builder~ : 依赖
    FunctionDefinition~Builder~ --> FunctionParameters : 依赖
    FunctionParameters --> FunctionParameters~Builder~ : 依赖
    FunctionParameters~Builder~ --> JsonValue : 依赖
    JsonValue --> JsonObject : 依赖
    FunctionCallingExample --> ChatCompletionToolMessageParam : 依赖
    ChatCompletionToolMessageParam --> ChatCompletionToolMessageParam~Builder~ : 依赖
```

**描述**：该代码展示了如何使用OpenAI的Java SDK进行函数调用。`FunctionCallingExample`类通过`OpenAIClient`与OpenAI的API进行交互，构建聊天完成请求，并处理返回的消息。代码中使用了多个构建器模式来创建复杂的参数对象，并通过函数调用获取SDK的质量评估。类图展示了各个类之间的依赖关系，包括客户端、消息、工具调用等组件的交互。


### 内部方法调用关系图

```mermaid
graph TD
    A["类FunctionCallingExample"]
    B["构造方法: FunctionCallingExample()"]
    C["main方法: main(String[] args)"]
    D["创建OpenAIClient: OpenAIOkHttpClient.fromEnv()"]
    E["构建ChatCompletionCreateParams.Builder: ChatCompletionCreateParams.builder()"]
    F["设置模型: .model(ChatModel.GPT_3_5_TURBO)"]
    G["设置最大token数: .maxCompletionTokens(2048)"]
    H["添加工具: .addTool(ChatCompletionTool.builder())"]
    I["定义函数: FunctionDefinition.builder()"]
    J["设置函数名: .name('get-sdk-quality')"]
    K["设置函数描述: .description('Gets the quality of the given SDK.')"]
    L["设置函数参数: FunctionParameters.builder()"]
    M["添加用户消息: .addUserMessage('How good are the following SDKs: OpenAI Java SDK, Unknown Company SDK')"]
    N["创建聊天完成: client.chat().completions().create(createParamsBuilder.build())"]
    O["处理选择: .choices().stream()"]
    P["映射消息: .map(ChatCompletion.Choice::message)"]
    Q["添加助手消息: .peek(createParamsBuilder::addMessage)"]
    R["输出消息内容: .flatMap(message -> message.content().ifPresent(System.out::println))"]
    S["处理工具调用: .flatMap(message -> message.toolCalls().stream().flatMap(Collection::stream))"]
    T["调用函数: .forEach(toolCall -> callFunction(toolCall.function()))"]
    U["添加工具调用结果: createParamsBuilder.addMessage(ChatCompletionToolMessageParam.builder())"]
    V["输出工具调用结果: System.out.println(content)"]
    W["添加后续问题: createParamsBuilder.addUserMessage('Why do you say that?')"]
    X["创建后续聊天完成: client.chat().completions().create(createParamsBuilder.build())"]
    Y["输出后续消息内容: .flatMap(choice -> choice.message().content().stream()).forEach(System.out::println)"]
    Z["callFunction方法: callFunction(ChatCompletionMessageToolCall.Function function)"]
    AA["验证函数名: if (!function.name().equals('get-sdk-quality'))"]
    AB["解析函数参数: JsonValue.from(jsonMapper().readTree(function.arguments()))"]
    AC["获取SDK名称: String sdkName = ((JsonObject) arguments).values().get('name').asStringOrThrow()"]
    AD["判断SDK名称: if (sdkName.contains('OpenAI'))"]
    AE["返回结果: return sdkName + ': It's robust and polished!'"]
    AF["返回默认结果: return sdkName + ': *shrug*'"]

    A --> B
    A -.-> C
    C --> D
    C --> E
    E --> F
    E --> G
    E --> H
    H --> I
    I --> J
    I --> K
    I --> L
    E --> M
    C --> N
    N --> O
    O --> P
    P --> Q
    P --> R
    P --> S
    S --> T
    T --> U
    U --> V
    C --> W
    W --> X
    X --> Y
    C -.-> Z
    Z --> AA
    Z --> AB
    AB --> AC
    AC --> AD
    AD --> AE
    AD --> AF
```

这段代码展示了一个使用OpenAI API进行对话和函数调用的示例。首先，代码通过环境变量配置OpenAIClient，然后构建了一个包含模型、最大token数和自定义函数的聊天请求。接着，代码处理聊天完成的结果，调用自定义函数并输出结果。最后，代码添加了一个后续问题并输出结果。整个过程展示了如何使用OpenAI API进行复杂的对话和函数调用。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| callFunction | String | 调用函数检查SDK质量，若为OpenAI则返回优质评价，否则返回不确定。 |
| main | void | Java代码配置OpenAI客户端，构建聊天参数，调用函数并输出结果。 |




