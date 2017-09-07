---
title: "Utilizar operadores de conversión (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
caps.latest.revision: 20
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
ms.openlocfilehash: 2561b680da567623b8dab13e9e5294c3dd2c1012
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="using-conversion-operators-c-programming-guide"></a>Utilizar operadores de conversión (Guía de programación de C#)
Puede usar los operadores de conversión `implicit`, que son más fáciles de usar, o los operadores de conversión `explicit`, que indican claramente a cualquiera que lea el código que está convirtiendo un tipo. En este tema se muestran ambos tipos de operadores de conversión.  
  
> [!NOTE]
>  Para obtener información sobre las conversiones de tipo simple, vea [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) o <xref:System.Convert>.  
  
## <a name="example"></a>Ejemplo  
 Este es un ejemplo de un operador de conversión explícita. Este operador convierte el tipo <xref:System.Byte> en un tipo de valor denominado `Digit`. Como no todos los bytes se pueden convertir en valores de tipo digit, la conversión es explícita, lo que significa que se debe usar una conversión, como se muestra en el método `Main`.  
  
 [!code-cs[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra un operador de conversión implícita mediante la definición de un operador de conversión que deshace lo que hizo el ejemplo anterior: convierte una clase de valor denominada `Digit` en el tipo entero <xref:System.Byte>. Dado que cualquier dígito se puede convertir en <xref:System.Byte>, no hay ninguna necesidad de obligar a los usuarios a que definan explícitamente la conversión.  
  
 [!code-cs[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [is](../../../csharp/language-reference/keywords/is.md)

