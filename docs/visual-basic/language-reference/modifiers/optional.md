---
title: "Optional (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Optional"
  - "vb.optional"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Optional (palabra clave)"
  - "Optional (palabra clave), contextos"
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Optional (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifique que se puede omitir un argumento de procedimiento cuando se llama al procedimiento.  
  
## Comentarios  
 Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro.  Si la expresión se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el valor predeterminado del tipo de datos de valor se utiliza como valor predeterminado.  
  
 Si la lista de parámetros contiene un parámetro opcional, cada parámetro que lo sigue también debe ser opcional.  
  
 El modificador `Optional` se puede utilizar en estos contextos:  
  
-   [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  Al llamar a un procedimiento con o sin parámetros opcionales, puede pasar argumentos por posición o por nombre.  Para obtener más información, vea [Pasar argumentos por posición o por nombre](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  También puede definir un procedimiento con parámetros opcionales mediante la sobrecarga.  Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, el que acepta el parámetro y otro que no lo hace.  Para obtener más información, vea [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## Ejemplo  
 El ejemplo siguiente se define un procedimiento con un parámetro opcional.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo llamar a un procedimiento con los argumentos por posición y con los argumentos por nombre.  El procedimiento tiene dos parámetros opcionales.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## Vea también  
 [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)