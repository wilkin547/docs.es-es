---
title: Varianza en delegados (C#)
ms.date: 07/20/2015
ms.assetid: 19de89d2-8224-4406-8964-2965b732b890
ms.openlocfilehash: 7370813179040f54e65adf3b568a1fd914223f1d
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990038"
---
# <a name="variance-in-delegates-c"></a>Varianza en delegados (C#)
En .NET Framework 3.5 se presentó por primera vez la compatibilidad con la varianza para hacer coincidir firmas de método con tipos de delegados en todos los delegados en C#. Esto significa que puede asignar a los delegados no solo métodos con firmas coincidentes, sino métodos que devuelven tipos más derivados (covarianza) o que aceptan parámetros con tipos menos derivados (contravarianza) que el especificado por el tipo de delegado. Esto incluye delegados genéricos y no genéricos.  
  
 Por ejemplo, consideremos el siguiente código, que tiene dos clases y dos delegados: genéricos y no genéricos.  
  
```csharp  
public class First { }  
public class Second : First { }  
public delegate First SampleDelegate(Second a);  
public delegate R SampleGenericDelegate<A, R>(A a);  
```  
  
 Al crear delegados de los tipos `SampleDelegate` o `SampleGenericDelegate<A, R>`, puede asignar uno de los métodos siguientes a dichos delegados.  
  
```csharp  
// Matching signature.  
public static First ASecondRFirst(Second second)  
{ return new First(); }  
  
// The return type is more derived.  
public static Second ASecondRSecond(Second second)  
{ return new Second(); }  
  
// The argument type is less derived.  
public static First AFirstRFirst(First first)  
{ return new First(); }  
  
// The return type is more derived
// and the argument type is less derived.  
public static Second AFirstRSecond(First first)  
{ return new Second(); }  
```  
  
 En el ejemplo de código siguiente se ilustra la conversión implícita entre la firma del método y el tipo de delegado.  
  
```csharp  
// Assigning a method with a matching signature
// to a non-generic delegate. No conversion is necessary.  
SampleDelegate dNonGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type
// and less derived argument type to a non-generic delegate.  
// The implicit conversion is used.  
SampleDelegate dNonGenericConversion = AFirstRSecond;  
  
// Assigning a method with a matching signature to a generic delegate.  
// No conversion is necessary.  
SampleGenericDelegate<Second, First> dGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type
// and less derived argument type to a generic delegate.  
// The implicit conversion is used.  
SampleGenericDelegate<Second, First> dGenericConversion = AFirstRSecond;  
```  
  
 Para obtener más ejemplos, vea [Usar varianza en delegados (C#)](./using-variance-in-delegates.md) y [Usar la varianza para los delegados genéricos Func y Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).  
  
## <a name="variance-in-generic-type-parameters"></a>Varianza en parámetros de tipo genérico  
 En .NET Framework 4 o posterior puede habilitar la conversión implícita entre los delegados, de modo que los delegados genéricos con tipos diferentes especificados por parámetros de tipo genérico se puedan asignar entre sí, en el caso de que los tipos se hereden entre sí, como requiere la varianza.  
  
 Para habilitar la conversión implícita, debe declarar explícitamente parámetros genéricos en un delegado como covariante o contravariante mediante la palabra clave `in` o `out`.  
  
 En el ejemplo de código siguiente se muestra cómo se crea un delegado que tiene un parámetro de tipo genérico covariante.  
  
```csharp  
// Type T is declared covariant by using the out keyword.  
public delegate T SampleGenericDelegate <out T>();  
  
public static void Test()  
{  
    SampleGenericDelegate <String> dString = () => " ";  
  
    // You can assign delegates to each other,  
    // because the type T is declared covariant.  
    SampleGenericDelegate <Object> dObject = dString;
}  
```  
  
 Si usa solo la compatibilidad con la varianza para hacer coincidir firmas de método con tipos de delegados y no usa las palabras clave `in` y `out`, es posible que en algunas ocasiones pueda crear instancias de delegados con métodos o expresiones lambda idénticos, pero no pueda asignar un delegado a otro.  
  
 En el ejemplo de código siguiente, `SampleGenericDelegate<String>` no se puede convertir explícitamente a `SampleGenericDelegate<Object>`, aunque `String` hereda `Object`. Para solucionar este problema, marque el parámetro genérico `T` con la palabra clave `out`.  
  
```csharp  
public delegate T SampleGenericDelegate<T>();  
  
public static void Test()  
{  
    SampleGenericDelegate<String> dString = () => " ";  
  
    // You can assign the dObject delegate  
    // to the same lambda expression as dString delegate  
    // because of the variance support for
    // matching method signatures with delegate types.  
    SampleGenericDelegate<Object> dObject = () => " ";  
  
    // The following statement generates a compiler error  
    // because the generic type T is not marked as covariant.  
    // SampleGenericDelegate <Object> dObject = dString;  
  
}  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-net"></a>Delegados genéricos con parámetros de tipo variante en .NET

En .NET Framework 4 se presentó por primera vez la compatibilidad con la varianza para los parámetros de tipo genérico en varios delegados genéricos existentes:  
  
- `Action` delega del espacio de nombres <xref:System>, por ejemplo, <xref:System.Action%601> y <xref:System.Action%602>  
  
- `Func` delega del espacio de nombres <xref:System>, por ejemplo, <xref:System.Func%601> y <xref:System.Func%602>  
  
- Delegado <xref:System.Predicate%601>.  
  
- Delegado <xref:System.Comparison%601>.  
  
- Delegado <xref:System.Converter%602>.  
  
 Para obtener más información y ejemplos, vea [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md) (Usar varianza para delegados genéricos Func y Action (C#)).  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Declarar parámetros de tipo variante en delegados genéricos  
 Si un delegado genérico tiene parámetros de tipo genérico covariante o contravariante, se puede hacer referencia a él como un *delegado genérico variante*.  
  
 Puede declarar un parámetro de tipo genérico covariante en un delegado genérico mediante la palabra clave `out`. El tipo covariante puede usarse solo como un tipo de valor devuelto de método, y no como un tipo de argumentos de método. En el siguiente ejemplo de código se muestra cómo declarar un delegado genérico covariante.  
  
```csharp  
public delegate R DCovariant<out R>();  
```  
  
 Puede declarar un parámetro de tipo genérico contravariante en un delegado genérico mediante la palabra clave `in`. El tipo contravariante puede usarse solo como un tipo de argumentos de método, y no como un tipo de valor devuelto de método. En el siguiente ejemplo de código se muestra cómo declarar un delegado genérico contravariante.  
  
```csharp  
public delegate void DContravariant<in A>(A a);  
```  
  
> [!IMPORTANT]
> Los parámetros `ref`, `in` y `out` de C# no se pueden marcar como variantes.  
  
 También es posible admitir la varianza y la covarianza en el mismo delegado, pero para parámetros de tipo diferentes. Esta implementación se muestra en el ejemplo siguiente.  
  
```csharp  
public delegate R DVariant<in A, out R>(A a);  
```  
  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Crear instancias de delegados genéricos variantes e invocarlos  
 Puede crear instancias de delegados variantes e invocarlos del mismo modo que crea instancias de delegados invariables y los invoca. En el ejemplo siguiente, se crea una instancia del delegado mediante una expresión lambda.  
  
```csharp  
DVariant<String, String> dvariant = (String str) => str + " ";  
dvariant("test");  
```  
  
### <a name="combining-variant-generic-delegates"></a>Combinar delegados genéricos variantes  

No combine delegados variantes. El método <xref:System.Delegate.Combine%2A> no admite la conversión de delegados variantes y espera que los delegados sean exactamente del mismo tipo. Esto puede provocar una excepción en tiempo de ejecución cuando se combinan delegados mediante el método <xref:System.Delegate.Combine%2A> o mediante el operador `+`, como se muestra en el ejemplo de código siguiente.  
  
```csharp  
Action<object> actObj = x => Console.WriteLine("object: {0}", x);  
Action<string> actStr = x => Console.WriteLine("string: {0}", x);  
// All of the following statements throw exceptions at run time.  
// Action<string> actCombine = actStr + actObj;  
// actStr += actObj;  
// Delegate.Combine(actStr, actObj);  
```  
  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Varianza en parámetros de tipo genérico para los tipos de referencia y valor  
 La varianza para parámetros de tipo genérico solo es compatible con tipos de referencia. Por ejemplo, `DVariant<int>` no se puede convertir implícitamente en `DVariant<Object>` o `DVariant<long>`, porque un entero es un tipo de valor.  
  
 En el ejemplo siguiente se muestra que la varianza en parámetros de tipo genérico no se admite para tipos de valor.  
  
```csharp  
// The type T is covariant.  
public delegate T DVariant<out T>();  
  
// The type T is invariant.  
public delegate T DInvariant<T>();  
  
public static void Test()  
{  
    int i = 0;  
    DInvariant<int> dInt = () => i;  
    DVariant<int> dVariantInt = () => i;  
  
    // All of the following statements generate a compiler error  
    // because type variance in generic parameters is not supported  
    // for value types, even if generic type parameters are declared variant.  
    // DInvariant<Object> dObject = dInt;  
    // DInvariant<long> dLong = dInt;  
    // DVariant<Object> dVariantObject = dVariantInt;  
    // DVariant<long> dVariantLong = dVariantInt;
}  
```  
  
## <a name="see-also"></a>Vea también

- [Genéricos](../../../../standard/generics/index.md)
- [Usar varianza para los delegados genéricos Func y Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)
- [Procedimiento para combinar delegados (delegados de multidifusión)](../../delegates/how-to-combine-delegates-multicast-delegates.md)
