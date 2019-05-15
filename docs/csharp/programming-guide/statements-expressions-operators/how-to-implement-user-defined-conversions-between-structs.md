---
title: 'Procedimiento Implementar conversiones definidas por el usuario entre structs: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: f33d8791791543704c8a49a44167b94c0f0c86b8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608170"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>Procedimiento Implementar conversiones definidas por el usuario entre structs (Guía de programación de C#)
Este ejemplo define dos structs, `RomanNumeral` y `BinaryNumeral`, y muestra conversiones entre ellos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideStatements#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#13)]  
  
## <a name="robust-programming"></a>Programación sólida  
  
- En el ejemplo anterior, la instrucción:  
  
     [!code-csharp[csProgGuideStatements#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#14)]  
  
     realiza una conversión de `RomanNumeral` a `BinaryNumeral`. Como no existe una conversión directa de `RomanNumeral` a `BinaryNumeral`, se usa una conversión explícita de un `RomanNumeral` a un `int`, y otra conversión explícita para convertir de un `int` a un `BinaryNumeral`.  
  
- Además la instrucción  
  
     [!code-csharp[csProgGuideStatements#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#15)]  
  
     realiza una conversión de `BinaryNumeral` a `RomanNumeral`. Como `RomanNumeral` define una conversión implícita desde `BinaryNumeral`, no se requiere ninguna conversión explícita.  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
