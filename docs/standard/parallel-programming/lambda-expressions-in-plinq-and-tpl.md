---
title: Expresiones lambda en PLINQ y TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
ms.openlocfilehash: 4e5be295a52edc1a7f0a0a3aa98f55335ae3e31b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453005"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a>Expresiones lambda en PLINQ y TPL

La biblioteca TPL contiene muchos métodos que adoptan una de las familias <xref:System.Func%601?displayProperty=nameWithType> o <xref:System.Action?displayProperty=nameWithType> de delegados como parámetros de entrada. Puede usar estos delegados para pasar de la lógica personalizada del programa al bucle, tarea o consulta en paralelo. Los ejemplos de código de TPL, igual que igual que de PLINQ, usan expresiones lambda para crear instancias de esos delegados como bloques de código insertados. En este tema se proporciona una breve introducción a Func y Action, y muestra cómo usar las expresiones lambda en la biblioteca TPL y PLINQ.

> [!NOTE]
> Para más información sobre los delegados en general, vea [Delegados](../../csharp/programming-guide/delegates/index.md) y [Delegados](../../visual-basic/programming-guide/language-features/delegates/index.md). Para obtener más información sobre las expresiones lambda en C# y Visual Basic, vea [Expresiones lambda](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) y [Expresiones lambda](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="func-delegate"></a>Func (delegado)

Un delegado `Func` encapsula un método que devuelve un valor. En una signatura `Func`, el último parámetro de tipo o el ubicado más a la derecha siempre especifica el tipo de devolución. Una causa común de los errores de compilador es intentar pasar dos parámetros de entrada a un <xref:System.Func%602?displayProperty=nameWithType>; de hecho, este tipo solo acepta un parámetro de entrada. .NET define 17 versiones de `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, etc. hasta <xref:System.Func%6017?displayProperty=nameWithType>.

## <a name="action-delegate"></a>Action (delegado)

Un delegado <xref:System.Action?displayProperty=nameWithType> encapsula un método (Sub en Visual Basic) que no devuelve ningún valor. En una signatura de tipo `Action`, los parámetros de tipo representan solo parámetros de entrada. Al igual que `Func`, .NET define 17 versiones de `Action`, desde una versión que no tiene parámetros de tipo hasta una versión que tiene 16 de ellos.

## <a name="example"></a>Ejemplo

El siguiente ejemplo del método <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> muestra cómo expresar delegados Func y Action mediante expresiones lambda.

[!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
[!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]

## <a name="see-also"></a>Vea también

- [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)
