# grails-dbm-gorm-diff-grails5rc1-issue

Grails DB-Migration plugin does not work with Grails 5.0.0.rc1 due to dependency scoping (compile vs. implementation) problems.


```
grails dbm-generate-changelog changelog.groovy
...
Exception in thread "main" java.lang.NoClassDefFoundError: org/hibernate/service/ServiceRegistry
        at org.grails.plugins.databasemigration.command.DbmFutureRollbackSqlCommand.<clinit>(DbmFutureRollbackSqlCommand.groovy)
        at java.base/jdk.internal.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)
        at java.base/jdk.internal.reflect.NativeConstructorAccessorImpl.newInstance(NativeConstructorAccessorImpl.java:62)
        at java.base/jdk.internal.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)
        at java.base/java.lang.reflect.Constructor.newInstance(Constructor.java:490)
        at org.codehaus.groovy.reflection.CachedConstructor.invoke(CachedConstructor.java:72)
        at org.codehaus.groovy.reflection.CachedConstructor.doConstructorInvoke(CachedConstructor.java:59)
        at groovy.lang.MetaClassImpl.invokeConstructor(MetaClassImpl.java:1826)
        at groovy.lang.MetaClassImpl.invokeConstructor(MetaClassImpl.java:1615)
        at org.codehaus.groovy.runtime.InvokerHelper.invokeConstructorOf(InvokerHelper.java:1060)
        at org.codehaus.groovy.runtime.DefaultGroovyMethods.newInstance(DefaultGroovyMethods.java:17679)
        at org.grails.core.io.support.GrailsFactoriesLoader.loadFactoriesWithArguments(GrailsFactoriesLoader.groovy:65)
        at org.grails.core.io.support.GrailsFactoriesLoader.loadFactories(GrailsFactoriesLoader.groovy:47)
        at grails.dev.commands.ApplicationContextCommandRegistry.<clinit>(ApplicationContextCommandRegistry.groovy:33)
        at grails.ui.command.GrailsApplicationContextCommandRunner.run(GrailsApplicationContextCommandRunner.groovy:45)
        at grails.ui.command.GrailsApplicationContextCommandRunner.main(GrailsApplicationContextCommandRunner.groovy:102)
Caused by: java.lang.ClassNotFoundException: org.hibernate.service.ServiceRegistry
        at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:581)
        at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:178)
        at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:522)
        ... 16 more
``` 
