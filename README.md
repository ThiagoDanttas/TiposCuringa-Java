# Tipos curinga (wildcard types)

---

### Generics s�o invariantes
~~~~java
public class Program {
    public static void main(String[] args){
        List<Object> // n�o � o supertipo de qualquer tipo de lista:
        List<Object> myObjs = new ArrayList<Object>();
        List<Integer> myNumbers = new ArrayList<Integer>();
        myObjs = myNumbers; // erro de compila��o
        
        // O supertipo de qualquer tipo de lista � List<?>. Este � um tipo curinga:
        List<?> myObjs = new ArrayList<Object>();
        List<Integer> myNumbers = new ArrayList<Integer>();
        myObjs = myNumbers;
    }
}

~~~~
### O supertipo de qualquer tipo de lista � List<?>. Este � um tipo curinga:

~~~~java
public class Program {
    public static void main(String[] args){
        
        List<?> myObjs = new ArrayList<Object>();
        List<Integer> myNumbers = new ArrayList<Integer>();
        myObjs = myNumbers;
    }
}

~~~~

### Com tipos curinga podemos fazer m�todos que recebem um gen�rico de "qualquer tipo":


~~~~java

public class Program {
    public static void main(String[] args) {
        List<Integer> myInts = Arrays.asList(5, 2, 10);
        printList(myInts);
    }
        public static void printList(List<?> list) {
        for (Object obj : list) {
        System.out.println(obj);
        }
    }
}

~~~~

### Por�m n�o � poss�vel adicionar dados a uma cole��o de tipo curinga
~~~~java


public class Program {
    public static void main(String[] args) {
    List<?> list = new ArrayList<Integer>();
    list.add(3); // erro de compila��o; O compilador n�o sabe qual � o tipo espec�fico do qual a lista foi instanciada.
    }
}

~~~~
