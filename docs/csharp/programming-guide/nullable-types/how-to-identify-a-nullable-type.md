---
title: 'Cómo: Identificar tipos que aceptan valores NULL (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: f3ac4ebd77fc92a133eb326919d5ba55264ced97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a>Cómo: Identificar tipos que aceptan valores NULL (Guía de programación de C#)
Puede usar el operador [typeof](../../../csharp/language-reference/keywords/typeof.md) de C# para crear un objeto <xref:System.Type> que represente un tipo que acepta valores NULL:  
  
```  
System.Type type = typeof(int?);  
```  
  
 También puede usar las clases y métodos del espacio de nombres <xref:System.Reflection> para generar objetos <xref:System.Type> que representen tipos que aceptan valores NULL. En cambio, si intenta obtener información de tipo de las variables que aceptan valores NULL en tiempo de ejecución mediante el método <xref:System.Object.GetType%2A> o el operador `is`, el resultado será un objeto <xref:System.Type> que representa el tipo subyacente y no el propio tipo que acepta valores NULL.  
  
 La llamada a `GetType` en un tipo que acepta valores NULL origina que se ejecute una operación de conversión boxing cuando el tipo se convierte implícitamente en <xref:System.Object>. Por consiguiente, <xref:System.Object.GetType%2A> siempre devuelve un objeto <xref:System.Type> que representa el tipo subyacente y no el tipo que acepta valores NULL.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 El operador [is](../../../csharp/language-reference/keywords/is.md) de C# funciona también en el tipo subyacente de un tipo que acepta valores NULL. Por tanto, no puede usar `is` para determinar si una variable es un tipo que acepta valores NULL. En el ejemplo siguiente se muestra que el operador `is` trata una variable \<int> que acepta valores NULL como un valor int.  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a>Ejemplo  
 Use el código siguiente para determinar si un objeto <xref:System.Type> representa un tipo que acepta valores NULL. Recuerde que este código siempre devuelve false si el objeto `Type` se devuelve de una llamada a <xref:System.Object.GetType%2A>, como se ha explicado anteriormente en este mismo tema.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a>Vea también  
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)  
 [Aplicar la conversión boxing a tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)
