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
public class Flat {
    public int Number { get; set; }
}

public class Tenant {
    public int Id { get; set; }
    public string Name { get; set; }
}

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
    public void RentFor(Tenant tenant);
    public void Release();
    // the rest of OO-style methods
}

public class Tenant {
    public int Id { get; set; }
    public string Name { get; set; }
    public void RentFlat(Flat flat);
    public void ReleaseFlat();
    // the rest of OO-style methods
}
```

---

## Ok, what about architecture?
UI, database, external services, notifications?

---

## Hexagonal Architecture

![](/images/hex-arch.jpg)

---

## What do we get?

1. Testability.
2. Frameworks independecy.
3. UI independecy.
4. Database independecy.
5. Any external agency independecy.

---

![](/images/golden-hummer.png)

---

# NO!

---

## Does DDD worth the effort?
Behavioral-centric app - YES 

Data centric app - NO

---

## When DDD worth the effort?
|System Type|Domain logic complexity|Use cases|DDD payoff?|
|-----|-----|-----|-----|
|CRUD, Master Data, Lookup|Low|Any|No|
|Simple, small, utility|Low|<30|No|
|Departmental, narrow scoped|Low|30<x<40|Could be|
|Innovative|Unknown|?|Yes|
|Enterprize system, Core system|High|>40|Yes|

---

# What about QuickHelp?

---

![](/images/thanks.png)
