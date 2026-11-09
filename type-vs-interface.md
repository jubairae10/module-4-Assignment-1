# Difference Between Type and Interface in TypeScript

## Introduction

In TypeScript we can use both `type` and `interface` to define the structure of our data. Both are useful for writing code and checking data types. But there are some differences between them. In this blog I will explain these differences and when we should use them.

## What is Type?

A `type` is used to create a custom type in TypeScript. We can use it for strings, numbers, objects, unions and tuples.

For example:

```typescript
type UserId = string | number;

type Student = {
  name: string;
  age: number;
};
```

Here `UserId` can be a string or number. And `Student` defines an object with a name and age.

## What is Interface?

An `interface` is mainly used to define the structure of an object.

For example:

```typescript
interface Student 
{
  name: string;
  age: number;
}
```

Here the `Student` interface tells us that a student object must have a name and age.

## Main Differences

The first difference is that `type` can define union types but `interface` cannot directly do that.

Another difference is declaration merging. If we create two interfaces with the same name, TypeScript can combine them.

```typescript
interface Person 
{
  name: string;
}

interface Person 
{
  age: number;
}
```

Now `Person` contains both name and age.

We can also extend interfaces using `extends`. For types, we can combine object types using `&`.

## Conclusion

Both `type` and `interface` are important in TypeScript. We should use `interface` when working with object structures and classes. On the other hand, `type` is useful for unions, tuples and other type combinations. So we should choose them based on our requirements.