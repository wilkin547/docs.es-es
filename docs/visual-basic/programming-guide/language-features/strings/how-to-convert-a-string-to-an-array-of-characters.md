---
title: 'Cómo: Convertir una cadena en una matriz de caracteres'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: d2f7128f97e576d37216d3aa9736921f13f77004
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352443"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Cómo: Convertir una cadena en una matriz de caracteres en Visual Basic
A veces resulta útil tener datos sobre los caracteres de la cadena y las posiciones de esos caracteres dentro de la cadena, como cuando se analiza una cadena. En este ejemplo se muestra cómo se puede obtener una matriz de los caracteres de una cadena mediante una llamada al método <xref:System.String.ToCharArray%2A> de la cadena.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo dividir una cadena en una matriz de `Char` y cómo dividir una cadena en una matriz `String` de sus caracteres de texto Unicode. La razón de esta distinción es que los caracteres de texto Unicode pueden estar compuestos de dos o más caracteres `Char` (como un par suplente o una secuencia de caracteres combinable). Para obtener más información, vea <xref:System.Globalization.TextElementEnumerator> y [el estándar Unicode](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Ejemplo  
 Es más difícil dividir una cadena en sus caracteres de texto Unicode, pero esto es necesario si necesita información sobre la representación visual de una cadena. En este ejemplo se usa el método <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> para obtener información sobre los caracteres de texto Unicode que componen una cadena.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Obtener acceso a caracteres de cadenas](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [Conversión entre cadenas y otros tipos de datos en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
