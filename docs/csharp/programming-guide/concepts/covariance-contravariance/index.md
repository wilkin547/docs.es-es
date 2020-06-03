---
title: Covarianza y contravarianza (C#)
ms.date: 07/20/2015
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
ms.openlocfilehash: 23633675059b9c295dda7ddf3d78754c0223f5f8
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241375"
---
# <a name="covariance-and-contravariance-c"></a>Covarianza y contravarianza (C#)
En C#, la covarianza y la contravarianza habilitan la conversión de referencias implícita de tipos de matriz, tipos de delegado y argumentos de tipo genérico. La covarianza conserva la compatibilidad de asignaciones y la contravarianza la invierte.  
  
 El siguiente código muestra la diferencia entre la compatibilidad de asignaciones, la covarianza y la contravarianza.  
  
```csharp  
// Assignment compatibility.
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.
object obj = str;  
  
// Covariance.
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument
// is assigned to an object instantiated with a less derived type argument.
// Assignment compatibility is preserved.
IEnumerable<object> objects = strings;  
  
// Contravariance.
// Assume that the following method is in the class:
// static void SetObject(object o) { }
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument
// is assigned to an object instantiated with a more derived type argument.
// Assignment compatibility is reversed.
Action<string> actString = actObject;  
```  
  
 La covarianza de matrices permite la conversión implícita de una matriz de un tipo más derivado a una matriz de un tipo menos derivado. Pero esta operación no es segura, tal como se muestra en el ejemplo de código siguiente.  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 La compatibilidad de la covarianza y la contravarianza con grupos de métodos permite hacer coincidir firmas de método con tipos de delegado. Esto le permite asignar a los delegados no solo métodos con firmas coincidentes, sino métodos que devuelven tipos más derivados (covarianza) o que aceptan parámetros con tipos menos derivados (contravarianza) que el especificado por el tipo de delegado. Para obtener más información, vea [Varianza en delegados (C#)](./variance-in-delegates.md) y [Usar varianza en delegados (C#)](./using-variance-in-delegates.md).  
  
 En el ejemplo de código siguiente, se muestra la compatibilidad de covarianza y contravarianza con grupos de métodos.  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 En .NET Framework 4 o versiones posteriores, C# admite la covarianza y contravarianza en las interfaces genéricas y los delegados, y permite la conversión implícita de los parámetros de tipo genérico. Para obtener más información, vea [Varianza en interfaces genéricas (C#)](./variance-in-generic-interfaces.md) y [Varianza en delegados (C#)](./variance-in-delegates.md).  
  
 En el ejemplo de código siguiente, se muestra la conversión implícita de referencias para interfaces genéricas.  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 Un delegado o interfaz genéricos se denominan *variante* si sus parámetros genéricos se declaran como covariantes o contravariantes. C# le permite crear sus propias interfaces y delegados variantes. Para obtener más información, consulte [Crear interfaces genéricas variantes (C#)](./creating-variant-generic-interfaces.md) y [Varianza en delegados (C#)](./variance-in-delegates.md).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Varianza en interfaces genéricas (C#)](./variance-in-generic-interfaces.md)|Describe la covarianza y contravarianza en las interfaces genéricas y proporciona una lista de interfaces genéricas variantes en .NET Framework.|  
|[Crear interfaces genéricas variantes (C#)](./creating-variant-generic-interfaces.md)|Se muestra cómo crear interfaces variantes personalizadas.|  
|[Usar la varianza en interfaces para las colecciones genéricas (C#)](./using-variance-in-interfaces-for-generic-collections.md)|Se muestra cómo la compatibilidad de covarianza y contravarianza en las interfaces <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IComparable%601> puede ayudarle a volver a usar el código.|  
|[Varianza en delegados (C#)](./variance-in-delegates.md)|Se describe la covarianza y contravarianza en delegados genéricos y no genéricos y se proporciona una lista de delegados genéricos variantes en .NET Framework.|  
|[Usar varianza en delegados (C#)](./using-variance-in-delegates.md)|Se muestra cómo usar la compatibilidad de covarianza y contravarianza en los delegados no genéricos para que coincidan las firmas de método con los tipos de delegado.|  
|[Usar varianza para los delegados genéricos Func y Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)|Se muestra cómo la compatibilidad de covarianza y contravarianza en los delegados `Func` y `Action` puede ayudarle a volver a usar el código.|
