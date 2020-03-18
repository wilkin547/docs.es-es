---
title: 'Comparaciones de igualdad: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- object equality [C#]
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
ms.openlocfilehash: f09d9891f79eda44c428d5509e341a54ad3a3eee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157109"
---
# <a name="equality-comparisons-c-programming-guide"></a>Comparaciones de igualdad (guía de programación de C#)

A veces es necesario comparar si dos valores son iguales. En algunos casos, se prueba la *igualdad de valores*, también denominada *equivalencia*, lo que significa que los valores contenidos en las dos variables son iguales. En otros casos, hay que determinar si dos variables hacen referencia al mismo objeto subyacente de la memoria. Este tipo de igualdad se denomina *igualdad de referencia* o *identidad*. En este tema se describen estos dos tipos de igualdad y se proporcionan vínculos a otros temas para obtener más información.  
  
## <a name="reference-equality"></a>Igualdad de referencia

 La igualdad de referencia significa que dos referencias de objeto hacen referencia al mismo objeto subyacente. Esto puede suceder mediante una asignación simple, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideStatements#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#18)]  
  
 En este código, se crean dos objetos, pero después de la instrucción de asignación, ambas referencias hacen referencia al mismo objeto. Por consiguiente, presentan igualdad de referencia. Use el método <xref:System.Object.ReferenceEquals%2A> para determinar si dos referencias hacen referencia al mismo objeto.  
  
El concepto de igualdad de la referencia solo se aplica a los tipos de referencia. Los objetos de tipo de valor no pueden presentar igualdad de referencia porque al asignar una instancia de un tipo de valor a una variable, se realiza una copia del valor. Por consiguiente, nunca puede haber dos structs con conversión unboxing que hagan referencia a la misma ubicación de la memoria. Además, si se usa <xref:System.Object.ReferenceEquals%2A> para comparar dos tipos de valor, el resultado siempre será `false`, aunque todos los valores que contengan los objetos sean idénticos. Esto se debe a que a cada variable se aplica la conversión boxing en una instancia de objeto independiente. Para más información, consulte [Procedimiento Probar la igualdad de referencia (Identidad)](./how-to-test-for-reference-equality-identity.md).

## <a name="value-equality"></a>Igualdad de valores

 La igualdad de valores significa que dos objetos contienen el mismo valor o valores. Para los tipos de valor primitivos, como [int](../../language-reference/builtin-types/integral-numeric-types.md) o [bool](../../language-reference/builtin-types/bool.md), las pruebas de igualdad de valores son sencillas. Puede usar el operador [==](../../language-reference/operators/equality-operators.md#equality-operator-), como se muestra en el ejemplo siguiente.  
  
```csharp  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.
if (b == a)
{  
    // The two integers are equal.  
}  
```  
  
 Para la mayoría de los otros tipos, las pruebas de igualdad de valores son más complejas, porque es preciso entender cómo la define el tipo. Para las clases y los structs que tienen varios campos o propiedades, la igualdad de valores suele definirse de modo que significa que todos los campos o propiedades tienen el mismo valor. Por ejemplo, podrían definirse dos objetos `Point` que fueran equivalentes si pointA.X es igual a pointB.X y pointA.Y es igual a pointB.Y.  
  
En cambio, no hay ningún requisito que exija que la equivalencia se base en todos los campos de un tipo. Se puede basar en un subconjunto. Al comparar tipos que no sean de su propiedad, es importante asegurarse concretamente de cómo se define la equivalencia para ese tipo. Para más información sobre cómo definir la igualdad de valores en sus propias clases y structs, consulte [Procedimiento Definir la igualdad de valores para un tipo](./how-to-define-value-equality-for-a-type.md).
  
### <a name="value-equality-for-floating-point-values"></a>Igualdad de valores en valores de número de punto flotante

 Las comparaciones de igualdad de valores de punto flotante ([double](../../language-reference/builtin-types/floating-point-numeric-types.md) y [float](../../language-reference/builtin-types/floating-point-numeric-types.md)) son problemáticas debido a la imprecisión de la aritmética de número de punto flotante en los equipos binarios. Para obtener más información, vea los comentarios en el tema <xref:System.Double?displayProperty=nameWithType>.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Description|  
|-----------|-----------------|  
|[Procedimiento Probar la igualdad de referencia (Identidad)](./how-to-test-for-reference-equality-identity.md)|Describe cómo determinar si dos variables presentan igualdad de referencia.|  
|[Procedimiento Definir la igualdad de valores para un tipo](./how-to-define-value-equality-for-a-type.md)|Describe cómo proporcionar una definición personalizada de igualdad de valores para un tipo.|  
|[Guía de programación de C#](../index.md)|Proporciona vínculos a información detallada sobre importantes características del lenguaje C# y características que están disponibles para C# a través de .NET Framework.|  
|[Tipos](../types/index.md)|Proporciona información sobre el sistema de tipos de C# y vínculos a información adicional.|  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
