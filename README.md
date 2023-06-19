# teamcity_java_test

This repository contains two simple "Hello Project" examples written in Java (version 2.13.6). One is compatible with Java 1.8, while the other works with Java 17. The only difference between the projects is their Java version. Both projects can be built successfully locally using IntelliJ IDEA 20231.2.

However, when building with TeamCity 2023.05, only the Java 1.8 version can be built successfully. Attempting to build the Java 17 version results in the following exception:

java.lang.reflect.InvocationTargetException
09:15:50       at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
09:15:50       at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
09:15:50       at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
09:15:50       at java.base/java.lang.reflect.Method.invoke(Method.java:568)
09:15:50       at org.codehaus.groovy.tools.GroovyStarter.rootLoader(GroovyStarter.java:116)
09:15:50       at org.codehaus.groovy.tools.GroovyStarter.main(GroovyStarter.java:138)
09:15:50       at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
09:15:50       at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
09:15:50       at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
09:15:50       at java.base/java.lang.reflect.Method.invoke(Method.java:568)
09:15:50       at jetbrains.buildServer.agent.ideaRunner.ToolsAwareGroovyStarter.main(ToolsAwareGroovyStarter.java:48)
09:15:50     Caused by: groovy.lang.MissingMethodException: No signature of method: org.codehaus.groovy.tools.RootLoader.getPackage() is applicable for argument types: (java.lang.String) values: [gant]
09:15:50       at org.codehaus.groovy.runtime.ScriptBytecodeAdapter.unwrap(ScriptBytecodeAdapter.java:71)
09:15:50       at org.codehaus.groovy.runtime.callsite.PojoMetaClassSite.call(PojoMetaClassSite.java:48)
09:15:50       at org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCall(CallSiteArray.java:47)
09:15:50       at org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:116)
09:15:50       at org.codehaus.groovy.runtime.callsite.AbstractCallSite.call(AbstractCallSite.java:128)
09:15:50       at gant.Gant.<init>(Gant.groovy:192)
09:15:50       at gant.Gant.<init>(Gant.groovy:180)
09:15:50       at gant.Gant.<init>(Gant.groovy:173)
09:15:50       at java.base/jdk.internal.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)
09:15:50       at java.base/jdk.internal.reflect.NativeConstructorAccessorImpl.newInstance(NativeConstructorAccessorImpl.java:77)
09:15:50       at java.base/jdk.internal.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)
09:15:50       at java.base/java.lang.reflect.Constructor.newInstanceWithCaller(Constructor.java:499)
09:15:50       at java.base/java.lang.reflect.Constructor.newInstance(Constructor.java:480)
09:15:50       at org.codehaus.groovy.reflection.CachedConstructor.invoke(CachedConstructor.java:83)
09:15:50       at org.codehaus.groovy.runtime.callsite.ConstructorSite$ConstructorSiteNoUnwrapNoCoerce.callConstructor(ConstructorSite.java:105)
09:15:50       at org.codehaus.groovy.runtime.callsite.CallSiteArray.defaultCallConstructor(CallSiteArray.java:59)
09:15:50       at org.codehaus.groovy.runtime.callsite.AbstractCallSite.callConstructor(AbstractCallSite.java:238)
09:15:50       at org.codehaus.groovy.runtime.callsite.AbstractCallSite.callConstructor(AbstractCallSite.java:242)
09:15:50       at gant.Gant.main(Gant.groovy:667)
09:15:50       ... 11 more


