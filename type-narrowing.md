# Type Narrowing in TypeScript

## Introduction

Type Narrowing is an important concept in TypeScript. Sometimes a variable can have more than one type. In that situation we need to check the type before using it. Type Narrowing helps us to identify the correct type and use it safely.

There are different ways to do Type Narrowing. In this blog I will explain `typeof`, `instanceof` and `in` operator with examples.

## 1. Using typeof

We use `typeof` to check the type of a variable. It is useful for checking strings, numbers and booleans.

For example:

```typescript
function checkValue(value: string | number): string 
{
  if (typeof value === "string") 
  {
    return value.toUpperCase();
  }
  return value.toString();
}
```

Here we check whether the value is a string. If it is a string, we convert it to uppercase. Otherwise we convert the number into a string.

## 2. Using instanceof

We use `instanceof` to check whether an object belongs to a particular class.

For example:

```typescript
function checkDate(value: Date | string): string 
{
  if (value instanceof Date) 
  {
    return value.toDateString();
  }
  return value;
}
```

Here `instanceof` checks whether the value is a Date object.

## 3. Using in Operator

The `in` operator checks whether a property exists in an object.

For example:

```typescript
type Student = { studentId: number };
type Teacher = { subject: string };

function checkPerson(person: Student | Teacher): string 
{
  if ("studentId" in person) 
  {
    return "Student";
  }
  return "Teacher";
}
```

Here we check whether the object has a `studentId` property.

## Conclusion

Type Narrowing helps us handle different data types safely. We can use `typeof` for basic types, `instanceof` for class instances and `in` for checking object properties. These methods make our TypeScript code easier to understand and reduce type errors.