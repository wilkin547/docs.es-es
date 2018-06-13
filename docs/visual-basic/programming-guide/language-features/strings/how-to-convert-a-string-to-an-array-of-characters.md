---
title: 'Cómo: Convertir una cadena en una matriz de caracteres en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: c109143601e304b1ec15a60c71d65fe6bd15aae8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648624"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Cómo: Convertir una cadena en una matriz de caracteres en Visual Basic
A veces resulta útil tener información sobre los caracteres de la cadena y las posiciones de los caracteres de la cadena, como cuando se está analizando una cadena. Este ejemplo muestra cómo puede obtener una matriz de los caracteres de una cadena mediante una llamada a la cadena <xref:System.String.ToCharArray%2A> método.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra cómo dividir una cadena en un `Char` matriz y cómo dividir una cadena en un `String` matriz de sus caracteres de texto Unicode. La razón de esta distinción es que los caracteres de texto Unicode pueden estar compuestos de dos o más `Char` caracteres (por ejemplo, un par suplente o una combinación de secuencia de caracteres). Para obtener más información, consulte <xref:System.Globalization.TextElementEnumerator> y "El estándar Unicode" en http://www.unicode.org.  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 Es más difícil dividir una cadena en sus caracteres de texto Unicode, pero esto es necesario si necesita información sobre la representación visual de una cadena. Este ejemplo se utiliza la <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> método para obtener información acerca de los caracteres de texto Unicode que constituyen una cadena.  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [Obtener acceso a caracteres de cadenas](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [Conversión entre cadenas y otros tipos de datos en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
