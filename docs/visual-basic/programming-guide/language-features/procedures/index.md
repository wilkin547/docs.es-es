---
title: "Procedimientos en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedimientos"
  - "procedimientos, código estructurado"
  - "procedimientos, tipos de"
  - "código estructurado, procedimientos"
  - "código de Visual Basic, procedimientos"
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Procedimientos en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Un *procedimiento* es un bloque de instrucciones de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] incluido entre una instrucción de declaración \(`Function`, `Sub`, `Operator`, `Get`, `Set`\) y una declaración `End` correspondiente.  Todas las instrucciones ejecutables de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] deben estar incluidas en algún procedimiento.  
  
## Llamar a un procedimiento  
 Los procedimientos se invocan desde otras partes del código.  Esto se conoce como una *llamada a procedimiento*.  Cuando finaliza la ejecución de un procedimiento, éste devuelve el control al código que lo invocó, que recibe el nombre de *código de llamada*.  El código de llamada es una instrucción o una expresión contenida en una instrucción, que hace referencia al procedimiento por su nombre y le transfiere el control.  
  
## Volver de un procedimiento  
 Los procedimientos devuelven el control al código de llamada cuando finalizan su ejecución.  Para ello, puede utilizar [Return \(Instrucción\)](../../../../visual-basic/language-reference/statements/return-statement.md), la instrucción [Exit \(Instrucción\)](../../../../visual-basic/language-reference/statements/exit-statement.md) apropiada para el procedimiento o la instrucción [End \<palabra clave\> \(Instrucción\)](../../../../visual-basic/language-reference/statements/end-keyword-statement.md) del procedimiento.  El control se devuelve al código de llamada, a continuación del punto de la llamada al procedimiento.  
  
-   Con una instrucción `Return`, el control vuelve inmediatamente al código de llamada.  No se ejecutan las instrucciones siguientes a la instrucción `Return`.  Puede tener más de una instrucción `Return` en el mismo procedimiento.  
  
-   Con una instrucción `Exit Sub` o `Exit Function`, el control vuelve inmediatamente al código de llamada.  No se ejecutan las instrucciones siguientes a la instrucción `Exit`.  Puede tener más de una instrucción `Exit` en el mismo procedimiento, y puede mezclar las instrucciones `Return` y `Exit` en el mismo procedimiento.  
  
-   Si un procedimiento no incluye instrucciones `Return` o `Exit`, concluye con una instrucción `End Sub` o `End Function`, `End Get` o `End Set` a continuación de la última instrucción del cuerpo del procedimiento.  La instrucción `End` devuelve el control inmediatamente al código de llamada.  Puede tener sólo una instrucción `End` en un procedimiento.  
  
## Parámetros y argumentos  
 En la mayoría de los casos, un procedimiento necesita funcionar en datos diferentes cada vez que lo llama.  Puede pasar esta información al procedimiento como parte de la llamada al procedimiento.  El procedimiento define cero o más *parámetros*, cada uno de los cuales representa un valor que el procedimiento espera que le pase.  Cada parámetro de la definición del procedimiento cuenta con un *argumento* correspondiente en la llamada al procedimiento.  Un argumento representa el valor que pasa al parámetro correspondiente en una llamada a procedimiento determinada.  
  
## Tipos de procedimientos  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] utiliza varios tipos de procedimientos:  
  
-   [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md): ejecutan acciones pero no devuelven un valor al código de llamada.  
  
-   Los procedimientos de control de eventos son procedimientos `Sub` que se ejecutan en respuesta a un evento provocado por una acción del usuario o por un suceso en un programa.  
  
-   [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md): devuelven un valor al código de llamada.  Pueden realizar otras acciones antes de volver.  
  
-   [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md): devuelven y asignan valores de propiedades en objetos o módulos.  
  
-   [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md): definen el comportamiento de un operador estándar cuando uno o los dos operandos son una clase definida recientemente o una estructura.  
  
-   [Procedimientos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md): definen uno o varios *parámetros de tipo* además de sus parámetros normales, de forma que el código de llamada puede pasar tipos de datos específicos cada vez que realiza una llamada.  
  
## Procedimientos y código estructurado  
 Todas las líneas de código ejecutable de una aplicación deben encontrarse dentro de un procedimiento, por ejemplo, `Main`, `calculate` o `Button1_Click`.  La aplicación se leerá con mayor facilidad si subdivide los procedimientos grandes en procedimientos más pequeños.  
  
 Los procedimientos son útiles para realizar tareas repetitivas o compartidas, como cálculos de uso frecuente, manipulación de texto y controles, y operaciones con bases de datos.  Se puede llamar a un procedimiento desde distintos lugares del código; de modo que los procedimientos se prestan a servir de bloques de creación de la aplicación.  
  
 La estructuración del código en procedimientos aporta las siguientes ventajas:  
  
-   Los procedimientos permiten desglosar los programas en unidades lógicas independientes.  Es más fácil depurar unidades individuales que todo un programa sin procedimientos.  
  
-   Después de desarrollar los procedimientos para el uso en un programa, puede utilizarlos en otros programas, a menudo con pocas o ninguna modificación.  Esto ayuda a evitar la duplicación del código.  
  
## Vea también  
 [Cómo: crear un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Procedimientos recursivos](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Procedimientos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)