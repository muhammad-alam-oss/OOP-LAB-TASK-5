# OOP-LAB-TASK-5

Payment Methods (Java)

A small Java console program I wrote to understand polymorphism. There's one parent class, Payment, and three child classes for different ways of paying: cash, card and online. Each one handles the pay() method in its own way.

The main thing I wanted to see here is how a single variable of the parent type can hold different child objects and still run the right version of the method.

How it's set up

Payment is the parent class. It has a pay(double amount) method that just prints the amount being paid.

CashPayment, CardPayment and OnlinePayment all extend Payment and override pay(). Each prints the amount along with how it was paid ("in cash", "by card" or "online").

paymentMethods is the main class. It declares one variable, Payment p, and reuses it three times: first it points to a CashPayment, then a CardPayment, then an OnlinePayment. Every time, it calls p.pay(...).

The variable type is always Payment, but Java checks the actual object at runtime and calls that object's own pay(). That's why the same line p.pay(...) gives three different results. This is called runtime polymorphism (or dynamic method dispatch).

What it prints
Paid =500.0 in cash
Paid =1500.0 by card
Paid =5500.0 online
