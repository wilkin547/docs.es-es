---
description: 'Más información sobre: procedimientos recursivos (Visual Basic)'
title: Procedimientos recursivos
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: 378b279a6664cd494fb2e26ff3276afcea56cc16
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466567"
---
# <a name="recursive-procedures-visual-basic"></a>Procedimientos recursivos (Visual Basic)

Un procedimiento *recursivo* es uno que se llama a sí mismo. En general, esta no es la forma más eficaz de escribir código de Visual Basic.  
  
 En el procedimiento siguiente se usa la recursividad para calcular el factorial de su argumento original.  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a>Consideraciones con procedimientos recursivos

 **Condiciones de limitación**. Debe diseñar un procedimiento recursivo para probar al menos una condición que pueda finalizar la recursividad, y también debe controlar el caso en el que no se cumpla esa condición en un número razonable de llamadas recursivas. Si no hay al menos una condición que pueda cumplirse sin errores, el procedimiento ejecuta un alto riesgo de ejecutarse en un bucle infinito.

 **Uso de memoria**. La aplicación tiene una cantidad limitada de espacio para las variables locales. Cada vez que un procedimiento se llama a sí mismo, usa más espacio para las copias adicionales de sus variables locales. Si este proceso continúa indefinidamente, se produce un <xref:System.StackOverflowException> error.

 **Eficacia**. Casi siempre se puede sustituir un bucle por recursividad. Un bucle no tiene la sobrecarga de pasar argumentos, inicializar almacenamiento adicional y devolver valores. El rendimiento puede ser mucho mejor sin llamadas recursivas.

 **Recursividad mutua**. Es posible que observe un rendimiento muy deficiente, o incluso un bucle infinito, si dos procedimientos se llaman entre sí. Este tipo de diseño presenta los mismos problemas que un único procedimiento recursivo, pero puede ser más difícil de detectar y depurar.

 **Llamar a con paréntesis**. Cuando un `Function` procedimiento se llama a sí mismo de forma recursiva, debe seguir el nombre del procedimiento entre paréntesis, incluso si no hay ninguna lista de argumentos. De lo contrario, el nombre de la función se toma como representa el valor devuelto de la función.

 **Pruebas** Si escribe un procedimiento recursivo, debe probarlo con cuidado para asegurarse de que siempre cumple alguna condición de limitación. También debe asegurarse de que no se puede quedarse sin memoria debido a que hay demasiadas llamadas recursivas.

## <a name="see-also"></a>Consulte también

- <xref:System.StackOverflowException>
- [Procedimientos](index.md)
- [Procedimientos Sub](sub-procedures.md)
- [Procedimientos de función](function-procedures.md)
- [Procedimientos de propiedad](property-procedures.md)
- [Procedimientos de operador](operator-procedures.md)
- [Argumentos y parámetros de procedimiento](procedure-parameters-and-arguments.md)
- [Sobrecarga de procedimientos](procedure-overloading.md)
- [Solución de problemas de procedimientos](troubleshooting-procedures.md)
- [Estructuras de bucle](../control-flow/loop-structures.md)
