---
title: "Mid (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.MidB"
  - "vb.Mid"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Mid (instrucción)"
  - "cadenas [Visual Basic], reemplazar"
  - "cadenas [Visual Basic], subcadenas"
  - "subcadenas, Mid (instrucción)"
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Mid (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sustituye un número especificado de caracteres de una variable `String` por los caracteres de otra cadena.  
  
## Sintaxis  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## Elementos  
 `Target`  
 Obligatorio.  Nombre de la variable `String` que se va a modificar.  
  
 `Start`  
 Obligatorio.  Expresión `Integer`.  Posición de carácter de `Target` donde comienza el reemplazo del texto.  `Start` usa un índice basado en uno.  
  
 `Length`  
 Opcional.  Expresión `Integer`.  Número de caracteres que se va a reemplazar.  Si se omite, se utilizará `String` por completo.  
  
 `StringExpression`  
 Obligatorio.  Expresión de tipo `String` que reemplaza parte de `Target`.  
  
## Excepciones  
  
|Tipo de excepción|Condition|  
|-----------------------|---------------|  
|<xref:System.ArgumentException>|`Start` \<\= 0 ó `Length` \<0.|  
  
## Comentarios  
 El número de caracteres reemplazado siempre es menor o igual que el número de caracteres de `Target`.  
  
 Visual Basic tiene una función <xref:Microsoft.VisualBasic.Strings.Mid%2A> y una instrucción `Mid`.  Ambos elementos actúan en un número especificado de caracteres de una cadena, pero la función `Mid` devuelve los caracteres, en tanto que la instrucción `Mid` los reemplaza.  Para obtener más información, vea <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  La instrucción `MidB` de versiones anteriores de Visual Basic devuelve una subcadena en bytes, en lugar de caracteres.  Se utiliza principalmente para convertir cadenas en aplicaciones de juegos de caracteres de doble byte \(DBCS\).  Todas las cadenas de Visual Basic están en Unicode y ya no se admite `MidB`.  
  
## Ejemplo  
 En este ejemplo se utiliza la instrucción `Mid` para reemplazar un número de caracteres específico de una variable de cadena por los caracteres de otra cadena.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## Requisitos  
 **Espacio de nombres:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Módulo:** `Strings`  
  
 **Ensamblado:** [!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime-md.md)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 [Cadenas](../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Introducción a las cadenas en Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)