# template-java

Javaプロジェクトを作成するためのテンプレート。

## Gradle tips

[Gradle User Manual](https://docs.gradle.org/current/userguide/userguide.html)

### プロジェクト作成

```
$ gradle init
```

`init` で適宜プロジェクトを作成する。

see [Gradle: Building Java Applications Sample](https://docs.gradle.org/current/samples/sample_building_java_applications.html)  
see [Gradle: Building Java Libraries Sample](https://docs.gradle.org/current/samples/sample_building_java_libraries.html)

### テスト実行

```
$ ./gradlew cleanTest test
```

`./gradlew test` とするとコードの変更点がないと `up-to-date` でテストが実行されない。  
`./gradlew cleanTest test` とすることで変更点がなくてもテストを実行することができる。

see [Gradle: Java plugin tasks clean*TaskName*](https://docs.gradle.org/current/userguide/java_plugin.html#sec:java_tasks)

### テスト実行結果のコンソール出力

*build.gradle*
```
tasks.named('test') {

    ... 省略 ...

    testLogging {
        // see https://docs.gradle.org/current/dsl/org.gradle.api.tasks.testing.logging.TestLoggingContainer.html
        events "PASSED", "SKIPPED", "FAILED", "STANDARD_OUT", "STANDARD_ERROR"
        exceptionFormat "full"
    }
}
```

see [Gradle: TestLogging](https://docs.gradle.org/current/dsl/org.gradle.api.tasks.testing.logging.TestLogging.html)