---
title: "Diferencias entre argumentos modificables y no modificables (Visual Basic) | Microsoft Docs"
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
  - "argumentos [Visual Basic], modificables"
  - "argumentos [Visual Basic], no modificables"
  - "argumentos de procedimientos"
  - "procedimientos, argumentos"
  - "código de Visual Basic, procedimientos"
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Diferencias entre argumentos modificables y no modificables (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando se llama a un procedimiento, normalmente se transfieren uno o varios argumentos a dicho procedimiento.  Cada argumento se corresponde con un elemento de programación subyacente.  Los elementos subyacentes y los argumentos pueden ser modificables o no modificables.  
  
## Elementos modificables y no modificables  
 Un elemento de programación puede ser un *elemento modificable*, cuyo valor se puede modificar, o un *elemento no modificable*, cuyo valor se mantiene fijo una vez que se ha creado.  
  
 En la tabla siguiente se muestran los elementos de programación modificables y no modificables.  
  
|Elementos modificables|Elementos no modificables|  
|----------------------------|-------------------------------|  
|Variables locales \(se declaran dentro de los procedimientos\), incluidas las variables de objeto, excepto las de sólo lectura|Variables, campos y propiedades de sólo lectura|  
|Campos \(variables miembro de módulos, clases y estructuras\), excepto las de sólo lectura|Constantes y literales|  
|Propiedades, salvo las de sólo lectura|Miembros de enumeraciones|  
|Elementos matriciales|Expresiones \(aun cuando sus elementos sean modificables\)|  
  
## Argumentos modificables y no modificables  
 Un *argumento modificable* es aquel que tiene un elemento subyacente que se puede modificar.  El código de llamada puede almacenar un nuevo valor en cualquier momento y, si se transfiere el argumento [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), el código del procedimiento también puede modificar el elemento subyacente en el código de llamada.  
  
 Un *argumento no modificable* o tiene un elemento subyacente no modificable o se ha transferido [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  El procedimiento no puede modificar el elemento subyacente en el código de llamada, aun cuando se trate de un elemento modificable.  Si es un elemento no modificable, tampoco podrá modificarlo el propio código de llamada.  
  
 El procedimiento invocado podría modificar la copia local del argumento no modificable, pero esta modificación no afectaría al elemento subyacente del código de llamada.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre pasar un argumento por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Cómo: Cambiar el valor de un argumento de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Cómo: Forzar un argumento para que pase como un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)