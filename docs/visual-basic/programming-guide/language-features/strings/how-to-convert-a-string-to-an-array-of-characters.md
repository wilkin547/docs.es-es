---
title: Filtrar Convertir una cadena en una matriz de caracteres en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: 63368f41aec674922ae44a3f1c9816709b981c9b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974411"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Procedimiento Convertir una cadena en una matriz de caracteres en Visual Basic
A veces resulta útil tener información sobre los caracteres de la cadena y las posiciones de los caracteres dentro de la cadena, como cuando se está analizando una cadena. En este ejemplo muestra cómo puede obtener una matriz de los caracteres en una cadena mediante una llamada a la cadena <xref:System.String.ToCharArray%2A> método.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo dividir una cadena en un `Char` matriz y cómo dividir una cadena en un `String` matriz de sus caracteres de texto Unicode. La razón de esta distinción es que los caracteres de texto Unicode pueden estar compuestos de dos o más `Char` caracteres (por ejemplo, un par suplente o una combinación secuencia de caracteres). Para obtener más información, consulte <xref:System.Globalization.TextElementEnumerator> y [el estándar Unicode](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Ejemplo  
 Es más difícil dividir una cadena en sus caracteres de texto Unicode, pero esto es necesario si necesita información sobre la representación visual de una cadena. Este ejemplo se usa el <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> método para obtener información acerca de los caracteres de texto Unicode que componen una cadena.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Cómo: Acceso a caracteres en cadenas](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [Conversión entre cadenas y otros tipos de datos en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
