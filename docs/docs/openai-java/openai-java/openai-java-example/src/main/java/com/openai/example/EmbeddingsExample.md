# 基础信息

|      |      |
|------|------|
| 名称 | EmbeddingsExample |
| 编码语言 | .java |
| 代码路径 | openai-java/openai-java-example/src/main/java/com/openai/example/EmbeddingsExample.java |
| 包名 | com.openai.example |
| 依赖项 | ['com.openai.client.OpenAIClient', 'com.openai.client.okhttp.OpenAIOkHttpClient', 'com.openai.models.embeddings.EmbeddingCreateParams', 'com.openai.models.embeddings.EmbeddingModel'] |
| 概述说明 | Java示例：利用OpenAI API生成文本嵌入，支持环境变量配置。 |

# 说明

该Java示例展示了如何利用OpenAI API生成文本嵌入，并支持通过环境变量进行配置。示例中详细说明了如何设置和调用API，以确保生成高质量的文本嵌入。通过环境变量配置，用户可以灵活调整API密钥和其他相关参数，从而实现更高效的集成和部署。此示例适用于需要在Java应用中嵌入OpenAI API功能的开发者，提供了清晰的指导和实现路径。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| EmbeddingsExample | class | Java示例：使用OpenAI API生成文本嵌入，支持环境变量配置。 |



## 类 EmbeddingsExample

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | EmbeddingsExample |
| 说明 | Java示例：使用OpenAI API生成文本嵌入，支持环境变量配置。 |


### UML类图

```mermaid
classDiagram
    class EmbeddingsExample {
        -EmbeddingsExample()
        +main(String[] args) void
    }

    class OpenAIClient {
        <<Interface>>
        +embeddings() Embeddings
    }

    class OpenAIOkHttpClient {
        +fromEnv() OpenAIClient
    }

    class Embeddings {
        <<Interface>>
        +create(EmbeddingCreateParams params) EmbeddingResult
    }

    class EmbeddingCreateParams {
        +builder() Builder
    }

    class EmbeddingCreateParams.Builder {
        +input(String input) Builder
        +model(EmbeddingModel model) Builder
        +build() EmbeddingCreateParams
    }

    class EmbeddingModel {
        <<Enum>>
        TEXT_EMBEDDING_3_SMALL
    }

    class EmbeddingResult {
        <<Interface>>
    }

    EmbeddingsExample --> OpenAIOkHttpClient : 依赖
    OpenAIOkHttpClient --> OpenAIClient : 实现
    EmbeddingsExample --> OpenAIClient : 依赖
    OpenAIClient --> Embeddings : 依赖
    EmbeddingsExample --> EmbeddingCreateParams : 依赖
    EmbeddingCreateParams --> EmbeddingCreateParams.Builder : 依赖
    EmbeddingCreateParams.Builder --> EmbeddingModel : 依赖
    Embeddings --> EmbeddingResult : 依赖
```

这段代码展示了一个使用OpenAI API生成文本嵌入的示例。`EmbeddingsExample`类通过`OpenAIOkHttpClient`获取`OpenAIClient`实例，并构建`EmbeddingCreateParams`参数来调用`embeddings().create()`方法生成嵌入结果。类图清晰地展示了各个类之间的依赖关系和接口实现，帮助理解代码的结构和功能。


### 内部方法调用关系图

```mermaid
graph TD
    A["类EmbeddingsExample"]
    B["私有构造方法: EmbeddingsExample()"]
    C["main方法: main(String[] args)"]
    D["创建OpenAIClient: OpenAIOkHttpClient.fromEnv()"]
    E["构建EmbeddingCreateParams: EmbeddingCreateParams.builder()"]
    F["设置input: 'The quick brown fox jumped over the lazy dog'"]
    G["设置model: EmbeddingModel.TEXT_EMBEDDING_3_SMALL"]
    H["构建createParams: .build()"]
    I["调用client.embeddings().create(createParams)"]
    J["输出结果: System.out.println()"]

    A --> B
    A -.-> C
    C --> D
    C --> E
    E --> F
    E --> G
    E --> H
    C --> I
    C --> J
```

这段代码展示了如何使用OpenAI的客户端库来创建文本嵌入。首先，通过环境变量配置OpenAIClient，然后构建一个包含输入文本和模型的EmbeddingCreateParams对象。最后，调用客户端的embeddings().create方法生成嵌入，并将结果打印到控制台。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| main | void | Java代码通过环境变量配置OpenAI客户端，创建并输出文本嵌入。 |




