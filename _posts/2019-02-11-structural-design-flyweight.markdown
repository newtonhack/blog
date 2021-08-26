---
layout: post
title: "Flyweight - Structural Design Pattern"
date: 2019-02-11 20:00:00 +0530
description: Notes about design patterns. # Add post description (optional)
img: design-pattern.jpg # Add image post (optional)
tags: design-patterns
categories: structural-pattern
icon: blogging.png
---
🍃 Flyweight
-----------
It is used to minimize memory usage or computational expenses by sharing as much as possible with similar objects

Example:
```java
class CoffeeFlavour {
    private final String name;
    private static final WeakHashMap<String, CoffeeFlavour> CACHE = new WeakHashMap<>();
    // only intern() can call this constructor
    private CoffeeFlavour(String name) {
        this.name = name;
    }
    @Override
    public String toString() {
        return name;
    }
    public static CoffeeFlavour intern(String name) {
        synchronized (CACHE) {
            return CACHE.computeIfAbsent(name, CoffeeFlavour::new);
        }
    }
    public static int flavoursInCache() {
        synchronized (CACHE) {
            return CACHE.size();
        }
    }
}
@FunctionalInterface
interface Order {
    void serve();

    static Order of(String flavourName, int tableNumber) {
        CoffeeFlavour flavour = CoffeeFlavour.intern(flavourName);
        return () -> System.out.println("Serving " + flavour + " to table " + tableNumber);
    }
}
class CoffeeShop {
    private final ArrayList<Order> orders = new ArrayList<>();

    public void takeOrder(String flavour, int tableNumber) {
        orders.add(Order.of(flavour, tableNumber));
    }

    public void service() {
        orders.forEach(Order::serve);
    }
}
public class FlyweightExample {
    public static void main(String[] args) {
        CoffeeShop shop = new CoffeeShop();
        shop.takeOrder("Cappuccino", 2);
        shop.takeOrder("Frappe", 1);
        shop.takeOrder("Espresso", 1);
        shop.takeOrder("Frappe", 897);
        shop.takeOrder("Cappuccino", 97);
        shop.takeOrder("Frappe", 3);
        shop.takeOrder("Espresso", 3);
        shop.takeOrder("Cappuccino", 3);
        shop.takeOrder("Espresso", 96);
        shop.takeOrder("Frappe", 552);
        shop.takeOrder("Cappuccino", 121);
        shop.takeOrder("Espresso", 121);

        shop.service();
        System.out.println(
            "CoffeeFlavor objects in cache: " + CoffeeFlavour.flavoursInCache()
            );
  }
}
```