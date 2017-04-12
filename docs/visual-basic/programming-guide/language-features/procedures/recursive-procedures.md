---
title: Procedimientos recursivos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9fc95cd5f7cfd5637f6282c6ef571eb81bac1816
ms.lasthandoff: 03/13/2017

---
# <a name="recursive-procedures-visual-basic"></a>Procedimientos recursivos (Visual Basic)
Un *recursiva* procedimiento es aquél que se llama a sí mismo. En general, esto no es la manera más eficaz escribir [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] código.  
  
 El siguiente procedimiento utiliza la recursividad para calcular el factorial de su argumento original.  
  
 [!code-vb[VbVbcnProcedures&#51;](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Consideraciones sobre procedimientos recursivos  
 **Condiciones restrictivas**. Debe diseñar un procedimiento recursivo para probar al menos una condición que puede finalizar la recursividad y también debe controlar el caso donde no se cumple ninguna condición de ese tipo dentro de un número razonable de llamadas recursivas. Sin al menos una condición que puede cumplirse sin errores, el procedimiento ejecuta un alto riesgo de ejecutar un bucle infinito.  
  
 **Uso de memoria**. La aplicación tiene una cantidad limitada de espacio para variables locales. Cada vez que un procedimiento se llama a sí mismo, utiliza más espacio para las copias adicionales de sus variables locales. Si este proceso continúa indefinidamente, se acaba produciendo un <xref:System.StackOverflowException>error.</xref:System.StackOverflowException>  
  
 **Eficiencia**. Casi siempre se puede sustituir un bucle por la recursividad. Un bucle no tiene la sobrecarga de transferir argumentos, inicializar el almacenamiento adicional y devolver valores. El rendimiento puede ser mucho mayor sin llamadas recursivas.  
  
 **Recursividad mutua**. Puede observar un rendimiento muy deficiente o incluso un bucle infinito si dos procedimientos llaman entre sí. Este tipo de diseño presenta los mismos problemas que un procedimiento recursivo único, pero puede ser difícil de detectar y depurar.  
  
 **Llamadas con paréntesis**. Cuando un `Function` procedimiento llama repetidamente, deberá seguir el nombre del procedimiento con paréntesis, incluso si no hay ninguna lista de argumentos. De lo contrario, se toma el nombre de función que representa el valor devuelto de la función.  
  
 **Pruebas**. Si escribe un procedimiento recursivo, debe probarlo con mucho cuidado para asegurarse de que siempre cumple ciertas condiciones de limitación. También debe asegurarse de que no se puede ejecutar sin memoria debido a que hay demasiadas llamadas recursivas.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.StackOverflowException></xref:System.StackOverflowException>   
 [Procedimientos](./index.md)   
 [Sub (procedimientos)](./sub-procedures.md)   
 [Function (procedimientos)](./function-procedures.md)   
 [Property (procedimientos)](./property-procedures.md)   
 [Procedimientos de operadores](./operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Sobrecarga de procedimientos](./procedure-overloading.md)   
 [Procedimientos de solución de problemas](./troubleshooting-procedures.md)   
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Solución de problemas de excepciones: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
