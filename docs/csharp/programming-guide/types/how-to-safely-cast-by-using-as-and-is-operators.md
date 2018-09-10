---
title: 'Cómo: Realizar conversiones seguras usando los operadores is y as (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
ms.openlocfilehash: 8e0b17122bd23a7de82ca1c210a559fe09ad7fee
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508123"
---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a>Cómo: Realizar conversiones seguras usando los operadores is y as (Guía de programación de C#)
Dado que los objetos son polimórficos, es posible que una variable de un tipo de clase base contenga un tipo derivado. Para acceder a los métodos de la instancia del tipo derivado, es necesario volver a convertir el valor al tipo derivado. En cambio, el intento de realizar una conversión de tipos sencilla en estos casos conlleva el riesgo de producir una excepción <xref:System.InvalidCastException>. Por esa razón, C# proporciona los operadores [is](../../../csharp/language-reference/keywords/is.md) y [as](../../../csharp/language-reference/keywords/as.md). Puede usar estos operadores para comprobar si una conversión de tipo se realizará correctamente sin hacer que se produzca una excepción. En general, el operador `as` suele ser más eficaz, ya que devuelve el valor de la conversión de tipo si esta puede realizarse correctamente. El operador `is` devuelve solamente un valor Boolean. Así, puede usarse cuando simplemente quiera determinar el tipo de un objeto pero no tenga que realizar una conversión de tipo del mismo.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes se muestra cómo usar los operadores `is` y `as` para realizar una conversión de un tipo de referencia a otro sin el riesgo de que se produzca una excepción. En el ejemplo también se muestra cómo usar el operador `as` con tipos de valor que aceptan valores NULL.  
  
 [!code-csharp[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Tipos](../../../csharp/programming-guide/types/index.md)  
- [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
- [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)
