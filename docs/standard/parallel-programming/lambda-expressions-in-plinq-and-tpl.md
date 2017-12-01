---
title: Expresiones lambda en PLINQ y TPL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79ab0f4427e0f37259f88cd3ec0762d1582481f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a>Expresiones lambda en PLINQ y TPL
La biblioteca (TPL) contiene muchos métodos que toman una de las <xref:System.Func%601?displayProperty=nameWithType> o <xref:System.Action?displayProperty=nameWithType> familia de delegados como parámetros de entrada. Puede usar estos delegados para pasar de la lógica personalizada del programa al bucle, tarea o consulta en paralelo. Los ejemplos de código de TPL, igual que igual que de PLINQ, usan expresiones lambda para crear instancias de esos delegados como bloques de código insertados. En este tema se proporciona una breve introducción a Func y Action, y muestra cómo usar las expresiones lambda en la biblioteca TPL y PLINQ.  
  
 **Nota** Para más información sobre los delegados en general, consulte [Delegados](../../csharp/programming-guide/delegates/index.md) y [Delegados](../../visual-basic/programming-guide/language-features/delegates/index.md). Para más información sobre las expresiones lambda en C# y [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], consulte [Expresiones lambda](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) y [Expresiones lambda](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="func-delegate"></a>Func (delegado)  
 Un delegado `Func` encapsula un método que devuelve un valor. En una signatura Func, el último parámetro de tipo o el ubicado más a la derecha siempre especifica el tipo de devolución. Una causa común de errores del compilador está intentando pasar dos parámetros de entrada para un <xref:System.Func%602?displayProperty=nameWithType>; en el hecho de este tipo es solo un parámetro de entrada. La biblioteca de clases de Framework define 17 versiones de `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, y así sucesivamente hasta a través de <xref:System.Func%6017?displayProperty=nameWithType>.  
  
## <a name="action-delegate"></a>Action (delegado)  
 A <xref:System.Action?displayProperty=nameWithType> delegado encapsula un método (Sub en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) que no devuelve un valor o devuelve [void](~/docs/csharp/language-reference/keywords/void.md). En una signatura de tipo Action, los parámetros de tipo representan solo parámetros de entrada. Al igual que Func, la biblioteca de clases de .NET Framework define 17 versiones de Action, desde una versión que no tiene parámetros de tipo hasta una versión que tiene 16.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo para el <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> método muestra cómo expresar delegados Func y Action mediante expresiones lambda.  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## <a name="see-also"></a>Vea también  
 [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)
