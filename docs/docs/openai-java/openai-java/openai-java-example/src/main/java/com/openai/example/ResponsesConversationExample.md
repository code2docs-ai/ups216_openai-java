# 基础信息

|      |      |
|------|------|
| 名称 | ResponsesConversationExample |
| 编码语言 | .java |
| 代码路径 | openai-java/openai-java-example/src/main/java/com/openai/example/ResponsesConversationExample.java |
| 包名 | com.openai.example |
| 依赖项 | ['com.openai.client.OpenAIClient', 'com.openai.client.okhttp.OpenAIOkHttpClient', 'com.openai.models.ChatModel', 'com.openai.models.responses.EasyInputMessage', 'com.openai.models.responses.ResponseCreateParams', 'com.openai.models.responses.ResponseInputItem', 'com.openai.models.responses.ResponseOutputMessage', 'java.util.ArrayList', 'java.util.List', 'java.util.stream.Collectors.toList'] |
| 概述说明 | Java代码示例：利用OpenAI客户端生成对话响应并进行循环迭代。 |

# 说明

该Java示例代码展示了如何使用OpenAI客户端生成对话响应，并通过循环迭代实现连续对话。代码首先初始化OpenAI客户端，设置必要的参数，如API密钥和模型类型。然后，通过循环结构不断接收用户输入，调用OpenAI的API生成响应，并将响应输出给用户。这一过程可以持续进行，直到用户主动终止对话。整个流程展示了如何将OpenAI的对话生成能力集成到Java应用程序中，实现智能对话功能。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| ResponsesConversationExample | class | Java示例代码，使用OpenAI客户端生成对话响应并循环迭代。 |



## 类 ResponsesConversationExample

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | ResponsesConversationExample |
| 说明 | Java示例代码，使用OpenAI客户端生成对话响应并循环迭代。 |


### UML类图

```mermaid
classDiagram
    class ResponsesConversationExample {
        +main(String[] args)
    }

    class OpenAIClient {
        +responses() : ResponseService
    }

    class ResponseService {
        +create(ResponseCreateParams params) : ResponseResult
    }

    class ResponseResult {
        +output() : List<ResponseOutputItem>
    }

    class ResponseOutputItem {
        +message() : List<ResponseOutputMessage>
    }

    class ResponseOutputMessage {
        +content() : List<ResponseContent>
    }

    class ResponseContent {
        +outputText() : List<OutputText>
    }

    class OutputText {
        +text() : String
    }

    class ResponseCreateParams {
        +builder() : Builder
        +toBuilder() : Builder
    }

    class Builder {
        +inputOfResponse(List<ResponseInputItem> inputItems) : Builder
        +model(ChatModel model) : Builder
        +build() : ResponseCreateParams
    }

    class ResponseInputItem {
        +ofEasyInputMessage(EasyInputMessage message) : ResponseInputItem
        +ofResponseOutputMessage(ResponseOutputMessage message) : ResponseInputItem
    }

    class EasyInputMessage {
        +builder() : Builder
    }

    class EasyInputMessage.Builder {
        +role(EasyInputMessage.Role role) : Builder
        +content(String content) : Builder
        +build() : EasyInputMessage
    }

    ResponsesConversationExample --> OpenAIClient : 依赖
    OpenAIClient --> ResponseService : 依赖
    ResponseService --> ResponseResult : 依赖
    ResponseResult --> ResponseOutputItem : 依赖
    ResponseOutputItem --> ResponseOutputMessage : 依赖
    ResponseOutputMessage --> ResponseContent : 依赖
    ResponseContent --> OutputText : 依赖
    ResponseCreateParams --> Builder : 依赖
    ResponseInputItem --> EasyInputMessage : 依赖
    EasyInputMessage --> EasyInputMessage.Builder : 依赖
```

这段代码展示了一个与OpenAI API进行对话的示例。`ResponsesConversationExample`类通过`OpenAIClient`与API交互，生成对话内容并输出。代码通过构建`ResponseCreateParams`对象来配置请求参数，并通过循环不断更新对话内容。类图清晰地展示了各个类之间的依赖关系，以及如何通过构建器模式创建和更新请求参数。


### 内部方法调用关系图

```mermaid
graph TD
    A["类ResponsesConversationExample"]
    B["构造方法: ResponsesConversationExample()"]
    C["main方法: main(String[] args)"]
    D["创建OpenAIClient: OpenAIOkHttpClient.fromEnv()"]
    E["创建List<ResponseInputItem>: new ArrayList<>()"]
    F["添加ResponseInputItem: inputItems.add(ResponseInputItem.ofEasyInputMessage(EasyInputMessage.builder().role(EasyInputMessage.Role.USER).content('Tell me a story about building the best SDK!').build()))"]
    G["创建ResponseCreateParams: ResponseCreateParams.builder().inputOfResponse(inputItems).model(ChatModel.GPT_4O).build()"]
    H["循环4次: for (int i = 0; i < 4; i++)"]
    I["获取ResponseOutputMessage: client.responses().create(createParams).output().stream().flatMap(item -> item.message().stream()).collect(toList())"]
    J["输出消息内容: messages.stream().flatMap(message -> message.content().stream()).flatMap(content -> content.outputText().stream()).forEach(outputText -> System.out.println(outputText.text()))"]
    K["输出分隔符: System.out.println('\\n-----------------------------------\\n')"]
    L["添加ResponseInputItem: messages.forEach(message -> inputItems.add(ResponseInputItem.ofResponseOutputMessage(message)))"]
    M["添加EasyInputMessage: inputItems.add(ResponseInputItem.ofEasyInputMessage(EasyInputMessage.builder().role(EasyInputMessage.Role.USER).content('But why?' + '?'.repeat(i)).build()))"]
    N["更新ResponseCreateParams: createParams = createParams.toBuilder().inputOfResponse(inputItems).build()"]

    A --> B
    A -.-> C
    C --> D
    C --> E
    E --> F
    F --> G
    G --> H
    H --> I
    I --> J
    J --> K
    K --> L
    L --> M
    M --> N
    N --> H
```

这段代码展示了一个对话生成的过程，通过循环4次，每次生成对话内容并输出，然后将生成的对话内容添加到输入列表中，以便在下一次循环中使用。代码通过OpenAI客户端生成对话，并在每次循环后更新对话参数，以模拟多轮对话的场景。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| main | void | Java代码通过环境变量配置OpenAI客户端，使用GPT-4模型生成并输出对话响应。 |




