---
title: In (Modificador genérico) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: d8d503f0814a89c977cdc208eced026b2d8cb1fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802478"
---
# <a name="in-generic-modifier-visual-basic"></a>In (Modificador genérico) (Visual Basic)
Para los parámetros de tipo genérico, la palabra clave `In` especifica que el parámetro de tipo es contravariante.  
  
## <a name="remarks"></a>Comentarios  
 La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.  
  
 Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="rules"></a>Reglas  
 Puede usar la palabra clave `In` en las interfaces y delegados genéricos.  
  
 Un parámetro de tipo se puede declarar contravariante en una interfaz o delegado genéricos si se usa solamente como un tipo de argumentos de método y no se usa como un tipo de valor devuelto del método. `ByRef` parámetros no pueden ser covariantes o contravariantes.  
  
 Covarianza y contravarianza son compatibles con tipos de referencia y no se admite para tipos de valor.  
  
 En Visual Basic, no puede declarar eventos en interfaces contravariantes sin especificar el tipo de delegado. Además, una interfaz contravariante no puede tener anidadas clases, enumeraciones o estructuras, pero puede haber interfaces anidadas.  
  
## <a name="behavior"></a>Comportamiento  
 Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz. Por ejemplo, dado que en la interfaz <xref:System.Collections.Generic.IComparer%601> de .NET Framework 4 el tipo T es contravariante, puede asignar un objeto de tipo `IComparer(Of Person)` a un objeto de tipo `IComparer(Of Employee)` sin tener que usar ningún método de conversión especial si `Person` hereda `Employee`.  
  
 A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante. También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.  
  
 [!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este. También se muestra cómo puede convertir implícitamente un tipo de delegado.  
  
 [!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
