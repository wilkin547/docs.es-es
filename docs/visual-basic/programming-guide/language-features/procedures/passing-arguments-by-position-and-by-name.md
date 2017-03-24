---
title: "Pasar argumentos por posici&#243;n o por nombre (Visual Basic) | Microsoft Docs"
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
  - "pasar argumentos mediante :="
  - "pasar argumentos"
  - "pasar argumentos, por posición"
  - "argumentos [Visual Basic], enumerar por nombre"
  - "argumentos [Visual Basic], pasar por nombre"
  - "argumentos [Visual Basic], pasar por posición"
  - "Function (procedimientos), pasar argumentos"
  - "argumentos con nombre"
  - "argumentos con nombre, pasar argumentos"
  - "parámetros con nombre"
  - "parámetros con nombre, pasar argumentos"
  - "pasar parámetros, por nombre"
  - "pasar parámetros, por posición"
  - "pasar parámetros, argumentos de parámetro con nombre"
  - "argumentos de procedimientos"
  - "procedimientos, argumentos"
  - "procedimientos, llamar"
  - "Sub (procedimientos), pasar argumentos"
  - "código de Visual Basic, procedimientos"
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Pasar argumentos por posici&#243;n o por nombre (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando se llama a un procedimiento `Sub` o `Function`, los argumentos pueden pasarse *por posición*, es decir, en el orden en que aparecen en la definición del procedimiento, o *por nombre*, sin tener en cuenta la posición.  
  
 Para pasar un argumento por nombre, hay que especificar el nombre declarado del argumento, seguido de un signo de dos puntos y un signo igual \(`:=`\) y seguido del valor del argumento.  Los argumentos que se pasan por nombre pueden suministrarse en cualquier orden.  
  
 Por ejemplo, el siguiente procedimiento `Sub` toma tres argumentos:  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 Cuando se llama a este procedimiento, los argumentos pueden suministrarse por posición, por nombre o mediante una combinación de ambos.  
  
## Pasar argumentos por posición  
 Puede llamar al procedimiento  `studentInfo`  pasando sus argumentos por posición y delimitados por comas, como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 Si omite un argumento opcional de una lista de argumentos por posición, deberá mantener su posición mediante una coma.  El ejemplo siguiente llama a  `studentInfo`  sin el argumento  `age` :  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## Pasar argumentos por nombre  
 Otra opción es llamar al procedimiento  `studentInfo`  pasando sus argumentos por nombre, también delimitados por comas, como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## Pasar argumentos por posición y por nombre  
 Puede suministrar los argumentos por posición y por nombre a la vez en la misma llamada a un procedimiento, como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 En el ejemplo anterior, no se necesita una coma adicional para mantener la posición del argumento  `age`  omitido, puesto que  `birth`  se pasa por nombre.  
  
 Si se suministran argumentos por nombre y por posición, los argumentos por posición deben preceder al resto.  Si se ha suministrado un argumento por nombre, el resto de los argumentos deberán especificarse también por nombre.  
  
## Suministrar argumentos opcionales por nombre  
 Pasar argumentos por nombre tiene especial utilidad si se llama a un procedimiento que tiene varios argumentos opcionales.  Si se suministran argumentos por nombre, no es necesario utilizar comas consecutivas para denotar los argumentos por posición ausentes.  Pasar argumentos por nombre facilita también la tarea de realizar un seguimiento de los argumentos que se pasan y de los que se omiten.  
  
## Restricciones al suministro de argumentos por nombre  
 No se pueden pasar argumentos por nombre a fin de evitar tener que especificar argumentos requeridos.  Sólo pueden omitirse los argumentos opcionales.  
  
 No se puede pasar una matriz de parámetros por nombre.  Esto obedece a que, cuando se llama al procedimiento, se suministra a la matriz de parámetros un número indeterminado de argumentos separados por comas, y el compilador no puede asociar más de un argumento a cada nombre individual.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Matrices de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)   
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)