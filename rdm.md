## Hexagonal Architecture
![](/images/hex-arch-fun.jpeg)

---

## Case study
![](/images/land-use-case.png)

---

## Our usual approach
![](/images/layered-arch.jpg)

---

## Advantages
1. Easy to implement
2. Well known
3. Scalable

---

## When the problems come?
1. Bloated services
2. Non-testability
3. Vendor/technology lock-in
5. Portability

----

## Bloated Services 
Say "Hello" to  ADM

1. Complex code
2. Procedural (not OO)

----

## Non-testability
How would you test bloated services which are heavily relaying on DA layer?

----

## Vendor/technology lock-in
Can you change MS SQL to MongoDB? Cassandra?

----

## Portability
Imagine you wrote in in Java.
Can you run it on iOS?

---

## Solution
RDM - Rich Domain Model

----

## ADM approach
```
public class RentService {
    public void RentFlat(int flatNumber, int tenantId);
    public void ReleaseFlat(int number);
    // the rest of procedural-style methods
}
```

----

## RDM approach
```
public class Flat {
    public int Number { get; set; }
    public void Rent(int number);
    public void Release();
    // the rest of OO-style methods
}
```
