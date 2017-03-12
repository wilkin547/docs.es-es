---
title: "Diferencias entre par&#225;metros y argumentos (Visual Basic) | Microsoft Docs"
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
  - "argumentos [Visual Basic], y parámetros"
  - "parámetros, y argumentos"
  - "parámetros, definición"
  - "argumentos de procedimientos"
  - "parámetros de procedimientos"
  - "procedimientos, argumentos"
  - "procedimientos, parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Diferencias entre par&#225;metros y argumentos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En la mayoría de los casos, un procedimiento debe tener cierta información sobre las circunstancias en las que se le ha llamado.  Un procedimiento que ejecuta tareas repetidas o compartidas utiliza datos distintos en cada llamada.  Estos datos se componen de variables, constantes y expresiones que se transfieren al procedimiento cada vez que se le llama.  
  
 Para comunicar esta información al procedimiento, el procedimiento define un *parámetro*, y el código de llamada transfiere un *argumento* a dicho parámetro.  Puede imaginar el parámetro como una plaza de aparcamiento y el argumento como un automóvil.  Del mismo modo que diferentes automóviles puede aparcan en la misma plaza de aparcamiento en momentos distintos, el código de llamada puede transferir un argumento distinto al mismo parámetro cada vez que llama al procedimiento.  
  
## Parámetros  
 Un *parámetro* representa un valor que el procedimiento espera que se transfiera cuando es llamado.  La declaración del procedimiento define sus parámetros.  
  
 Cuando se define un procedimiento `Function` o `Sub`, se especifica una *lista de parámetros* entre paréntesis que va inmediatamente después del nombre de procedimiento.  Para cada parámetro, se especifica un nombre, un tipo de datos y un mecanismo para pasar argumentos \([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\).  También puede indicar que un parámetro es opcional.  Esto significa que el código de llamada no tiene que transferir un valor.  
  
 El nombre de cada parámetro actúa como una *variable local* en el procedimiento.  El nombre del parámetro se utiliza del mismo modo que cualquier otra variable.  
  
## Argumentos  
 Un *argumento* representa el valor que se transfiere a un parámetro del procedimiento cuando se llama al procedimiento.  El código de llamada proporciona los argumentos cuando llama al procedimiento.  
  
 Cuando se llama al procedimiento `Function` o `Sub`, se incluye una *lista de argumentos* entre paréntesis que van inmediatamente después del nombre del procedimiento.  Cada argumento se corresponde con el parámetro situado en la misma posición de la lista.  
  
 A diferencia de la definición de parámetros, los argumentos no tienen nombres.  Cada argumento es una expresión que puede contener cero o más variables, constantes y literales.  El tipo de datos de la expresión evaluada normalmente debe coincidir con el tipo de datos definido para el parámetro correspondiente, y en algún caso, debe poder convertirse al tipo del parámetro.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Cómo: Definir un parámetro para un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Procedimientos recursivos](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)