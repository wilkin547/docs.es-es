---
title: Filtrar Acceso a caracteres en cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: f2831333008844c959c3625698fce6c485450683
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967560"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Filtrar Acceso a caracteres en cadenas en Visual Basic
Este ejemplo muestra cómo usar el <xref:System.String.Chars%2A> propiedad para tener acceso el carácter que ocupa la posición especificada en una cadena.  
  
## <a name="example"></a>Ejemplo  
 A veces resulta útil tener información sobre los caracteres de la cadena y las posiciones de los caracteres dentro de la cadena. Puede pensar en una cadena como una matriz de caracteres (`Char` instancias); puede recuperar un carácter concreto haciendo referencia al índice de dicho carácter a través de la <xref:System.String.Chars%2A> propiedad.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 El `index` parámetro de la <xref:System.String.Chars%2A> propiedad está basado en cero.  
  
## <a name="robust-programming"></a>Programación sólida  
 El <xref:System.String.Chars%2A> propiedad devuelve el carácter que ocupa la posición especificada. Sin embargo, algunos caracteres Unicode pueden representarse mediante más de un carácter. Para obtener más información sobre cómo trabajar con caracteres Unicode, vea [Cómo: Convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 El <xref:System.String.Chars%2A> propiedad produce una <xref:System.IndexOutOfRangeException> excepción si el `index` parámetro es mayor o igual que la longitud de la cadena, o si es menor que cero  
  
## <a name="see-also"></a>Vea también
- <xref:System.String.Chars%2A>
- [Cómo: Convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [Conversión entre cadenas y otros tipos de datos en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
