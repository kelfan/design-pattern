# design-pattern
# singleton = 有且只有一个实例
# singleton 懒汉模式 = 运行时创建
```java
package Singleton;

public class LazySingleton {
    //懒汉式单例模式
    //比较懒，在类加载时，不创建实例，因此类加载速度快，但运行时获取对象的速度慢
    
    private static LazySingleton intance = null;//静态私用成员，没有初始化
    
    private LazySingleton()
    {
        //私有构造函数
    }
    
    public static synchronized LazySingleton getInstance()    //静态，同步，公开访问点
    {
        if(intance == null)
        {
            intance = new LazySingleton();
        }
        return intance;
    }
}
```

# singleton 饿汉模式 = 加载时创建 
```java 
package Singleton;

public class EagerSingleton {
    //饿汉单例模式
    //在类加载时就完成了初始化，所以类加载较慢，但获取对象的速度快
    
    private static EagerSingleton instance = new EagerSingleton();//静态私有成员，已初始化
    
    private EagerSingleton() 
    {
        //私有构造函数
    }
    
    public static EagerSingleton getInstance()    //静态，不用同步（类加载时已初始化，不会有多线程的问题）
    {
        return instance;
    }
```

