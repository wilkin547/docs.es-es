---
title: Procedimientos recursivos (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 471746f4412b61c9782e8019aa8a9ec6221afb04
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="recursive-procedures-visual-basic"></a>Procedimientos recursivos (Visual Basic)
A *recursiva* procedimiento es aquella que se llama a sí mismo. En general, esto no es la manera más eficaz para escribir código de Visual Basic.  
  
 El siguiente procedimiento usa la recursividad para calcular el factorial de su argumento original.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Consideraciones sobre procedimientos recursivos  
 **Condiciones restrictivas**. Debe diseñar un procedimiento recursivo para probar al menos una condición que puede dificultar la recursión y también deben considerar el caso donde no se cumple ninguna condición de ese tipo dentro de un número razonable de las llamadas recursivas. Sin al menos una condición que se puedan cumplir sin errores, el procedimiento ejecuta un alto riesgo de la ejecución en un bucle infinito.  
  
 **Uso de memoria**. La aplicación tiene una cantidad limitada de espacio para las variables locales. Cada vez que un procedimiento se llama a sí mismo, utiliza más espacio para las copias adicionales de sus variables locales. Si este proceso continúa indefinidamente, se acaba produciendo un <xref:System.StackOverflowException> error.  
  
 **Eficacia**. Casi siempre se puede sustituir un bucle para que la recursividad. Un bucle no tiene la sobrecarga de pasar argumentos, inicializar el almacenamiento adicional y devolver valores. El rendimiento puede ser mucho mayor sin llamadas recursivas.  
  
 **Recursividad mutua**. Puede observar un rendimiento muy bajo, o incluso un bucle infinito, si dos procedimientos llaman entre sí. Este tipo de diseño presenta los mismos problemas que un procedimiento recursivo único, pero puede ser difícil de detectar y depurar.  
  
 **Llamadas con paréntesis**. Cuando un `Function` procedimiento llama a sí mismo recursivamente, debe seguir el nombre del procedimiento con paréntesis, incluso si no hay ninguna lista de argumentos. En caso contrario, se toma el nombre de la función representa el valor devuelto de la función.  
  
 **Pruebas**. Si escribe un procedimiento recursivo, debe probarlo con mucho cuidado para asegurarse de que siempre se cumple alguna condición de limitación. También debe asegurarse de que no se puede quedarse sin memoria debido a que hay demasiadas llamadas recursivas.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.StackOverflowException>  
 [Procedimientos](./index.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Procedimientos de función](./function-procedures.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Sobrecarga de procedimientos](./procedure-overloading.md)  
 [Solución de problemas de procedimientos](./troubleshooting-procedures.md)  
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Solución de problemas de excepciones: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
