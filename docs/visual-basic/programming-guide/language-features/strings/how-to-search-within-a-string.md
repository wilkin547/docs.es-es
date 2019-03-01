---
title: Filtrar Buscar en una cadena (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: c150299efe07809d0d33edf882771f552c3e5b63
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982016"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Filtrar Buscar en una cadena (Visual Basic)
Este ejemplo llama a la <xref:System.String.IndexOf%2A> método en un <xref:System.String> objeto para informar del índice de la primera aparición de una subcadena.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un `Imports` instrucción que especifica el <xref:System> espacio de nombres. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programación sólida  
 El <xref:System.String.IndexOf%2A> método informa de la ubicación del primer carácter de la primera aparición de la subcadena. El índice está basado en 0, lo que significa que el primer carácter de una cadena tiene un índice de 0.  
  
 Si <xref:System.String.IndexOf%2A> no encuentra la subcadena, devuelve -1.  
  
 El <xref:System.String.IndexOf%2A> método distingue mayúsculas de minúsculas y utiliza la referencia cultural actual.  
  
 Para el control de errores óptimo, podría incluir la cadena de búsqueda en el `Try` block de un [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construcción.  
  
## <a name="see-also"></a>Vea también
- <xref:System.String.IndexOf%2A>
- [Try...Catch...Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
