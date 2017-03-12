---
title: "Procedimientos recursivos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "funciones [Visual Basic], llamar de forma recursiva"
  - "procedimientos, llamar"
  - "procedimientos, recursivos"
  - "procedimientos, que se llaman a sí mismos"
  - "recursividad"
  - "procedimientos recursivos"
  - "código de Visual Basic, procedimientos"
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Procedimientos recursivos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un procedimiento *recursivo* es aquél que se llama a sí mismo.  En general, esta no suele ser la manera más eficaz de escribir código en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 En el siguiente procedimiento se utiliza la recursividad para calcular el factorial de su argumento original.  
  
 [!code-vb[VbVbcnProcedures#51](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/recursive-procedures_1.vb)]  
  
## Consideraciones sobre procedimientos recursivos  
 **Condiciones de limitación**.  Debe designar un procedimiento recursivo para probar al menos una condición que pueda poner fin a la recursividad; también debe supervisar los casos en los que no se satisface ninguna condición dentro de un número razonable de llamadas recursivas.  Si no existe al menos una condición que pueda cumplirse sin errores, el procedimiento corre un riesgo elevado de ejecutarse en un bucle infinito.  
  
 **Uso de la memoria**.  La aplicación tiene una cantidad de espacio limitada para las variables locales.  Cada vez que un procedimiento se llama a sí mismo, utiliza más cantidad de ese espacio para las copias adicionales de sus variables locales.  Si este proceso continúa indefinidamente, se acaba produciendo un error <xref:System.StackOverflowException>.  
  
 **Eficacia**.  Casi siempre se puede sustituir un bucle por la recursividad.  Un bucle no tiene la sobrecarga de transferir argumentos, inicializar el almacenamiento adicional y devolver valores.  Su rendimiento puede ser mucho mayor sin llamadas recursivas.  
  
 **Recursividad mutua**.  Si dos procedimientos se llaman mutuamente, el rendimiento puede ser muy deficiente o incluso puede producirse un bucle infinito.  Este tipo de diseño presenta los mismos problemas que un procedimiento recursivo único, pero puede ser más difícil de detectar y depurar.  
  
 **Llamadas con paréntesis**.  Cuando un procedimiento `Function` se llama a sí mismo de manera recursiva, debe agregar paréntesis detrás del nombre del procedimiento, aun cuando no exista una lista de argumentos.  De lo contrario, se considerará que el nombre de la función representa al valor devuelto por ésta.  
  
 **Pruebas** Si escribe un procedimiento recursivo, debe probarlo minuciosamente para asegurarse de que siempre cumple ciertas condiciones de limitación.  También debería comprobar que la memoria no resulta insuficiente debido a la gran cantidad de llamadas recursivas.  
  
## Vea también  
 <xref:System.StackOverflowException>   
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Procedimientos de solución de problemas](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Estructuras de bucles](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Solución de problemas de excepciones: System.StackOverflowException](../Topic/Troubleshooting%20Exceptions:%20System.StackOverflowException.md)