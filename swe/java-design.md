# Java Design Patterns
[Back](./swe.md)

## What are design patterns?
Design patterns in the world of Software Engineering are reusable solutions that address a problem or various problems. To put it simply, patterns are a "blueprint" to solve problems in our applications.

#### Jump to a Section
- [Factory Pattern](#factory-pattern)


## Factory Pattern
The factory design pattern is a very commonly used pattern in the world of software engineering. With the factory design pattern, we do not need to specify the concrete class during the creation of the product objects.

Here is an example of a factory pattern in Java.

Our product interface.
```Java
public interface Product
{
    void displayProduct();
}
```

Now we can implement our products by impltementing the interface.
```Java
class ProductA implements Product
{
    @Override
    public void displayProduct()
    {
        System.out.println("This is our product A");
    }
}

class ProductB implements Product
{
    @Override
    public void displayProduct()
    {
        System.out.println("This is our product B");
    }
}

```

Next, we would create our Factory that creates our products.

```Java
public class ProductFactory
{
    public static Product createProduct(String productType)
    {
        switch(productType.toLowerCase())
        {
            case "a":
                return new ProductA();
                break;
            case "b":
                return new ProductB();
                break;
            default:
                throw new IllegalArgumentException("Invalid product type: " + productType);
        }
    }
}

```

Finally, we can have our main class that creates and displays our products.

```Java
public class Main
{
    public static void main(String [] args)
    {
        Product productA = ProductFactory.createProduct("a");
        Product productB = ProductFactory.createProduct("b");


        //This displays "This is our product A"
        productA.displayProduct();
        //This displays "This is our product B"
        productB.displayProduct();
    }
}
```

## Builder Pattern
Builder is a design pattern that lets you construct objects step by step. This allows one to produce objects that have different types and properties, but use the same construction code.

Below is a quick example of a builder interface in Java
```Java
public interface Builder
{
    void setProductType(ProductType type);
    void setProductName(String productName);
}

```

From here, we can implement this interface to classes that will build our objects, like so.

```Java
public class ProductBuilder implements Builder
{
    private ProductType type;
    private String productName;

    public void setProductType(ProductType type)
    {
        this.type = type;
    }
    
    @Override
    public void setProductName(String productName)
    {
        this.productName = productName;
    }

}
```

#### References:
https://refactoring.guru/design-patterns/java
https://medium.com/@saygiligozde/design-patterns-in-java-5251032ca244