---
title: 'Cómo: Implementar conversiones definidas por el usuario entre structs (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: cff85d60c1b59f4d1ca028f8fc02fee5728fa3d6
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45583072"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>Cómo: Implementar conversiones definidas por el usuario entre structs (Guía de programación de C#)
Este ejemplo define dos structs, `RomanNumeral` y `BinaryNumeral`, y muestra conversiones entre ellos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a>Programación sólida  
  
-   En el ejemplo anterior, la instrucción:  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     realiza una conversión de `RomanNumeral` a `BinaryNumeral`. Como no existe una conversión directa de `RomanNumeral` a `BinaryNumeral`, se usa una conversión explícita de un `RomanNumeral` a un `int`, y otra conversión explícita para convertir de un `int` a un `BinaryNumeral`.  
  
-   Además la instrucción  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     realiza una conversión de `BinaryNumeral` a `RomanNumeral`. Como `RomanNumeral` define una conversión implícita desde `BinaryNumeral`, no se requiere ninguna conversión explícita.  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
