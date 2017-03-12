---
title: "Diferencias entre pasar un argumento por valor y por referencia (Visual Basic) | Microsoft Docs"
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
  - "argumentos [Visual Basic], pasar por valor o por referencia"
  - "ByRef (palabra clave), pasar argumentos por referencia"
  - "ByVal (palabra clave), pasar argumentos por valor"
  - "procedimientos, pasar argumentos"
  - "código de Visual Basic, procedimientos"
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Diferencias entre pasar un argumento por valor y por referencia (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando pasa uno o más argumentos a un procedimiento, cada argumento corresponde a un elemento de programación subyacente en el código de llamada.  Puede pasar el valor de este elemento subyacente o una referencia a él.  Esto se conoce como *mecanismo para pasar argumentos*.  
  
## Pasar por valor  
 Un argumento se pasa *por valor* especificando la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) para el parámetro correspondiente en la definición de procedimiento.  Cuando se utiliza este mecanismo para pasar argumentos, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] copia el valor del elemento de programación subyacente en una variable local del procedimiento.  El código de procedimiento no tiene ningún acceso al elemento subyacente del código de llamada.  
  
## Pasar por referencia  
 Un argumento se pasa *por referencia* especificando la palabra clave [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para el parámetro correspondiente en la definición de procedimiento.  Cuando se utiliza este mecanismo para pasar argumentos, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona al procedimiento una referencia directa al elemento de programación subyacente del código de llamada.  
  
## Mecanismo para pasar argumentos y tipo de elemento  
 La opción del mecanismo para pasar argumentos no es igual que la clasificación del tipo de elemento subyacente.  Pasar por valor o por referencia hace referencia a lo que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona al código de procedimiento.  Un tipo de valor o un tipo de referencia hace referencia a cómo se almacena un elemento de programación en memoria.  
  
 Sin embargo, el mecanismo para pasar argumentos y el tipo de elemento están relacionados.  El valor de un tipo de referencia es un puntero que señala a los datos de otra parte de la memoria.  Esto significa que cuando pasa un tipo de referencia por valor, el código de procedimiento tiene un puntero que señala a los datos del elemento subyacente, aunque no tenga acceso al elemento subyacente en sí.  Por ejemplo, si el elemento es una variable de matriz, el código de procedimiento no tiene acceso a la variable en sí, pero sí a los miembros de la matriz.  
  
## Capacidad de modificación  
 Si se pasa un elemento no modificable como argumento, el procedimiento no podrá modificarlo nunca en el código de llamada, se pase con `ByVal` o con `ByRef`.  
  
 En la tabla siguiente se resume, para un elemento modificable, la interacción entre el tipo del elemento y el mecanismo para pasar argumentos.  
  
|Tipo de elemento|`ByVal` pasado|`ByRef` pasado|  
|----------------------|--------------------|--------------------|  
|Tipo de valor \(sólo contiene un valor\)|El procedimiento no puede modificar la variable ni ninguno de los miembros de ésta.|El procedimiento puede modificar la variable y los miembros de ésta.|  
|Tipo de referencia \(contiene un puntero a una instancia de clase o estructura\)|El procedimiento no puede modificar la variable, pero puede cambiar los miembros de la instancia a la que señala.|El procedimiento puede cambiar la variable y los miembros de la instancia a la que señala.|  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre argumentos modificables y no modificables](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Cómo: Cambiar el valor de un argumento de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Cómo: Forzar un argumento para que pase como un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)