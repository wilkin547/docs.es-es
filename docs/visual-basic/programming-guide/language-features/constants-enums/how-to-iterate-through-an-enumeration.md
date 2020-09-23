---
title: Procedimiento para iterar una enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 21c170d4708b90987a3f1e9c18969b8803fcdbe0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058721"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>Cómo: Recorrer en iteración una enumeración en Visual Basic

Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres. Para recorrer en iteración una enumeración, puede moverla a una matriz mediante el <xref:System.Enum.GetValues%2A> método. También puede recorrer en iteración una enumeración mediante una `For...Each` instrucción, utilizando el <xref:System.Enum.GetNames%2A> <xref:System.Enum.GetValues%2A> método o para extraer la cadena o el valor numérico.  
  
### <a name="to-iterate-through-an-enumeration"></a>Para recorrer en iteración una enumeración  
  
- Declare una matriz y convierta la enumeración en ella con el <xref:System.Enum.GetValues%2A> método antes de pasar la matriz como lo haría con cualquier otra variable. En el ejemplo siguiente se muestra cada miembro de la enumeración <xref:Microsoft.VisualBasic.FirstDayOfWeek> a medida que recorre en iteración la enumeración.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre las enumeraciones](enumerations-overview.md)
- [Cómo: Declarar una enumeración](how-to-declare-enumerations.md)
- [Cuándo se debe utilizar una enumeración](when-to-use-an-enumeration.md)
- [Procedimiento para determinar la cadena asociada a un valor de enumeración](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Procedimiento para hacer referencia al miembro de una enumeración](how-to-refer-to-an-enumeration-member.md)
- [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
- [Matrices](../arrays/index.md)
