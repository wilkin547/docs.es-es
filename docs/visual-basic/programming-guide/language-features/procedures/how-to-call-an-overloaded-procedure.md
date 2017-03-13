---
title: "C&#243;mo: Llamar a un procedimiento sobrecargado (Visual Basic) | Microsoft Docs"
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
  - "llamadas a procedimientos, sobrecargados"
  - "procedimientos, llamar"
  - "procedimientos, varias versiones"
  - "procedimientos, sobrecargar"
  - "código de Visual Basic, procedimientos"
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# C&#243;mo: Llamar a un procedimiento sobrecargado (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La ventaja de sobrecargar un procedimiento radica en la flexibilidad de la llamada.  El código de llamada puede obtener la información que necesita pasar al procedimiento y llamar después a un único nombre de procedimiento, independientemente de los argumentos que pase.  
  
### Para llamar a un procedimiento que tiene más que una versión definida  
  
1.  En el código de llamada, determine qué datos va a pasar al procedimiento.  
  
2.  Escriba la llamada a procedimiento de la manera normal y presente los datos en la lista de argumentos.  Asegúrese de que los argumentos coincidan con la lista de parámetros en una de las versiones definidas para el procedimiento.  
  
3.  No es necesario determinar qué versión del procedimiento se va a llamar.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] pasa el control a la versión que coincida con la lista de argumentos.  
  
     El ejemplo siguiente llama al procedimiento `post` declarado en [Cómo: Definir varias versiones de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md).  Obtiene la identificación del cliente, determina si es `String` o `Integer`, y a continuación llama en cualquier caso al mismo procedimiento.  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Procedimientos de solución de problemas](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Cómo: Definir varias versiones de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Resolución de sobrecargas](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)