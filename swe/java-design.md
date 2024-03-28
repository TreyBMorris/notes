# Java Design Patterns
[Back](./design.md)

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
