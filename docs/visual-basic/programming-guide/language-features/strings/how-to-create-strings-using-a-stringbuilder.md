---
title: 'Cómo: crear cadenas mediante StringBuilder en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 19e036abc9d25ec7fdfd6c33ebb420ec4f503cbc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700104"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Cómo: crear cadenas mediante StringBuilder en Visual Basic

Este ejemplo crea una cadena larga a partir de muchas cadenas más pequeñas mediante la clase <xref:System.Text.StringBuilder>. La clase <xref:System.Text.StringBuilder> es más eficaz que el operador `&=` para concatenar muchas cadenas.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se crea una instancia de la clase <xref:System.Text.StringBuilder>, se anexan cadenas 1.000 a esa instancia y, después, se devuelve su representación de cadena:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>Vea también

- [Utilizar la clase StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [Operador &=](../../../language-reference/operators/and-assignment-operator.md)
- [Cadenas](index.md)
- [Creación de cadenas nuevas](../../../../standard/base-types/creating-new.md)
- [Manipular cadenas](../../../../standard/base-types/manipulating-strings.md)
