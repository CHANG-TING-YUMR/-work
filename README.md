```
傳直呼叫
方法的虛引數如果宣告為基本資料型别，
如: char,byte,short,int,long,float,double,boolean,char八種型別變數
，就表示該方法的引數傳遞方式是採傳值呼叫（Call By Value）。基本資料型別的變數是存放在Stack堆疊儲存空間，
方法若採傳值呼叫，則呼叫敘述的實引引數與被呼叫方法的虛引數是分別佔用不同記憶體，因此，使用傳值呼叫可以防止變數被方法更改。

參考呼叫
方法中的虚引數若宣告為參考資料型別
如陣列，物件..等，表示此方法的引數傳遞方式是採參考呼叫（Call By Reference）
所謂的「參考呼叫」，就是呼叫敘述的實引|數與被呼叫方法的虛引數，兩者佔用同一記憶體位址，也就是說在做引數傳遞時，呼叫敘述中的實引數是將自己本身的記憶體位址傳給被呼叫方法的虛引數因此，
以參考呼叫傳遞引數的好處，就是被呼叫方法可以透過該引數直接將資料值傳回給呼叫敘述。

方法多載（Overloading）
是指多個名稱相同但參數個數或型別不同的方法
，編譯器依傳入參數的個數、型別與順序決定使用哪一個方法。
概念上多載讓方法變得更彈性，能接受不同參數組合，符合更多應用情境。
舉個常見的例子，Convert.ToByte() 可傳入 int, short, string, float, double, decimal, char… 等輸入值
，將其轉成 byte，傳入 string 時還能指定 16 進位（fromBase）或 IFormatProvider。

```
### 靜態遞迴  Fibonacci Series
```
public class RecursionExample4 {  
    static int n1=0,n2=1,n3=0;      
     static void printFibo(int count){      
        if(count>0){      
             n3 = n1 + n2;      
             n1 = n2;      
             n2 = n3;      
             System.out.print(" "+n3);     
             printFibo(count-1);      
         }      
     }        
  
public static void main(String[] args) {  
    int count=15;      
      System.out.print(n1+" "+n2);//printing 0 and 1      
      printFibo(count-2);//n-2 because 2 numbers are already printed     
}  
}  
```
## 結果:
```
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377
```

### iterative:
```
import java.util.Collection;  
import java.util.Iterator;  
import java.util.concurrent.ConcurrentLinkedQueue;  
public class JavaCollectionIteratorExample1 {  
    static int i = 1;  
    public static void main(String[] args) {  
        Collection<String> collection = new ConcurrentLinkedQueue<String>();  
        collection.add("Ram");  
        collection.add("Sham");  
        collection.add("Mira");  
        collection.add("Rajesh");  
        Iterator<String> iterator = collection.iterator();  
        //Returns an iterator over the elements  
        while (iterator.hasNext()) {  
            System.out.println(i++ + "." + iterator.next());  
        }  
    }  
    
 ```
 ## 結果
 ```
 1.Ram
2.Sham
3.Mira
4.Rajesh
```
