---
title: 'Cómo: recorrer en iteración una enumeración'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 6e8fd6760565a73d9d3b3d1d02fc872992eea354
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354024"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Cómo: Recorrer en iteración una enumeración en Visual Basic
Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres. Para recorrer en iteración una enumeración, puede moverla a una matriz mediante el método <xref:System.Enum.GetValues%2A>. También puede recorrer en iteración una enumeración mediante una instrucción `For...Each`, mediante el método <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> para extraer la cadena o el valor numérico.  
  
### <a name="to-iterate-through-an-enumeration"></a>Para recorrer en iteración una enumeración  
  
- Declare una matriz y convierta la enumeración en ella con el método <xref:System.Enum.GetValues%2A> antes de pasar la matriz como lo haría con cualquier otra variable. En el ejemplo siguiente se muestra cada miembro de la enumeración <xref:Microsoft.VisualBasic.FirstDayOfWeek> a medida que recorre en iteración la enumeración.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
