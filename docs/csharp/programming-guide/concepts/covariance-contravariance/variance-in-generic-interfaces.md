---
title: Varianza en interfaces genéricas (C#)
ms.date: 06/06/2019
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: ea5d3d35bc9ee438263707efd16829b6217a1968
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241336"
---
# <a name="variance-in-generic-interfaces-c"></a>Varianza en interfaces genéricas (C#)

En .NET Framework 4 se ha presentado la compatibilidad con la varianza para varias interfaces genéricas existentes. La compatibilidad con la varianza permite la conversión implícita de clases que implementan estas interfaces.

A partir de .NET Framework 4, las siguientes interfaces son variantes:

- <xref:System.Collections.Generic.IEnumerable%601> (T es covariante)

- <xref:System.Collections.Generic.IEnumerator%601> (T es covariante)

- <xref:System.Linq.IQueryable%601> (T es covariante)

- <xref:System.Linq.IGrouping%602> (`TKey` y `TElement` son covariantes)

- <xref:System.Collections.Generic.IComparer%601> (T es contravariante)

- <xref:System.Collections.Generic.IEqualityComparer%601> (T es contravariante)

- <xref:System.IComparable%601> (T es contravariante)

A partir de .NET Framework 4.5, las siguientes interfaces son variantes:

- <xref:System.Collections.Generic.IReadOnlyList%601> (T es covariante)

- <xref:System.Collections.Generic.IReadOnlyCollection%601> (T es covariante)

La covarianza permite que un método tenga un tipo de valor devuelto más derivado que los que se definen en los parámetros de tipo genérico de la interfaz. Para ilustrar la característica de la covarianza, considere estas interfaces genéricas: `IEnumerable<Object>` y `IEnumerable<String>`. La interfaz `IEnumerable<String>` no hereda la interfaz `IEnumerable<Object>`. En cambio, el tipo `String` hereda el tipo `Object`, y en algunos casos puede que quiera asignar objetos de estas interfaces entre sí. Esto se muestra en el ejemplo de código siguiente.

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

En versiones anteriores de .NET Framework, este código provoca un error de compilación en C# y, si `Option Strict` está activado, en Visual Basic. Pero ahora puede usar `strings` en lugar de `objects`, como se muestra en el ejemplo anterior, porque la interfaz <xref:System.Collections.Generic.IEnumerable%601> es covariante.

La contravarianza permite que un método tenga tipos de argumento menos derivados que los que se especifican en el parámetro genérico de la interfaz. Para ilustrar la contravarianza, se presupone que ha creado una clase `BaseComparer` para comparar instancias de la clase `BaseClass`. La clase `BaseComparer` implementa la interfaz `IEqualityComparer<BaseClass>`. Como la interfaz <xref:System.Collections.Generic.IEqualityComparer%601> ahora es contravariante, puede usar `BaseComparer` para comparar instancias de clases que heredan la clase `BaseClass`. Esto se muestra en el ejemplo de código siguiente.

```csharp
// Simple hierarchy of classes.
class BaseClass { }
class DerivedClass : BaseClass { }

// Comparer class.
class BaseComparer : IEqualityComparer<BaseClass>
{
    public int GetHashCode(BaseClass baseInstance)
    {
        return baseInstance.GetHashCode();
    }
    public bool Equals(BaseClass x, BaseClass y)
    {
        return x == y;
    }
}
class Program
{
    static void Test()
    {
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();

        // Implicit conversion of IEqualityComparer<BaseClass> to
        // IEqualityComparer<DerivedClass>.
        IEqualityComparer<DerivedClass> childComparer = baseComparer;
    }
}
```

Para obtener más ejemplos, vea [Usar la varianza en interfaces para las colecciones genéricas (C#)](./using-variance-in-interfaces-for-generic-collections.md).

La varianza para interfaces genéricas solo es compatible con tipos de referencia. Los tipos de valor no admiten la varianza. Por ejemplo, `IEnumerable<int>` no puede convertirse implícitamente en `IEnumerable<object>`, porque los enteros se representan mediante un tipo de valor.

```csharp
IEnumerable<int> integers = new List<int>();
// The following statement generates a compiler error,
// because int is a value type.
// IEnumerable<Object> objects = integers;
```

También es importante recordar que las clases que implementan las interfaces variantes siguen siendo invariables. Por ejemplo, aunque <xref:System.Collections.Generic.List%601> implementa la interfaz covariante <xref:System.Collections.Generic.IEnumerable%601>, no puede convertir `List<String>` en `List<Object>` implícitamente. Esto se muestra en el siguiente código de ejemplo.

```csharp
// The following line generates a compiler error
// because classes are invariant.
// List<Object> list = new List<String>();

// You can use the interface object instead.
IEnumerable<Object> listObjects = new List<String>();
```

## <a name="see-also"></a>Vea también

- [Usar la varianza en interfaces para las colecciones genéricas (C#)](./using-variance-in-interfaces-for-generic-collections.md)
- [Crear interfaces genéricas variantes (C#)](./creating-variant-generic-interfaces.md)
- [Interfaces genéricas](../../../../standard/generics/interfaces.md)
- [Varianza en delegados (C#)](./variance-in-delegates.md)
