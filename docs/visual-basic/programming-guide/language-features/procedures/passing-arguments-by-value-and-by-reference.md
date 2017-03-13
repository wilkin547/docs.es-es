---
title: "Pasar argumentos por valor y por referencia (Visual Basic) | Microsoft Docs"
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
  - "pasar argumentos, por valor o por referencia"
  - "argumentos [Visual Basic], pasar por valor o por referencia"
  - "ByRef (palabra clave), pasar argumentos por referencia"
  - "ByVal (palabra clave), pasar argumentos por valor"
  - "pasar argumentos, por valor o por referencia"
  - "código de Visual Basic, procedimientos"
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Pasar argumentos por valor y por referencia (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], puede transferir un argumento a un procedimiento *por valor* o *por referencia*.  Esto se conoce como *mecanismo para pasar argumentos*, y determina si el procedimiento puede modificar el elemento de programación subyacente al argumento en el código de llamada.  La declaración del procedimiento determina el mecanismo para pasar argumentos de cada parámetro mediante la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
## Distinciones  
 Al pasar un argumento a un procedimiento, tenga en cuenta las distintas condiciones que interactúan entre sí:  
  
-   Si el elemento de programación subyacente es modificable o no modificable  
  
-   Si el propio argumento es modificable o no modificable  
  
-   Si el argumento se transfiere por valor o por referencia  
  
-   Si el tipo de datos del argumento es un tipo de valor o un tipo de referencia  
  
 Para obtener más información, vea [Diferencias entre argumentos modificables y no modificables](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md) y [Diferencias entre pasar un argumento por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## Selección del mecanismo para pasar argumentos  
 Debe elegir minuciosamente el mecanismo para pasar argumentos de cada argumento.  
  
-   **Protección**.  A la hora de elegir uno de los dos mecanismos que existen para pasar argumentos, el criterio más importante que hay que tener en cuenta es la exposición al cambio de las variables de llamada.  La ventaja de pasar un argumento con `ByRef` es que el procedimiento puede devolver un valor al código de llamada por medio del argumento.  La ventaja de pasarlo con `ByVal` es que protege a la variable de los cambios que sobre ella pueda efectuar el procedimiento.  
  
-   **Rendimiento**.  Aunque el mecanismo que se utilice para pasar argumentos también puede afectar al rendimiento del código, la diferencia suele ser insignificante.  Existe una excepción: cuando se pasa un tipo de valor con `ByVal`.  En esta caso, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] copia todo el contenido de los datos del argumento.  Por lo tanto, para un tipo de valor grande, como una estructura, lo más eficiente es transferirlo `ByRef`.  
  
     En los tipos de referencia, sólo se copia el puntero de los datos \(cuatro bytes en plataformas de 32 bits y ocho bytes en plataformas de 64 bits\).  Por lo tanto, se pueden pasar argumentos de tipo `String` u `Object` por valor sin que esto afecte negativamente al rendimiento.  
  
## Determinación del mecanismo para pasar argumentos  
 La declaración del procedimiento especifica el mecanismo para pasar argumentos de cada parámetro.  El código de llamada no puede reemplazar un mecanismo `ByVal` .  
  
 Si un parámetro se declara con `ByRef`, el código de llamada puede forzar el mecanismo a `ByVal` agregando el argumento entre paréntesis en la llamada.  Para obtener más información, vea [Cómo: Forzar un argumento para que pase como un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md).  
  
 En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], los argumentos se pasan por valor de forma predeterminada.  
  
## Cuándo se debe pasar un argumento por valor  
  
-   Si el elemento del código de llamada subyacente al argumento es un elemento no modificable, declare el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  Ningún código puede cambiar el valor de un elemento no modificable.  
  
-   Si el elemento subyacente es modificable, pero no desea que el procedimiento pueda modificar su valor, declare el parámetro `ByVal`.  Sólo el código de llamada puede cambiar el valor de un elemento modificable transferido por valor.  
  
## Cuándo se debe pasar un argumento por referencia  
  
-   Si el procedimiento necesita realmente modificar el valor subyacente en el código de llamada, declare el parámetro correspondiente [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Si la ejecución correcta del código depende del procedimiento que cambia el elemento subyacente en el código de llamada, declare el parámetro `ByRef`.  Si lo transfiere por valor o si el código de llamada en lugar de utilizar el mecanismo para pasar argumentos `ByRef` incluye el argumento entre paréntesis, la llamada al procedimiento podría producir resultados inesperados.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo siguiente se muestra cuándo se deben pasar argumentos por valor y cuándo se deben pasar por referencia.  El procedimiento `Calculate` tiene un parámetro `ByVal` y un parámetro `ByRef`.  Dados un tipo de interés, `rate`, y una suma de dinero, `debt`, la tarea del procedimiento es calcular un nuevo valor para `debt` que sea el resultado de aplicar el tipo de interés al valor original de `debt`.  Dado que `debt` es un parámetro `ByRef`, el nuevo total se refleja en el valor del argumento en el código de llamada que corresponde a `debt`.  El parámetro `rate` es un parámetro `ByVal` porque `Calculate` no debe cambiar su valor.  
  
### Código  
 [!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Cómo: Cambiar el valor de un argumento de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Cómo: Forzar un argumento para que pase como un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)