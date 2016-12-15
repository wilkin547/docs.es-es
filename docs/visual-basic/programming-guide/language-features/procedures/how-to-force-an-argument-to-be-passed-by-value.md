---
title: "C&#243;mo: Forzar un argumento para que pase como un valor (Visual Basic) | Microsoft Docs"
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
  - "argumentos [Visual Basic], ByVal"
  - "argumentos [Visual Basic], cambiar valor"
  - "argumentos [Visual Basic], entre paréntesis"
  - "argumentos [Visual Basic], pasar por valor"
  - "argumentos de procedimientos"
  - "argumentos de procedimientos, entre paréntesis"
  - "parámetros de procedimientos"
  - "procedimientos, argumentos"
  - "procedimientos, llamar"
  - "procedimientos, parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Forzar un argumento para que pase como un valor (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El mecanismo para pasar argumentos se determina en la declaración del procedimiento.  Si un parámetro se declara [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] espera transferir el argumento correspondiente por referencia.  Esto permite al procedimiento cambiar el valor del elemento de programación subyacente al argumento en el código de llamada.  Si desea proteger el elemento subyacente frente a un cambio de este tipo, puede encerrar entre paréntesis el nombre del argumento en lugar de utilizar el mecanismo para pasar argumentos `ByRef` en la llamada al procedimiento.  Estos paréntesis son distintos de los paréntesis que encierran la lista de argumentos en la llamada.  
  
 El código de llamada no puede reemplazar un mecanismo [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
### Para forzar un argumento para que pase por valor  
  
-   Si el parámetro correspondiente se declara `ByVal` en el procedimiento, no es necesario realizar ningún paso adicional.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ya tiene previsto pasar el argumento por valor.  
  
-   Si el parámetro correspondiente se declara `ByRef` en el procedimiento, incluya el argumento entre paréntesis en la llamada al procedimiento.  
  
## Ejemplo  
 En el ejemplo siguiente se reemplaza una declaración del parámetro `ByRef`.  En la llamada que obliga a utilizar `ByVal`, tenga en cuenta los dos niveles de paréntesis.  
  
 [!code-vb[VbVbcnProcedures#39](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 Cuando `str` está encerrado entre paréntesis adicionales dentro de la lista de argumentos, el procedimiento `setNewString` no puede cambiar su valor en el código de llamada, y `MsgBox` muestra "Cannot be replaced if passed ByVal".  Cuando `str` no está incluido entre paréntesis adicionales, el procedimiento no puede cambiarlo, y `MsgBox` muestra "This is a new value for the inString argument".  
  
## Compilar el código  
 Cuando se pasa una variable por referencia, debe utilizarse la palabra clave `ByRef` para especificar este mecanismo.  
  
 En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], los argumentos se pasan por valor de forma predeterminada.  Sin embargo, es una práctica de programación recomendable incluir la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) con cada parámetro declarado.  De este modo, el código resulta más fácil de leer.  
  
## Programación eficaz  
 Si un procedimiento declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la ejecución correcta del código dependerá de si es capaz de cambiar el elemento subyacente en el código de llamada.  Si el código de llamada sustituye este mecanismo de llamada encerrando el argumento entre paréntesis, o si transfiere un argumento que no se puede modificar, el procedimiento no puede cambiar el elemento subyacente.  Esto podría generar resultados inesperados en el código de llamada.  
  
## Seguridad de .NET Framework  
 Existe siempre el riesgo potencial de permitir que un procedimiento cambie el valor subyacente a un argumento en el código de llamada.  Asegúrese de que tiene previsto que este valor se modifique y prepárese para comprobar su validez antes de utilizarlo.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre argumentos modificables y no modificables](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Diferencias entre pasar un argumento por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Cómo: Cambiar el valor de un argumento de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)