---
title: out (Modificador genérico) (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: 95ccbe3ab5bf2d326e1154af0b169972a24f7e38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269619"
---
# <a name="out-generic-modifier-c-reference"></a>out (Modificador genérico) (Referencia de C#)
Para los parámetros de tipo genérico, la palabra clave `out` especifica que el parámetro de tipo es covariante. Puede usar la palabra clave `out` en las interfaces y delegados genéricos.  
  
 La covarianza le permite usar un tipo más derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado. La covarianza y la contravarianza son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.  
  
 Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo. Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerable(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.  
  
 A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.  
  
 Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante. También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.  
  
 [!code-csharp[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]  
  
 En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:  
  
-   El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.  
  
    > [!NOTE]
    >  Hay una excepción para esta regla. Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado. Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [Usar la varianza para los delegados genéricos Func y Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
-   El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante. También se muestra cómo convertir implícitamente los tipos de delegado.  
  
 [!code-csharp[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]  
  
 En un delegado genérico, un tipo se puede declarar como covariante si se usa solamente como tipo de valor devuelto por un método y no se usa para los argumentos de método.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [in](../../../csharp/language-reference/keywords/in-generic-modifier.md)  
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)
