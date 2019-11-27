---
title: 'Cómo: Obtener acceso a caracteres de cadenas'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352459"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Cómo: Obtener acceso a caracteres de cadenas en Visual Basic
En este ejemplo se muestra cómo utilizar la propiedad <xref:System.String.Chars%2A> para tener acceso al carácter que se encuentra en la ubicación especificada de una cadena.  
  
## <a name="example"></a>Ejemplo  
 A veces resulta útil tener datos sobre los caracteres de la cadena y las posiciones de esos caracteres dentro de la cadena. Puede pensar en una cadena como una matriz de caracteres (instancias`Char`); puede recuperar un carácter determinado haciendo referencia al índice de ese carácter a través de la propiedad <xref:System.String.Chars%2A>.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 El parámetro `index` de la propiedad <xref:System.String.Chars%2A> está basado en cero.  
  
## <a name="robust-programming"></a>Programación sólida  
 La propiedad <xref:System.String.Chars%2A> devuelve el carácter que se encuentra en la posición especificada. Sin embargo, algunos caracteres Unicode pueden estar representados por más de un carácter. Para obtener más información sobre cómo trabajar con caracteres Unicode, vea [Cómo: convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 La propiedad <xref:System.String.Chars%2A> produce una excepción <xref:System.IndexOutOfRangeException> si el parámetro `index` es mayor o igual que la longitud de la cadena, o si es menor que cero.  
  
## <a name="see-also"></a>Vea también

- <xref:System.String.Chars%2A>
- [Convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [Conversión entre cadenas y otros tipos de datos en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
