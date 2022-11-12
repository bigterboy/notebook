1. Type Alias vs Interface 
    We can use `type` and `interface`

```typescript
    type Student = {
        readonly id: number;   =>  readonly read only can not edit
        name: string;
        age?: number; // optional
}
```

```typescript
    interface Student {
        readonly id: number;
        name: string;
        age?: number; // optional
    }
```

2. Union type

```typescript
    type Status = 'active' | 'inactive';
    type ProductStatus = 0 | 1 | 2 | 3;
    type StudentId = number | string;

    interface Student {
        id: number | string;
        name: string;
        gender: 'male' | 'female';
        grade: 'A' | 'B' | 'C' | 'D' | 'E';
    }
```

3. Intersection type
```typescript
    
    interface BusinessPartner {
        name: string;
        credit: number;
    }
    
    interface Identity {
        id: number;
        name: string;
    }
    
    interface Contact {
        email: string;
        phone: string;
    }

    type Employee = Identity & Contact;
    type Customer = BusinessPartner & Contact;
```

// interface way
```typescript
    interface Employee extends Identity, Contact {}
    interface Customer extends BusinessPartner, Contact {}
```

nếu kết hợp cả 3 thì vd name phải kiểu string hết nếu không sẽ báo lỗi

4. 

```typescript
    interface Student {
        id: number;
        name: string;
    }

    // declaration merging
    // works, no error
    interface Student {
        age?: number;
    }

    const alice: Student = {
        id: 1,
        name: 'Alice',
    }
```