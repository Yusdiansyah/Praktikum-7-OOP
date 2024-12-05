# Praktikum-7-OOP

## Nama : Yusdiansyah Andika Haryo Saputra 
## NIM  : 312310650
## Kelas: TI.23.A.6

![Alt Text](Screenshot(290)1.png)
## Class Customer
```java
public class customer {
    private String name;
    private String address;

    public customer(String name, String address) {
        this.name = name;
        this.address = address;
    }

    // Getter dan Setter
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }


}
```
## Class Order
```java
import java.util.ArrayList;
import java.util.Date;
import java.util.List;

public class order {
    private Date date;
    private String status;
    private List<orderdetail> orderDetails = new ArrayList<>(); // Kardinalitas 1..*

    public order(Date date, String status) {
        this.date = date;
        this.status = status;
    }

    public float calcSubTotal() {
        // Implementasi logika
        return 0;
    }

    public float calcTax() {
        // Implementasi logika
        return 0;
    }

    public float calcTotal() {
        // Implementasi logika
        return 0;
    }

    public float calcTotalWeight() {
        // Implementasi logika
        return 0;
    }

    // Getter dan Setter
    public Date getDate() {
        return date;
    }

    public void setDate(Date date) {
        this.date = date;
    }

    public String getStatus() {
        return status;
    }

    public void setStatus(String status) {
        this.status = status;
    }

    public List<orderdetail> getOrderDetails() {
        return orderDetails;
    }

    public void addOrderDetail(orderdetail orderDetail) {
        orderDetails.add(orderDetail);
    }
}
```
## Class Order Detail
```java
public class orderdetail {
    private int quantity;
    private String taxStatus;
    private item item; // Agregasi

    public orderdetail(int quantity, String taxStatus, item item) {
        this.quantity = quantity;
        this.taxStatus = taxStatus;
        this.item = item;
    }

    public float calcSubTotal() {
        // Implementasi logika
        return 0;
    }

    public float calcWeight() {
        // Implementasi logika
        return 0;
    }

    public float calcTax() {
        // Implementasi logika
        return 0;
    }

    // Getter dan Setter
    public int getQuantity() {
        return quantity;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }

    public String getTaxStatus() {
        return taxStatus;
    }

    public void setTaxStatus(String taxStatus) {
        this.taxStatus = taxStatus;
    }

    public item getItem() {
        return item;
    }

    public void setItem(item item) {
        this.item = item;
    }
}
```
## Class Item
```java
public class item {
    private float shippingWeight;
    private String description;

    public item(float shippingWeight, String description) {
        this.shippingWeight = shippingWeight;
        this.description = description;
    }

    public float getPriceForQuantity() {
        // Implementasi logika
        return 0;
    }

    public float getTax() {
        // Implementasi logika
        return 0;
    }

    public boolean inStock() {
        // Implementasi logika
        return false;
    }

    // Getter dan Setter
    public float getShippingWeight() {
        return shippingWeight;
    }

    public void setShippingWeight(float shippingWeight) {
        this.shippingWeight = shippingWeight;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }
}
```
## Class Payment
```java
public abstract class payment {
    protected float amount;

    public payment(float amount) {
        this.amount = amount;
    }

    public abstract boolean authorized();
}
```
## Class Cash
```java
public class cash extends payment {
    private float cashTendered;

    public cash(float amount, float cashTendered) {
        super(amount);
        this.cashTendered = cashTendered;
    }

    @Override
    public boolean authorized() {
        // Implementasi logika
        return true;
    }
}
```
## Class Check
```java
public class check extends payment {
    private String name;
    private String bankID;

    public check(float amount, String name, String bankID) {
        super(amount);
        this.name = name;
        this.bankID = bankID;
    }

    @Override
    public boolean authorized() {
        // Implementasi logika
        return true;
    }
}
```
## Class Credit
```java
import java.util.Date;

public class credit extends payment {
    private String number;
    private String type;
    private Date expDate;

    public credit(float amount, String number, String type, Date expDate) {
        super(amount);
        this.number = number;
        this.type = type;
        this.expDate = expDate;
    }

    @Override
    public boolean authorized() {
        // Implementasi logika
        return true;
    }
}
```
