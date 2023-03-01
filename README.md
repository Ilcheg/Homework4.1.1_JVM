# Homework4.1.1_JVM Описание кода
```java

public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;                      // 1
        Object o = new Object();        // 2
        Integer ii = 2;                 // 3
        printAll(o, i, ii);             // 4
        System.out.println("finished"); // 7
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5
        System.out.println(o.toString() + i + ii);  // 6
    }
}

```

JVM стартует: LOADING - запускается подсистема загрузчиков классов (Application ClassLoader -> Platform ClassLoader -> Bootstrap ClassLoader -> Platform ClassLoader -> Application ClassLoader), загружаются классы.   
LINKING (Verify, Prepare, Resolve). Initialization.   
**Все метаданные загружаются в Metaspace.**   
**Вызывается метод main - создаётся фрейм в Stack memory.**  
1. Создаётся в стеке в фрейме метода main переменная i со значением 1.  
2. Создаётся Object в Heap, ссылка на него "o" сохраняется в Stack.  
3. Создаётся Integer в Heap, ссылка на него "ii" сохраняется в Stack, там же присвается значение 2.  
4. Вызывается метод printAll - создаётся новый фрейм в стеке. Создаются новые ссылки в этом фрейме на уже сохранённые объекты в Heap: Object, Integer. Создаётся в этом же фрейме переменная i.  
5. Создаётся новая ссылка на объект Integer в стеке в фрейме метода printALL с значением 700.  
6. Вызывается метод println сохраняется в новом фрейме в стеке, сохраняются новые ссылки на объекты и переменные из параметров.  
7. Вызывается метод println сохраняется в новом фрейме в стеке, создаётся объект String в Heap.
