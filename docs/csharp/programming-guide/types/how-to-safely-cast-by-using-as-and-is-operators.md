---
title: "Cómo: Realizar conversiones seguras usando los operadores is y as (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c5daa8525f45c123dabb0f59dfd29385b9e50354
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a>Cómo: Realizar conversiones seguras usando los operadores is y as (Guía de programación de C#)
Dado que los objetos son polimórficos, es posible que una variable de un tipo de clase base contenga un tipo derivado. Para tener acceso al método del tipo derivado, es necesario volver a convertir el valor al tipo derivado. En cambio, el intento de realizar una conversión de tipos sencilla en estos casos conlleva el riesgo de producir una excepción <xref:System.InvalidCastException>. Por esa razón, C# proporciona los operadores [is](../../../csharp/language-reference/keywords/is.md) y [as](../../../csharp/language-reference/keywords/as.md). Puede usar estos operadores para comprobar si una conversión de tipo se realizará correctamente sin hacer que se produzca una excepción. En general, el operador `as` suele ser más eficaz, ya que devuelve el valor de la conversión de tipo si esta puede realizarse correctamente. El operador `is` devuelve solamente un valor Boolean. Así, puede usarse cuando simplemente quiera determinar el tipo de un objeto pero no tenga que realizar una conversión de tipo del mismo.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes se muestra cómo usar los operadores `is` y `as` para realizar una conversión de un tipo de referencia a otro sin el riesgo de que se produzca una excepción. En el ejemplo también se muestra cómo usar el operador `as` con tipos de valor que aceptan valores NULL.  
  
 [!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Types](../../../csharp/programming-guide/types/index.md)  (Tipos [Referencia de C#])  
 [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  (Conversiones de tipos [Guía de programación de C#])  
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)

