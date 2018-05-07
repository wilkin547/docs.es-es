---
title: 'Cómo: Buscar en una cadena (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 08a005f2927a76c9b29c1ff0092ea8282188b2b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Cómo: Buscar en una cadena (Visual Basic)
Este ejemplo llama a la <xref:System.String.IndexOf%2A> método en un <xref:System.String> objeto para informar del índice de la primera aparición de una subcadena.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un `Imports` instrucción especificando la <xref:System> espacio de nombres. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programación sólida  
 El <xref:System.String.IndexOf%2A> método notifica la ubicación del primer carácter de la primera aparición de la subcadena. El índice está basado en 0, lo que significa que el primer carácter de una cadena tiene un índice de 0.  
  
 Si <xref:System.String.IndexOf%2A> no encuentra la subcadena, devuelve -1.  
  
 El <xref:System.String.IndexOf%2A> método distingue entre mayúsculas y minúsculas y utiliza la referencia cultural actual.  
  
 Para un control óptimo de errores, debe incluir la búsqueda de cadena en el `Try` bloquear de un [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construcción.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.String.IndexOf%2A>  
 [Try...Catch...Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
