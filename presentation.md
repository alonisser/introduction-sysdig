class: center, middle

# Introduction to sysdig.

## Leaking abstractions and peeking into the system

[live presentation](http://alonisser.github.io/introduction-sysdig) <br/>
[twitter](alonisser@twitter.com), [medium](https://medium.com/@alonisser/)

#####Shameless promotion: you can also read my political blog: [דגל אדום](degeladom@wordpress.com)
---

# Leaking abstractions

Question: Did any one here played with strace? used it in production.

* I did: Looking at system calls and trying to figure out what is going on. 

    "Software, why not you work as expected"

* And this was surly frustrating

---

# Leaking abstractions

* But why did I need to look at system calls?
    

* Spolsky coined the law: "All non-trivial abstractions, to some degree, are leaky"

---

# Leaking abstractions


* Software is a leaking abstraction. Linux is, my python program is.
    
    
* Sometimes the abstracted syscalls, sockets, file descriptors, bytes, tcp connections, strike back.

---

# Sysdig

##self described:
 
 "strace + tcpdump + htop + iftop + lsof + transaction tracing + awesome sauce. With state of the art container visibility on top."


---

# sysdig - Live data

* csysdig is a cursors gui for sysdig

--

```bash
csysdig
```

--
* f2 - views
* f5 - bytes
* f6 - dig

---
# Views!

Default view is htop like but many more available: Containers, connections, cpu, open files, errors.. lots more


---
# Errors!

Sysdig can group and show system errors

* Let's take a look on open file errors

---
# containers!

Sysdig can help with visibility into containers

* In views choose a container,let's try this.

---

# sysdig - recoding 

```bash
sysdig -s 4096 -z -w analysis.scap.gz
```

---

# sysdig - Working with a recorded session

```bash
csysdig -r analysis.scap.gz
```

---

# Chisels

We are not limited to the cursers GUI. It's actually using chisels underneath we can access directly

* For example to see top connections

```bash
sysdig -r analysis.scap.gz -c topconns

```

---

# Read somemore

* [Fishing for hackers with sysdig](https://sysdig.com/blog/fishing-for-hackers/) a great post
* [The law of leaking abstractions](https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/)

---
# More functionality

* [Falco](http://www.sysdig.org/falco/) Security monitoring based on sysdig
* [Tracers](https://sysdig.com/blog/sysdig-tracers/) Tracing performance 

---

class: center, middle

#Open source rocks!

---

class: center, middle

#Thanks for listening!

---
