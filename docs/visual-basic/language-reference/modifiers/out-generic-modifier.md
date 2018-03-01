---
title: "Out (Modificador genérico) (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e54504cd65b78846af41692f39899140a6d99b5
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="out-generic-modifier-visual-basic"></a>Out (Modificador genérico) (Visual Basic)
Para los parámetros de tipo genérico, la `Out` palabra clave especifica que el tipo es covariante.  
  
## <a name="remarks"></a>Comentarios  
 La covarianza le permite usar un tipo más derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.  
  
 Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).  
  
## <a name="rules"></a>Reglas  
 Puede usar la palabra clave `Out` en las interfaces y delegados genéricos.  
  
 En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:  
  
-   El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.  
  
    > [!NOTE]
    >  Hay una excepción para esta regla. Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado. Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [Usar la varianza para los delegados genéricos Func y Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
-   El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.  
  
 En un delegado genérico, un parámetro de tipo se puede declarar covariante si se usa solo como un tipo de valor devuelto del método y no se usan para los argumentos de método.  
  
 La covarianza y la contravarianza son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.  
  
 En Visual Basic, no puede declarar eventos en las interfaces covariantes sin especificar el tipo de delegado. Además, no pueden tener anidadas interfaces covariantes clases, enumeraciones o estructuras, pero puede haber interfaces anidadas.  
  
## <a name="behavior"></a>Comportamiento  
 Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo. Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerabe(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.  
  
 A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante. También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante. También muestra cómo puede usar la conversión implícita de tipos de delegado.  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
