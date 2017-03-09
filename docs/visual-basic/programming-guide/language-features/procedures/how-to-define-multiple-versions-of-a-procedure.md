---
title: "C&#243;mo: Definir varias versiones de un procedimiento (Visual Basic) | Microsoft Docs"
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
  - "sobrecarga de procedimientos, varias versiones"
  - "procedimientos, definir"
  - "procedimientos, varias versiones"
  - "procedimientos, sobrecargar"
  - "código de Visual Basic, procedimientos"
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# C&#243;mo: Definir varias versiones de un procedimiento (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede definir un procedimiento en varias versiones *sobrecargándolo*, es decir, utilizando el mismo nombre pero una lista de parámetros diferente para cada versión.  El propósito de sobrecargar un procedimiento es definir varias versiones de un procedimiento estrechamente relacionadas sin tener que distinguirlas por su nombre.  
  
 Para obtener más información, vea [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
### Para definir varias versiones de un procedimiento  
  
1.  Escriba una instrucción de declaración `Sub` o `Function` para cada versión del procedimiento que desea definir.  Utilice el mismo nombre de procedimiento en cada declaración.  
  
2.  Anteponga la palabra clave `Sub` o `Function` en cada declaración con la palabra clave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md).  Si lo desea, puede omitir `Overloads` en las declaraciones, pero si incluye esta palabra clave en alguna declaración, deberá incluirla en todas.  
  
3.  Después de cada instrucción de declaración, escriba el código de procedimiento para que controle el caso concreto en el que el código de llamada proporciona argumentos que coinciden con la lista de parámetros de esa versión.  No es necesario que compruebe los parámetros que ha proporcionado el código de llamada.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] pasa el control a la versión correspondiente de su procedimiento.  
  
4.  Finalice cada versión del procedimiento con la instrucción `End Sub` o `End Function`  
  
## Ejemplo  
 En el ejemplo siguiente se define un procedimiento `Sub` que contabiliza una transacción en el balance de un cliente.  El procedimiento utiliza la palabra clave `Overloads` para definir dos versiones del procedimiento, una que acepta al cliente por nombre y otra que lo acepta por número de cuenta.  
  
 [!code-vb[VbVbcnProcedures#72](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-define-multiple-v_1.vb)]  
  
 El código de llamada puede obtener la identificación del cliente como una `String` o como un `Integer`, pero a continuación utiliza la misma instrucción de llamada en los dos casos.  
  
 Para obtener información sobre cómo llamar a estas versiones del procedimiento `post`, vea [Cómo: Llamar a un procedimiento sobrecargado](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md).  
  
## Compilar el código  
 Asegúrese de que cada una de las versiones sobrecargadas tiene el mismo nombre de procedimiento pero una lista de parámetros diferente.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Procedimientos de solución de problemas](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Resolución de sobrecargas](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)