---
title: Procedimiento Crear cadenas mediante un objeto StringBuilder en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834197"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Procedimiento Crear cadenas mediante un objeto StringBuilder en Visual Basic
En este ejemplo se crea una cadena larga en varias cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase. El <xref:System.Text.StringBuilder> clase es más eficaz que el `&=` operador para concatenar muchas cadenas.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> (clase), anexa 1.000 cadenas a esa instancia y, a continuación, devuelve su representación de cadena.  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a>Vea también

- [Utilizar la clase StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [Operador &=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Cadenas](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Creación de cadenas nuevas](../../../../standard/base-types/creating-new.md)
- [Manipular cadenas](../../../../standard/base-types/manipulating-strings.md)
