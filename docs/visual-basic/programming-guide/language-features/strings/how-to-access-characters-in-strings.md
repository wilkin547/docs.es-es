---
title: 'Cómo: Obtener acceso a caracteres de cadenas en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 48507cade639660e6ce36697975d09fb29206c20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649157"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Cómo: Obtener acceso a caracteres de cadenas en Visual Basic
En este ejemplo se muestra cómo utilizar el <xref:System.String.Chars%2A> propiedad para tener acceso el carácter que ocupa la posición especificada en una cadena.  
  
## <a name="example"></a>Ejemplo  
 A veces resulta útil tener información sobre los caracteres de la cadena y las posiciones de los caracteres de la cadena. Se puede considerar una cadena como una matriz de caracteres (`Char` instancias); puede recuperar un carácter concreto haciendo referencia al índice de dicho carácter a través del <xref:System.String.Chars%2A> propiedad.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 El `index` parámetro de la <xref:System.String.Chars%2A> propiedad está basado en cero.  
  
## <a name="robust-programming"></a>Programación sólida  
 El <xref:System.String.Chars%2A> propiedad devuelve el carácter que ocupa la posición especificada. Sin embargo, algunos caracteres Unicode pueden representarse por más de un carácter. Para obtener más información sobre cómo trabajar con caracteres Unicode, vea [Cómo: convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 El <xref:System.String.Chars%2A> propiedad produce un <xref:System.IndexOutOfRangeException> excepción si el `index` parámetro es mayor o igual que la longitud de la cadena, o si es menor que cero  
  
## <a name="see-also"></a>Vea también  
 <xref:System.String.Chars%2A>  
 [Convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [Conversión entre cadenas y otros tipos de datos en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
