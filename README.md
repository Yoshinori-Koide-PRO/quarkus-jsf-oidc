# quarkus-jsf-oidc
Quarkus での JSF + OpenID Connect (Keycloak) サンプル

# サンプルプロジェクトの構築方法

## Quarkus での JSF プラグインは以下

Apache Myfaces のコアAPI が Quarkus のプラグインとして提供されています。

https://github.com/apache/myfaces/tree/master/extensions/quarkus

Showcase 以下が Quarkus + Myfaces Core API のサンプルプロジェクトです。

## 以下のサイトを使用してサンプルダウンロード

GitHub 本体のUIではリポジトリまるごとでしかZipダウンロードできませんが、以下のサービスから特定のディレクトリ以下のZipダウンロードが行えます。

https://downgit.github.io

以下のURLで直接ダウンロードできます。

https://downgit.github.io/#/home?url=https:%2F%2Fgithub.com%2Fapache%2Fmyfaces%2Ftree%2Fmaster%2Fextensions%2Fquarkus%2Fshowcase

## 依存関係の追加


```
        <dependency>
            <groupId>jakarta.faces</groupId>
            <artifactId>jakarta.faces-api</artifactId>
            <version>3.0.0</version>
        </dependency>
```

## 以下のエラー？

```
[INFO] Running org.apache.myfaces.core.extensions.quarkus.showcase.QuarkusMyFacesShowcaseTest
[ERROR] Tests run: 1, Failures: 0, Errors: 1, Skipped: 0, Time elapsed: 10.385 s <<< FAILURE! - in org.apache.myfaces.core.extensions.quarkus.showcase.QuarkusMyFacesShowcaseTest
[ERROR] org.apache.myfaces.core.extensions.quarkus.showcase.QuarkusMyFacesShowcaseTest  Time elapsed: 10.383 s  <<< ERROR!
java.lang.RuntimeException:
java.lang.RuntimeException: io.quarkus.builder.BuildException: Build failure: Build failed due to errors
        [error]: Build step io.quarkus.arc.deployment.ArcProcessor#validate threw an exception: javax.enterprise.inject.spi.DeploymentException: javax.enterprise.inject.UnsatisfiedResolutionException: Unsatisfied dependency for type jakarta.faces.push.PushContext and qualifiers [@Default]
        - java member: org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView#helloChannel
        - declared on CLASS bean [types=[java.io.Serializable, org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView, java.lang.Object], qualifiers=[@Named, 
@Default, @Any], target=org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView]
        at io.quarkus.arc.processor.BeanDeployment.processErrors(BeanDeployment.java:990)
        at io.quarkus.arc.processor.BeanDeployment.init(BeanDeployment.java:234)
        at io.quarkus.arc.processor.BeanProcessor.initialize(BeanProcessor.java:122)
        at io.quarkus.arc.deployment.ArcProcessor.validate(ArcProcessor.java:391)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.base/java.lang.reflect.Method.invoke(Method.java:564)
        at io.quarkus.deployment.ExtensionLoader$2.execute(ExtensionLoader.java:932)
        at io.quarkus.builder.BuildContext.run(BuildContext.java:277)
        at org.jboss.threads.ContextClassLoaderSavingRunnable.run(ContextClassLoaderSavingRunnable.java:35)
        at org.jboss.threads.EnhancedQueueExecutor.safeRun(EnhancedQueueExecutor.java:2046)
        at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.doRunTask(EnhancedQueueExecutor.java:1578)
        at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.run(EnhancedQueueExecutor.java:1452)
        at java.base/java.lang.Thread.run(Thread.java:832)
        at org.jboss.threads.JBossThread.run(JBossThread.java:479)
Caused by: javax.enterprise.inject.UnsatisfiedResolutionException: Unsatisfied dependency for type jakarta.faces.push.PushContext and qualifiers [@Default]
        - java member: org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView#helloChannel
        - declared on CLASS bean [types=[java.io.Serializable, org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView, java.lang.Object], qualifiers=[@Named, 
@Default, @Any], target=org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView]
        at io.quarkus.arc.processor.Beans.resolveInjectionPoint(Beans.java:494)
        at io.quarkus.arc.processor.BeanInfo.init(BeanInfo.java:362)
        at io.quarkus.arc.processor.BeanDeployment.init(BeanDeployment.java:226)
        ... 14 more

Caused by: java.lang.RuntimeException: 
io.quarkus.builder.BuildException: Build failure: Build failed due to errors
        [error]: Build step io.quarkus.arc.deployment.ArcProcessor#validate threw an exception: javax.enterprise.inject.spi.DeploymentException: javax.enterprise.inject.UnsatisfiedResolutionException: Unsatisfied dependency for type jakarta.faces.push.PushContext and qualifiers [@Default]
        - java member: org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView#helloChannel
        - declared on CLASS bean [types=[java.io.Serializable, org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView, java.lang.Object], qualifiers=[@Named, 
@Default, @Any], target=org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView]
        at io.quarkus.arc.processor.BeanDeployment.processErrors(BeanDeployment.java:990)
        at io.quarkus.arc.processor.BeanDeployment.init(BeanDeployment.java:234)
        at io.quarkus.arc.processor.BeanProcessor.initialize(BeanProcessor.java:122)
        at io.quarkus.arc.deployment.ArcProcessor.validate(ArcProcessor.java:391)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.base/java.lang.reflect.Method.invoke(Method.java:564)
        at io.quarkus.deployment.ExtensionLoader$2.execute(ExtensionLoader.java:932)
        at io.quarkus.builder.BuildContext.run(BuildContext.java:277)
        at org.jboss.threads.ContextClassLoaderSavingRunnable.run(ContextClassLoaderSavingRunnable.java:35)
        at org.jboss.threads.EnhancedQueueExecutor.safeRun(EnhancedQueueExecutor.java:2046)
        at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.doRunTask(EnhancedQueueExecutor.java:1578)
        at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.run(EnhancedQueueExecutor.java:1452)
        at java.base/java.lang.Thread.run(Thread.java:832)
        at org.jboss.threads.JBossThread.run(JBossThread.java:479)
Caused by: javax.enterprise.inject.UnsatisfiedResolutionException: Unsatisfied dependency for type jakarta.faces.push.PushContext and qualifiers [@Default]
        - java member: org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView#helloChannel
        - declared on CLASS bean [types=[java.io.Serializable, org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView, java.lang.Object], qualifiers=[@Named, 
@Default, @Any], target=org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView]
        at io.quarkus.arc.processor.Beans.resolveInjectionPoint(Beans.java:494)
        at io.quarkus.arc.processor.BeanInfo.init(BeanInfo.java:362)
        at io.quarkus.arc.processor.BeanDeployment.init(BeanDeployment.java:226)
        ... 14 more

Caused by: io.quarkus.builder.BuildException: 
Build failure: Build failed due to errors
        [error]: Build step io.quarkus.arc.deployment.ArcProcessor#validate threw an exception: javax.enterprise.inject.spi.DeploymentException: javax.enterprise.inject.UnsatisfiedResolutionException: Unsatisfied dependency for type jakarta.faces.push.PushContext and qualifiers [@Default]
        - java member: org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView#helloChannel
        - declared on CLASS bean [types=[java.io.Serializable, org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView, java.lang.Object], qualifiers=[@Named, 
@Default, @Any], target=org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView]
        at io.quarkus.arc.processor.BeanDeployment.processErrors(BeanDeployment.java:990)
        at io.quarkus.arc.processor.BeanDeployment.init(BeanDeployment.java:234)
        at io.quarkus.arc.processor.BeanProcessor.initialize(BeanProcessor.java:122)
        at io.quarkus.arc.deployment.ArcProcessor.validate(ArcProcessor.java:391)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.base/java.lang.reflect.Method.invoke(Method.java:564)
        at io.quarkus.deployment.ExtensionLoader$2.execute(ExtensionLoader.java:932)
        at io.quarkus.builder.BuildContext.run(BuildContext.java:277)
        at org.jboss.threads.ContextClassLoaderSavingRunnable.run(ContextClassLoaderSavingRunnable.java:35)
        at org.jboss.threads.EnhancedQueueExecutor.safeRun(EnhancedQueueExecutor.java:2046)
        at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.doRunTask(EnhancedQueueExecutor.java:1578)
        at org.jboss.threads.EnhancedQueueExecutor$ThreadBody.run(EnhancedQueueExecutor.java:1452)
        at java.base/java.lang.Thread.run(Thread.java:832)
        at org.jboss.threads.JBossThread.run(JBossThread.java:479)
Caused by: javax.enterprise.inject.UnsatisfiedResolutionException: Unsatisfied dependency for type jakarta.faces.push.PushContext and qualifiers [@Default]
        - java member: org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView#helloChannel
        - declared on CLASS bean [types=[java.io.Serializable, org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView, java.lang.Object], qualifiers=[@Named, 
@Default, @Any], target=org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView]
        at io.quarkus.arc.processor.Beans.resolveInjectionPoint(Beans.java:494)
        at io.quarkus.arc.processor.BeanInfo.init(BeanInfo.java:362)
        at io.quarkus.arc.processor.BeanDeployment.init(BeanDeployment.java:226)
        ... 14 more

Caused by: javax.enterprise.inject.spi.DeploymentException: 
javax.enterprise.inject.UnsatisfiedResolutionException: Unsatisfied dependency for type jakarta.faces.push.PushContext and qualifiers [@Default]
        - java member: org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView#helloChannel
        - declared on CLASS bean [types=[java.io.Serializable, org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView, java.lang.Object], qualifiers=[@Named, 
@Default, @Any], target=org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView]
Caused by: javax.enterprise.inject.UnsatisfiedResolutionException: 
Unsatisfied dependency for type jakarta.faces.push.PushContext and qualifiers [@Default]
        - java member: org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView#helloChannel
        - declared on CLASS bean [types=[java.io.Serializable, org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView, java.lang.Object], qualifiers=[@Named, 
@Default, @Any], target=org.apache.myfaces.core.extensions.quarkus.showcase.view.SocketView]
```

→ Showcase 単体でのビルドを断念

→ プラグインまるごとビルドしてみる。

以下から取得

https://downgit.github.io/#/home?url=https:%2F%2Fgithub.com%2Fapache%2Fmyfaces%2Ftree%2F2.3-next%2Fextensions

myfaces まるごとやってみる main は失敗

2.3-next ブランチで成功

# Apache MyFaces Tobago

JSF リッチコンポーネント

http://tobago-vm.apache.org/

GitHub リポジトリ

https://github.com/apache/myfaces-tobago

masterはビルドが通らないので 4.x で試してみる。

```
$ git checkout tobago-4.x

$ mvn install
```

デモを動かしてみる

```
$ cd tobago-example/tobago-example-demo

$ mvn jetty:run
```
