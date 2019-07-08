1、避免内部类定义过多，属于函数式编程
2、可含参，返回值，但不能有多个方法，否则无法自动识别
3、定义接口  --->  类继承接口  --->   实例化(lambda表达式)   --->调用方法
```
interface Like{
    void function(int i);
}
class Ilike implements Like{

    @Override
    public void function(int i) {
        System.out.println("1nihao1"+i);
    }
}

interface Love{
    int function(int a,int b);
}

class Ilove implements Love{

    @Override
    public int function(int a, int b) {
        return a+b;
    }
}

public class LambdaTest01 {

    public static void main(String[] args) {
//        Like Ilike = (int a)->{
//            System.out.println("nihao"+ a);
//        };
        Like Ilike = a-> System.out.println("test"+a);
        Ilike.function(12);

        Love iLove = (a, b) -> {
            System.out.println(a+b);
            return a+b;
        };
        System.out.println(iLove.function(10,20));
    }
}

```

结合多线程
```
public class LambdaTread {
    public static void main(String[] args) {
        new Thread(()-> System.out.println("Learn Lambda")
        ).start();

        new Thread( ()->{
            for(int i=0 ;i<100; i++)
                System.out.println("Learn Java");
        }
        ).start();

        new Thread( ()-> System.out.println("simple") ).start();
    }
}

```

