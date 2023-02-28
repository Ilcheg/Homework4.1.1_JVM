# Homework4.1.1_JVM Описание кода

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


JVM стартует, LOADING - запускается подсистема загрузчиков классов (Application ClassLoader -> Platform ClassLoader -> Bootstrap ClassLoader -> Platform ClassLoader -> Application ClassLoader), загружаются классы. LINKING (Verify, Prepare, Resolve). Initialization.
1. 
