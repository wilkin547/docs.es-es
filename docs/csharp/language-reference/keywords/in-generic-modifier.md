---
title: in (Modificador genérico) (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: 003ce26fe9ba315eefc748a406754026231004b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267009"
---
# <a name="in-generic-modifier-c-reference"></a>in (Modificador genérico) (Referencia de C#)

Para los parámetros de tipo genérico, la palabra clave `in` especifica que el parámetro de tipo es contravariante. Puede usar la palabra clave `in` en las interfaces y delegados genéricos.  
  
 La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado. La covarianza y la contravarianza de los parámetros de tipo genérico son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.  
  
 Un tipo se puede declarar contravariante en una interfaz o un delgado genéricos solo si define el tipo de parámetros de un método y no el tipo de valor devuelto de un método. Los parámetros `In`, `ref` y `out` deben ser invariables, es decir, ni covariantes ni contravariantes.
  
 Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz. Por ejemplo, en la interfaz <xref:System.Collections.Generic.IComparer%601>, el tipo T es contravariante, puede asignar un objeto de tipo `IComparer<Person>` a un objeto de tipo `IComparer<Employee>` sin tener que usar ningún método de conversión especial si `Employee` hereda `Person`.  
  
 A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.  
  
 Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="contravariant-generic-interface"></a>Interfaz genérica contravariante   

 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante. También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.  
  
 [!code-csharp[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="contravariant-generic-delegate"></a>Delegado genérico contravariante  

 En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este. También se muestra cómo puede convertir implícitamente un tipo de delegado.  
  
 [!code-csharp[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)  
 [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)  
