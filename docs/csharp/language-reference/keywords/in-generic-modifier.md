---
title: "in (Modificador genérico) (Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: 663fa75a7e214ed97efb45dda2c9ac298559653d
ms.contentlocale: es-es
ms.lasthandoff: 08/11/2017

---
# <a name="in-generic-modifier-c-reference"></a>in (Modificador genérico) (Referencia de C#)
Para los parámetros de tipo genérico, la palabra clave `in` especifica que el parámetro de tipo es contravariante. Puede usar la palabra clave `in` en las interfaces y delegados genéricos.  
  
 La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado. La covarianza y la contravarianza de los parámetros de tipo genérico son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.  
  
 Un tipo se puede declarar contravariante en una interfaz o delegado genéricos si solo se usa como tipo de argumentos de método y no se usa como tipo de un valor devuelto de un método. Los parámetros `Ref` y `out` no pueden ser variantes.  
  
 Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz. Por ejemplo, dado que en la interfaz <xref:System.Collections.Generic.IComparer%601> de .NET Framework 4 el tipo T es contravariante, puede asignar un objeto de tipo `IComparer(Of Person)` a un objeto de tipo `IComparer(Of Employee)` sin tener que usar ningún método de conversión especial si `Employee` hereda `Person`.  
  
 A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.  
  
 Para obtener más información, vea [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md) (Covarianza y contravarianza).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante. También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.  
  
 [!code-cs[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este. También se muestra cómo puede convertir implícitamente un tipo de delegado.  
  
 [!code-cs[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [out](../../../csharp/language-reference/keywords/out-generic-modifier.md)   
 [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md)  (Covarianza y contravarianza)  
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)

