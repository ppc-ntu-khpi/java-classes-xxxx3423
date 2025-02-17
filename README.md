# Звіт

## Практична робота «Створення класів»

### Завдання 1. Створення класу з атрибутами
 
 1. В завданні 1 я склонував створений репозиторій в Netbeans. 
 2. Потім я створив в пакеті domain клас ````Сustomer```` з такими приватними атрибутами:
   - ````ID```` (номер клієнта, ціле число). В мене ````ID=1````
   - ````isNew```` (статус клієнта новий він чи старий, булевське значення). В мене - ````true````. 
   - ````total```` (сума замовлень за рік, дробове число). В мене ````total = 1000````.

### Завдання 2. Додавання в клас методів

В другому завданні я додав до класу метод ````displayCustomerInfo````, який виводить на консоль інформацію про клієнта з допомогою ````System.out.println````. Кожен рядок містить відповідну мітку. 

### Перевірка працездатності створеного класу
 1. Для перевірки я створив в пакеті test клас ````CustomerTest````, в методі ````main```` якого створити об'єкт класу ````Сustomer```` та вивести на екран його властивості з допомогою методу ````displayCustomerInfo````. 
 2. Далі я запустив його. 
 3. Після цього я зробив та зберіг у теку ````Solution```` файли ````done.png```` зі скріншотами результатів роботи програми. 

Завдання виконав "**на п'ять**". Виконав перелічені завдання, змінив файл ````README.md```` з скріншотом програми та зберіг та змінив код класу наступним чином:
- додав конструктор за замовчуванням, який ініціалізує атрибути початковими значеннями. 
- додав методи для зміни атрибутів - ````setID````, ````setStatus````, ````setTotal```` з відповідними параметрами та перевіркою присвоюваних значень
- використав ці методи в методі ````main```` класу ````CustomerTest````
- зробив та зберіг у теку ````Solution```` файл ````advanced1.png````, ````advanced1(2 part)png````, ````advanced2.png```` скріншоти результатів роботи програми, та модифікував файл ````README.md```` відповідним чином.
 
### Вихідні коди

#### Початковий код:

Customer.java

````java
package domain;
public class Customer {
    public int id = 1;
    public boolean isNew = true;
    public float total = 1000;

  
    public int getId() {
        return id;
    }
    public void setId(int id) {
        this.id = id;
    }
    public boolean isIsNew() {
        return isNew;
    }
    public void setIsNew(boolean isNew) {
        this.isNew = isNew;
    }
    public float getTotal() {
        return total;
    }
    public void setTotal(float total) {
        this.total = total;
    }
    
    
 public void displayCustomerInfo(){
    System.out.println("id: " + id);
    System.out.println("isNew: " + isNew);
    System.out.println("total: " + total);
 }}
````

CustomerTest.java

````java
package domain;

public class CustomerTest {
    public static void main(String args[]){
      Customer myCustomer = new Customer();
      myCustomer.displayCustomerInfo();
    }
}
````

#### Змінений код:

Customer.java

```` java
package domain;
public class Customer {
    public int id = 1;
    public boolean isNew = true;
    public float total = 1000;

  public Customer(){
    this.id = 1;
    this.isNew = true;
    this.total = 1000;
}
  
    public int getId() {
        return id;
    }

    public boolean isIsNew() {
        return isNew;
    }
  
    public float getTotal() {
        return total;
    }

  public void setId(int id) {
        if (id > 0) {
            this.id = id;
        }
    }
  
    public void setIsNew(boolean isNew) {
        this.isNew = isNew;
    }
  
    public void setTotal(float total) {
        if (total > 0) {
            this.total = total;
        }
    }
    
    
 public void displayCustomerInfo(){
    System.out.println("id: " + id);
    System.out.println("isNew: " + isNew);
    System.out.println("total: " + total);
 }}
 ````
CustomerTest.java

````java
package domain;

public class CustomerTest {
    public static void main(String args[]){
      Customer myCustomer = new Customer();
      myCustomer.displayCustomerInfo();

      myCustomer.setId(3);
      myCustomer.setIsNew(false);
      myCustomer.setTotal(2000);

       myCustomer.displayCustomerInfo();
    }
}
````
