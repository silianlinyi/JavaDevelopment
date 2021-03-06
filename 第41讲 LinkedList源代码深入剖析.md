# 第41讲 LinkedList源代码深入剖析

### 关于ArrayList与LinkedList的比较分析

* （1）ArrayList底层使用数组实现的，LinkedList底层采用双向链表实现。
* （2）当执行插入或者删除操作时，采用LinkedList比较好。
* （3）当执行搜索操作时，采用ArrayList比较好。

使用LinkedList类创建一个Stack类

> Stack.java

    public class Stack {
    	LinkedList list = new LinkedList();
    
    	public Object push(Object o) {
    		list.add(o);
    		return o;
    	}
    
    	public Object pop() {
    		return list.removeLast();
    	}
    
    	public Object peek() {
    		return list.peekLast();
    	}
    
    	public boolean isEmpty() {
    		return list.isEmpty();
    	}
    }

> LinkedList.java

    package java.util;
    
    public class LinkedList<E> 
        extends AbstractSequentialList<E>
        implements List<E>, Deque<E>, Cloneable, java.io.Serializable
    {
        // 记录元素个数
        transient int size = 0;
        
        // 指向第一个节点
        transient Node<E> first;
    
        // 指向最后一个节点
        transient Node<E> last;
        
        /**
         * 构造一个空的列表
         */
        public LinkedList() {
        }
        
        public LinkedList(Collection<? extends E> c) {
            this();
            addAll(c);
        }
        
        
        
    }











































