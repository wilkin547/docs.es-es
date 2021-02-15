---
description: 'Más información sobre: Cómo: convertir una cadena en una matriz de caracteres en Visual Basic'
title: Procedimiento para convertir una cadena en una matriz de caracteres
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: f85b0801cf013e207eacd70a256a3ed0a8dc7887
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476155"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Cómo: Convertir una cadena en una matriz de caracteres en Visual Basic

A veces resulta útil tener datos sobre los caracteres de la cadena y las posiciones de esos caracteres dentro de la cadena, como cuando se analiza una cadena. En este ejemplo se muestra cómo se puede obtener una matriz de los caracteres de una cadena mediante una llamada al método de la cadena <xref:System.String.ToCharArray%2A> .  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se muestra cómo dividir una cadena en una `Char` matriz y cómo dividir una cadena en una `String` matriz de sus caracteres de texto Unicode. La razón de esta distinción es que los caracteres de texto Unicode pueden estar compuestos de dos o más `Char` caracteres (por ejemplo, un par suplente o una secuencia de caracteres de combinación). Para obtener más información, vea <xref:System.Globalization.TextElementEnumerator> y [el estándar Unicode](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Ejemplo  

 Es más difícil dividir una cadena en sus caracteres de texto Unicode, pero esto es necesario si necesita información sobre la representación visual de una cadena. En este ejemplo se utiliza el <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> método para obtener información sobre los caracteres de texto Unicode que componen una cadena.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Procedimiento para obtener acceso a caracteres de cadenas](how-to-access-characters-in-strings.md)
- [Conversión entre cadenas y otros tipos de datos en Visual Basic](converting-between-strings-and-other-data-types.md)
- [Cadenas](index.md)
