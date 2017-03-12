---
title: "C&#243;mo: Pasar argumentos a un procedimiento (Visual Basic) | Microsoft Docs"
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
  - "pasar argumentos, procedimientos"
  - "argumentos [Visual Basic], pasar a procedimientos"
  - "argumentos de procedimientos"
  - "parámetros de procedimientos"
  - "procedimientos, argumentos"
  - "procedimientos, llamar"
  - "procedimientos, parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# C&#243;mo: Pasar argumentos a un procedimiento (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Al llamar a un procedimiento, se agrega detrás del nombre de procedimiento una lista de argumentos entre paréntesis.  Se proporciona un argumento correspondiente a cada parámetro necesario que el procedimiento define y, opcionalmente, se pueden proporcionar argumentos para los parámetros `Optional`.  Cuando no se proporciona un parámetro `Optional` en la llamada, se debe incluir una coma para marcar su lugar en la lista de argumentos si se indica algún argumento posterior.  
  
 Si se desea pasar un argumento de un tipo de datos diferente al del parámetro correspondiente, como `Byte` a `String`, se puede establecer el modificador de comprobación de tipos \([Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) en `Off`.  Si `Option Strict` está en `On`, se deben utilizar conversiones de ampliación o palabras clave de conversión explícita.  Para obtener más información, vea [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Para obtener más información, vea [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md).  
  
### Para pasar uno o varios argumentos a un procedimiento  
  
1.  En la instrucción de llamada, agregue paréntesis detrás del nombre de procedimiento.  
  
2.  Coloque una lista de argumentos entre los paréntesis.  Incluya un argumento para cada parámetro necesario que el procedimiento define y separe los argumentos por comas.  
  
3.  Asegúrese de que cada argumento sea una expresión válida que evalúa el tipo de datos convertible al tipo que el procedimiento define para el parámetro correspondiente.  
  
4.  Si un parámetro está definido como [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), puede incluirlo en la lista de argumentos u omitirlo.  Si lo omite, el procedimiento utiliza el valor predeterminado definido para ese parámetro.  
  
5.  Si omite un argumento para un parámetro `Optional` y hay otro parámetro después de él en la lista de parámetros, puede marcar el lugar del argumento omitido mediante una coma adicional en la lista de argumentos.  
  
     En el siguiente ejemplo se llama a la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
     [!code-vb[VbVbcnProcedures#34](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-pass-arguments-to_1.vb)]  
  
     El ejemplo anterior proporciona el primer argumento necesario que es la cadena de mensaje que se va a mostrar.  Omite un argumento para el segundo parámetro opcional que especifica los botones que se van a mostrar en el cuadro de mensaje.  Como la llamada no proporciona ningún valor, `MsgBox` utiliza el valor predeterminado, `MsgBoxStyle.OKOnly`, que muestra sólo un botón **Aceptar**.  
  
     La segunda coma de la lista de argumentos marca el lugar del segundo argumento omitido y la última cadena pasa al tercer parámetro opcional de `MsgBox`, que es el texto que se va a mostrar en la barra de título.  
  
## Vea también  
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Cómo: Definir un parámetro para un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-parameter-for-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Procedimientos recursivos](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Programación orientada a objetos](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)