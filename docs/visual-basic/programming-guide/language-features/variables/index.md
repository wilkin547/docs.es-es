---
title: Variables en Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7a47ad7e4ade9f15159c27ac672aeb937a05493
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="variables-in-visual-basic"></a>Variables en Visual Basic
A menudo tiene que almacenar valores al realizar cálculos con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Por ejemplo, tal vez le interese calcular varios valores, compararlos y realizar diversas operaciones con ellos, según el resultado de la comparación. Para poder compararlos, debe conservar los valores.  
  
## <a name="usage"></a>Uso  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], al igual que la mayoría de los lenguajes de programación, usa variables para almacenar valores. Las *variables* tienen un nombre (la palabra que se usa para hacer referencia al valor contenido por la variable). Las variables también tienen un tipo de datos (que determina el tipo de datos que puede almacenar la variable). Las variables pueden representar una matriz si tienen que almacenar un conjunto indexado de elementos de datos estrechamente relacionados.  
  
 La inferencia de tipo de variable local permite declarar variables sin especificar explícitamente un tipo de datos. En su lugar, el compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización. Para obtener más información, vea [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).  
  
## <a name="assigning-values"></a>Asignar valores  
 Para realizar cálculos y asignar el resultado a una variable debe usar instrucciones de asignación, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  El signo igual (`=`) de este ejemplo es un operador de asignación, no un operador de igualdad. El valor se asigna a la variable `applesSold`.  
  
 Para obtener más información, vea [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) (Cómo: Introducir y extraer los datos de una variable).  
  
## <a name="variables-and-properties"></a>Variables y propiedades  
 Al igual que una variable, una *propiedad* representa un valor al que se puede tener acceso, pero es más compleja que una variable. Una propiedad usa bloques de código que controlan cómo establecer y recuperar su valor. Para obtener más información, vea [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) (Diferencias entre propiedades y variables en Visual Basic).  
  
## <a name="see-also"></a>Vea también  
 [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Solución de problemas de variables](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)  
 [Introducir y extraer los datos de una variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [Diferencias entre propiedades y Variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
