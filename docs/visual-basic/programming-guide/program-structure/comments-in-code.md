---
title: "Comentarios en el c&#243;digo (Visual Basic) | Microsoft Docs"
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
  - "botones, comentar"
  - "botones, quitar comentarios"
  - "comentarios en código"
  - "comentarios en código, Visual Basic"
  - "Comment (botón)"
  - "comentarios"
  - "comentarios, en el código"
  - "comentarios, código de Visual Basic"
  - "REM (instrucción)"
  - "Uncomment (botón)"
  - "código de Visual Basic, comentarios"
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Comentarios en el c&#243;digo (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Cuando lea ejemplos de código, encontrará el símbolo de comentario \(`'`\).  Este símbolo solicita al compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] que pase por alto el texto que aparece a continuación o el *comentario*.  Los comentarios son notas cortas explicativas que se agregan al código para aportar mayor información a las personas que lo lean.  
  
 Una buena práctica de programación consiste en comenzar todos los procedimientos con un comentario breve que describe las características funcionales del procedimiento \(lo que hace\).  Esto ayuda al desarrollador y a los que puedan examinar el código.  Debería separar los detalles de implementación \(cómo lo hace el procedimiento\) de los comentarios que describen las características funcionales.  Al incluir detalles de implementación en la descripción, recuerde actualizarlos en el momento de actualizar la función.  
  
 Los comentarios pueden ir a continuación de una instrucción en la misma línea, o pueden ocupar una línea completa.  Ambas opciones quedan reflejadas en el código siguiente.  
  
 [!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 Si el comentario necesita más de una línea, utilice el símbolo de comentario en cada línea, como se muestra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## Instrucciones sobre los comentarios  
 La tabla siguiente proporciona directrices generales sobre los tipos de comentarios que pueden preceder una sección de código.  Se trata únicamente de sugerencias, ya que [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no tiene reglas obligatorias para agregar comentarios.  Escriba lo que considere más conveniente, para uso propio o para cualquier otra persona que lea el código.  
  
|||  
|-|-|  
|Tipo de comentario|Descripción del comentario|  
|Finalidad|Describe qué hace el procedimiento \(no cómo lo hace\).|  
|Suposiciones|Enumera cada variable externa, control, archivo abierto u otro elemento al cual el procedimiento tenga acceso.|  
|Efectos|Enumera cada variable externa, control o archivo que esté afectado, y el efecto que tienen \(únicamente si no es evidente\).|  
|Entradas|Especifica el propósito del argumento.|  
|Valores devueltos|Explica los valores que devuelve el procedimiento|  
  
 Recuerde los siguientes puntos:  
  
-   Cada declaración de variable importante debe incluir un comentario anterior que describa el uso de la variable que se declara.  
  
-   Las variables, controles y procedimientos deben tener un nombre lo suficientemente claro para asegurar que el uso de comentarios sólo sea necesario para detalles de implementación compleja.  
  
-   Después de la secuencia de continuación de línea no puede escribirse un comentario en la misma línea.  
  
 Para agregar o quitar símbolos de comentario de un bloque de código, seleccione una o varias líneas de código y elija los botones **Comentario** \(![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.png "vaCommentButton")\) y **Quitar marca de comentario** \(![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.png "vaUncommentButton")\) de la barra de herramientas de **edición**.  
  
> [!NOTE]
>  También puede agregar comentarios al código poniendo la palabra clave `REM` antes del texto.  Sin embargo, el símbolo `'` y los botones **Selección con comentarios** y **Selección sin comentarios** son más fáciles de utilizar y requieren menos espacio y memoria.  
  
## Vea también  
 [Documentar el código con comentarios XML](http://msdn.microsoft.com/magazine/dd722812.aspx)   
 [Cómo: Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)   
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)   
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [REM \(Instrucción\)](../../../visual-basic/language-reference/statements/rem-statement.md)