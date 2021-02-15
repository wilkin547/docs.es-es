---
description: 'Más información sobre: variables en Visual Basic'
title: Variables
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: d00907e451fa09c6e9b6be990a24a4d39b386622
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481719"
---
# <a name="variables-in-visual-basic"></a>Variables en Visual Basic

A menudo tiene que almacenar valores al realizar cálculos con Visual Basic. Por ejemplo, tal vez le interese calcular varios valores, compararlos y realizar diversas operaciones con ellos, según el resultado de la comparación. Para poder compararlos, debe conservar los valores.  
  
## <a name="usage"></a>Uso  

 Visual Basic, al igual que la mayoría de los lenguajes de programación, utiliza variables para almacenar valores. Las *variables* tienen un nombre (la palabra que se usa para hacer referencia al valor contenido por la variable). Las variables también tienen un tipo de datos (que determina el tipo de datos que puede almacenar la variable). Las variables pueden representar una matriz si tienen que almacenar un conjunto indexado de elementos de datos estrechamente relacionados.  
  
 La inferencia de tipo de variable local permite declarar variables sin especificar explícitamente un tipo de datos. En su lugar, el compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización. Para obtener más información, vea [Local Type Inference](local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).  
  
## <a name="assigning-values"></a>Asignar valores  

 Para realizar cálculos y asignar el resultado a una variable debe usar instrucciones de asignación, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> El signo igual (`=`) de este ejemplo es un operador de asignación, no un operador de igualdad. El valor se asigna a la variable `applesSold`.  
  
 Para obtener más información, vea [How to: Move Data Into and Out of a Variable](how-to-move-data-into-and-out-of-a-variable.md) (Cómo: Introducir y extraer los datos de una variable).  
  
## <a name="variables-and-properties"></a>Variables y propiedades  

 Al igual que una variable, una *propiedad* representa un valor al que se puede tener acceso, pero es más compleja que una variable. Una propiedad usa bloques de código que controlan cómo establecer y recuperar su valor. Para obtener más información, vea [Differences Between Properties and Variables in Visual Basic](../procedures/differences-between-properties-and-variables.md) (Diferencias entre propiedades y variables en Visual Basic).  
  
## <a name="see-also"></a>Consulte también

- [Declaración de variable](variable-declaration.md)
- [Variables de objeto](object-variables.md)
- [Solución de problemas de variables](troubleshooting-variables.md)
- [Procedimiento para introducir y extraer los datos de una variable](how-to-move-data-into-and-out-of-a-variable.md)
- [Diferencias entre propiedades y variables en Visual Basic](../procedures/differences-between-properties-and-variables.md)
- [Inferencia de tipo de variable local](local-type-inference.md)
