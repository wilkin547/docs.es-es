---
title: Crear interfaces genéricas variantes (C#)
ms.date: 07/20/2015
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
ms.openlocfilehash: a8e3e010c0e5d5490aee35603cad4fd6c1dc29e0
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990049"
---
# <a name="creating-variant-generic-interfaces-c"></a>Crear interfaces genéricas variantes (C#)

Puede declarar parámetros de tipo genérico en las interfaces como covariantes o contravariantes. La *covarianza* permite que los métodos de interfaz tengan tipos de valor devuelto más derivados que los que se definen en los parámetros de tipo genérico. La *contravarianza* permite que los métodos de interfaz tengan tipos de argumento menos derivados que los que se especifican en los parámetros genéricos. Las interfaces genéricas que tienen parámetros de tipo genérico covariantes o contravariantes se llaman *variantes*.

> [!NOTE]
> En .NET Framework 4 se ha presentado la compatibilidad con la varianza para varias interfaces genéricas existentes. Para ver la lista de interfaces variantes de .NET, vea [Varianza en interfaces genéricas (C#)](./variance-in-generic-interfaces.md).

## <a name="declaring-variant-generic-interfaces"></a>Declarar interfaces genéricas variantes

Puede declarar interfaces genéricas variantes mediante las palabras clave `in` y `out` para los parámetros de tipo genérico.

> [!IMPORTANT]
> Los parámetros `ref`, `in` y `out` de C# no pueden ser variantes. Los tipos de valor tampoco admiten la varianza.

Puede declarar un parámetro de tipo genérico covariante mediante la palabra clave `out`. El tipo covariante debe cumplir las siguientes condiciones:

- El tipo se usa únicamente como tipo de valor devuelto de los métodos de interfaz, y no como tipo de los argumentos de método. Esto se muestra en el siguiente ejemplo, en el que el tipo `R` se declara como covariante.

    ```csharp
    interface ICovariant<out R>
    {
        R GetSomething();
        // The following statement generates a compiler error.
        // void SetSomething(R sampleArg);

    }
    ```

    Hay una excepción para esta regla. Si tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo como parámetro de tipo genérico para el delegado. Esto se muestra en el siguiente ejemplo con el tipo `R`. Para obtener más información, vea [Varianza en delegados (C#)](./variance-in-delegates.md) y [Usar la varianza para los delegados genéricos Func y Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).

    ```csharp
    interface ICovariant<out R>
    {
        void DoSomething(Action<R> callback);
    }
    ```

- El tipo no se usa como restricción genérica para los métodos de interfaz. Esto se muestra en el siguiente código.

    ```csharp
    interface ICovariant<out R>
    {
        // The following statement generates a compiler error
        // because you can use only contravariant or invariant types
        // in generic constraints.
        // void DoSomething<T>() where T : R;
    }
    ```

Puede declarar un parámetro de tipo genérico contravariante mediante la palabra clave `in`. El tipo contravariante solo se puede usar como tipo de los argumentos de método, y no como tipo de valor devuelto de los métodos de interfaz. El tipo contravariante también se puede usar para las restricciones genéricas. En el siguiente código se muestra cómo declarar una interfaz contravariante y cómo usar una restricción genérica para uno de sus métodos.

```csharp
interface IContravariant<in A>
{
    void SetSomething(A sampleArg);
    void DoSomething<T>() where T : A;
    // The following statement generates a compiler error.
    // A GetSomething();
}
```

También se puede admitir la covarianza y la contravarianza en la misma interfaz, pero para distintos parámetros de tipo, como se muestra en el siguiente ejemplo de código.

```csharp
interface IVariant<out R, in A>
{
    R GetSomething();
    void SetSomething(A sampleArg);
    R GetSetSomethings(A sampleArg);
}
```

## <a name="implementing-variant-generic-interfaces"></a>Implementar interfaces genéricas variantes

Las interfaces genéricas variantes se implementan en las clases usando la misma sintaxis que se usa para las interfaces invariables. En el siguiente ejemplo de código se muestra cómo implementar una interfaz covariante en una clase genérica.

```csharp
interface ICovariant<out R>
{
    R GetSomething();
}
class SampleImplementation<R> : ICovariant<R>
{
    public R GetSomething()
    {
        // Some code.
        return default(R);
    }
}
```

Las clases que implementan interfaces variantes son invariables. Por ejemplo, considere el fragmento de código siguiente:

```csharp
// The interface is covariant.
ICovariant<Button> ibutton = new SampleImplementation<Button>();
ICovariant<Object> iobj = ibutton;

// The class is invariant.
SampleImplementation<Button> button = new SampleImplementation<Button>();
// The following statement generates a compiler error
// because classes are invariant.
// SampleImplementation<Object> obj = button;
```

## <a name="extending-variant-generic-interfaces"></a>Extender interfaces genéricas variantes

Al extender una interfaz genérica variante, debe usar las palabras clave `in` y `out` para especificar de forma explícita si la interfaz derivada admite la varianza. El compilador no infiere la varianza de la interfaz que se va a extender. Por ejemplo, observe las siguientes interfaces.

```csharp
interface ICovariant<out T> { }
interface IInvariant<T> : ICovariant<T> { }
interface IExtCovariant<out T> : ICovariant<T> { }
```

En la interfaz `IInvariant<T>`, el parámetro de tipo genérico `T` es invariable, mientras que en `IExtCovariant<out T>` el parámetro de tipo es covariante, si bien ambas interfaces extienden la misma interfaz. La misma regla se aplica a los parámetros de tipo genérico contravariantes.

Puede crear una interfaz que extienda la interfaz donde el parámetro de tipo genérico `T` es covariante y la interfaz donde es contravariante si, en la interfaz que va a extender, el parámetro de tipo genérico `T` es invariable. Esto se muestra en el siguiente código de ejemplo.

```csharp
interface ICovariant<out T> { }
interface IContravariant<in T> { }
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }
```

Pero si un parámetro de tipo genérico `T` se declara como covariante en una interfaz, no puede declararlo como contravariante en la interfaz extensible (o viceversa). Esto se muestra en el siguiente código de ejemplo.

```csharp
interface ICovariant<out T> { }
// The following statement generates a compiler error.
// interface ICoContraVariant<in T> : ICovariant<T> { }
```

### <a name="avoiding-ambiguity"></a>Evitar la ambigüedad

Al implementar interfaces genéricas variantes, la varianza a veces puede implicar ambigüedad. Debe evitarse esta ambigüedad.

Por ejemplo, si implementa explícitamente en una clase la misma interfaz genérica variante con distintos parámetros de tipo genérico, puede crear ambigüedad. El compilador no genera ningún error en este caso, pero no se especifica qué implementación de interfaz se va a elegir en tiempo de ejecución. Esta ambigüedad podría provocar errores sutiles en el código. Observe el siguiente ejemplo de código.

```csharp
// Simple class hierarchy.
class Animal { }
class Cat : Animal { }
class Dog : Animal { }

// This class introduces ambiguity
// because IEnumerable<out T> is covariant.
class Pets : IEnumerable<Cat>, IEnumerable<Dog>
{
    IEnumerator<Cat> IEnumerable<Cat>.GetEnumerator()
    {
        Console.WriteLine("Cat");
        // Some code.
        return null;
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        // Some code.
        return null;
    }

    IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()
    {
        Console.WriteLine("Dog");
        // Some code.
        return null;
    }
}
class Program
{
    public static void Test()
    {
        IEnumerable<Animal> pets = new Pets();
        pets.GetEnumerator();
    }
}
```

En este ejemplo no se especifica cómo elige el método `pets.GetEnumerator` entre `Cat` y `Dog`. Esto podría producir problemas en el código.

## <a name="see-also"></a>Vea también

- [Varianza en interfaces genéricas (C#)](./variance-in-generic-interfaces.md)
- [Usar varianza para los delegados genéricos Func y Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)
