---
title: 'Utilizar operadores de conversión: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 908067c3ad6cae34dd223bd608a74ba1cd7a88a3
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236875"
---
# <a name="using-conversion-operators-c-programming-guide"></a>Utilizar operadores de conversión (Guía de programación de C#)
Puede usar los operadores de conversión `implicit`, que son más fáciles de usar, o los operadores de conversión `explicit`, que indican claramente a cualquiera que lea el código que está convirtiendo un tipo. En este tema se muestran ambos tipos de operadores de conversión.  
  
> [!NOTE]
>  Para obtener información sobre las conversiones de tipos simples, consulte [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), o bien <xref:System.Convert>.  
  
## <a name="example"></a>Ejemplo  
 Este es un ejemplo de un operador de conversión explícita. Este operador convierte el tipo <xref:System.Byte> en un tipo de valor denominado `Digit`. Como no todos los bytes se pueden convertir en valores de tipo digit, la conversión es explícita, lo que significa que se debe usar una conversión, como se muestra en el método `Main`.  
  
 [!code-csharp[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra un operador de conversión implícita mediante la definición de un operador de conversión que deshace lo que hizo el ejemplo anterior: convierte una clase de valor denominada `Digit` en el tipo entero <xref:System.Byte>. Dado que cualquier dígito se puede convertir en <xref:System.Byte>, no hay ninguna necesidad de obligar a los usuarios a que definan explícitamente la conversión.  
  
 [!code-csharp[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
- [is](../../../csharp/language-reference/keywords/is.md)
