---
title: 'Instrucción return: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 058dc1d51099196559bee4ec2b96dc883e813f93
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236564"
---
# <a name="return-c-reference"></a>return (Referencia de C#)

La instrucción `return` termina la ejecución del método en el que aparece y devuelve el control al método de llamada. También puede devolver un valor opcional. Si el método es del tipo `void`, la instrucción `return` se puede omitir.

 Si la instrucción return está incluida en un bloque `try`, el bloque `finally`, si existe, se ejecutará antes de que el control se devuelva al método de llamada.

## <a name="example"></a>Ejemplo

 En el siguiente ejemplo, el método `CalculateArea()` devuelve la variable local `area` como un valor de tipo [double](double.md).

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [return (instrucción)](/cpp/cpp/return-statement-cpp)
- [Instrucciones de salto](jump-statements.md)
