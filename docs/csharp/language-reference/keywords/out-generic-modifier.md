---
title: "out (Modificador genérico) (Referencia de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
caps.latest.revision: 15
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a5b488eab5966a556b3e3c91ae8c748d11e61367
ms.lasthandoff: 03/13/2017

---
# <a name="out-generic-modifier-c-reference"></a>out (Modificador genérico) (Referencia de C#)
Para los parámetros de tipo genérico, la palabra clave `out` especifica que el parámetro de tipo es covariante. Puede usar la palabra clave `out` en las interfaces y delegados genéricos.  
  
 La covarianza le permite usar un tipo más derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado. La covarianza y la contravarianza son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.  
  
 Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo. Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerabe(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.  
  
 A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.  
  
 Para obtener más información, vea [Covarianza y contravarianza](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante. También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.  
  
 [!code-cs[csVarianceKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_1.cs)]  
  
 En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:  
  
-   El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.  
  
    > [!NOTE]
    >  Hay una excepción para esta regla. Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado. Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca) y [Usar la varianza para los delegados genéricos Func y Action](http://msdn.microsoft.com/library/e69c4f39-09aa-4c6d-a752-08cc767d8290).  
  
-   El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante. También se muestra cómo convertir implícitamente los tipos de delegado.  
  
 [!code-cs[csVarianceKeywords#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-generic-modifier_2.cs)]  
  
 En un delegado genérico, un tipo se puede declarar como covariante si se usa solamente como tipo de valor devuelto por un método y no se usa para los argumentos de método.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Varianza en interfaces genéricas](http://msdn.microsoft.com/library/e14322da-1db3-42f2-9a67-397daddd6b6a)   
 [in (Modificador genérico)](../../../csharp/language-reference/keywords/in-generic-modifier.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)
