---
title: "Procedimientos de funci&#243;n (Visual Basic) | Microsoft Docs"
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
  - "Function (procedimientos)"
  - "valores devueltos, procedimientos de función"
  - "código de Visual Basic, procedimientos"
  - "procedimientos, llamada"
  - "procedimientos, procedimientos de función"
  - "sintaxis, procedimientos de función"
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Procedimientos de funci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Un procedimiento `Function` es una serie de instrucciones de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] delimitadas por las instrucciones `Function` y `End Function`.  El procedimiento `Function` realiza una tarea y, a continuación, devuelve el control al código de llamada.  Cuando devuelve el control, también devuelve un valor al código de llamada.  
  
 Cada vez que se llama a un procedimiento, se ejecutan las instrucciones de éste, desde la primera instrucción ejecutable tras la instrucción `Function` hasta la primera instrucción `End Function`, `Exit Function` o `Return` que se encuentre.  
  
 Puede definir un procedimiento `Function` en un módulo, clase o estructura.  Es `Public` de forma predeterminada, lo que significa que puede llamarlo desde cualquier lugar de la aplicación que tenga acceso al módulo, clase o estructura en el que se ha definido.  
  
 Un procedimiento `Function` puede aceptar argumentos, como constantes, variables o expresiones, que le pasa el código de llamada.  
  
## Sintaxis de la declaración  
 La sintaxis para declarar un procedimiento `Function` es la siguiente:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 Los *modificadores* pueden especificar un nivel de acceso e información relativo a la sobrecarga, a la invalidación, uso compartido y sombreado.  Para obtener más información, vea [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Declara cada parámetro de la misma manera que para [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md).  
  
### Tipo de datos  
 Todos los procedimientos `Function` tienen un tipo de datos, al igual que las variables.  La cláusula `As` especifica este tipo de datos en la instrucción `Function` y determina el tipo de datos del valor que la función devuelve al código de llamada.  En las siguientes declaraciones de ejemplo se ilustra esto último.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Para obtener más información, vea "Partes" en [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## Valores devueltos  
 El valor que un procedimiento de `Function` envía de nuevo al código de llamada se denomina valor devuelto.  El procedimiento devuelve dicho valor de dos maneras:  
  
-   Utiliza la instrucción `Return` para especificar el valor devuelto y devuelve el control inmediatamente al programa de llamada.  Esto se ilustra en el siguiente ejemplo:  
  
    ```vb  
    Function FunctionName [(ParameterList)] As ReturnType  
        ' The following statement immediately transfers control back  
        ' to the calling code and returns the value of Expression.  
        Return Expression  
    End Function  
    ```  
  
-   La función asigna un valor a su propio nombre de función en una o más instrucciones del procedimiento.  El control no vuelve al programa de llamada hasta que se ejecuta una instrucción `Exit Function` o `End Function`.  Esto se ilustra en el siguiente ejemplo:  
  
    ```vb  
    Function FunctionName [(ParameterList)] As ReturnType  
        ‘ The following statement does not transfer control back to the calling code.  
        FunctionName = Expression  
        ' When control returns to the calling code, Expression is the return value.  
    End Function  
    ```  
  
 La ventaja de asignar el valor devuelto al nombre de la función es que el control permanece en el procedimiento hasta que encuentra una instrucción `Exit Function` o `End Function`,  lo que permite asignar un valor previo y, si es necesario, se puede ajustar después.  
  
 Para obtener más información sobre cómo devolver valores, vea [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md).  Para obtener información sobre cómo devolver las matrices, vea [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Sintaxis de llamada  
 Para invocar a un procedimiento `Function` hay que incluir el nombre y los argumentos de éste en la parte derecha de una instrucción de asignación o en una expresión.  Debe suministrar valores para todos los argumentos que no sean opcionales e incluir la lista de argumentos entre paréntesis.  Si no se proporcionan argumentos, se puede omitir el paréntesis.  
  
 La sintaxis para llamar a un procedimiento `Function` es la siguiente:  
  
 *l*  `=` *functionname* `[(` *argumentlist* `)]`  
  
 `If ((`\(\(*functionname*`[(`*argumentlist*`)] / 3) <=`*expresión*`) Then`  
  
 Cuando se llama a un procedimiento `Function`, no es necesario utilizar su valor devuelto,  en cuyo caso se ejecutan todas las acciones de la función, pero se omite el valor devuelto.  Se suele llamar de esta forma al método <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.  
  
### Ejemplo de declaración y llamada  
 El siguiente procedimiento `Function` calcula la hipotenusa de un triángulo rectángulo a partir de los valores de los catetos.  
  
 [!code-vb[VbVbcnProcedures#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 El ejemplo siguiente muestra una llamada típica a `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Cómo: Crear un procedimiento que devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [Cómo: Devolver un valor de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [Cómo: Llamar a un procedimiento que devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)