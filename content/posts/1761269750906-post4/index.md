---
title: "Bài 4: Lập trình hướng đối tượng (OOP) cơ bản trong Java"
date: 2025-10-24
draft: false
tags: ["Java","Cơ bản", "OOP"]
categories: ["Java"]
---
## Giới thiệu 
Lập trình hướng đối tượng (OOP) giúp tổ chức chương trình theo **lớp (class)** và **đối tượng (object)**, phản ánh thực thể ở đời thực bằng **thuộc tính (fields)** và **hành vi (methods)**.  
Bốn trụ cột chính: **đóng gói** (encapsulation), **kế thừa** (inheritance), **đa hình** (polymorphism) và **trừu tượng** (abstraction). Bài này tập trung vào 3 trụ cột đầu + ví dụ thực hành.

---

## Giải thích chi tiết

### Class và Object
- **Class**: bản thiết kế mô tả thuộc tính & hành vi.
- **Object**: thể hiện cụ thể class, được tạo bằng `new`.

```java 
class SinhVien {
    String ten;
    int tuoi;

    void gioiThieu() {
        System.out.println("Tôi là " + ten + ", " + tuoi + " tuổi.");
    }
}
```

### Tạo đối tượng:
```java 
SinhVien sv = new SinhVien();
sv.ten = "An";
sv.tuoi = 20;
sv.gioiThieu();
```

### Đóng gói (Encapsulation):
Ẩn chi tiết bên trong đối tượng; thuộc tính để private, truy cập qua `getter/setter.`
``` java
class Account {
    private String owner;
    private double balance;

    public Account(String owner, double balance) {
        this.owner = owner;
        this.balance = balance;
    }
    public String getOwner() { return owner; }
    public double getBalance() { return balance; }

    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }
    public boolean withdraw(double amount) {
        if (amount > 0 && amount <= balance) { balance -= amount; return true; }
        return false;
    }
}
```