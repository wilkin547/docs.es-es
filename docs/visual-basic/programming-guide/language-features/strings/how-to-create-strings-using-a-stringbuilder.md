---
description: 'Más información acerca de cómo: crear cadenas mediante StringBuilder en Visual Basic'
title: 'Cómo: crear cadenas mediante StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 6def32517f71ec3c2a7795c3395e3e572903ce1e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429824"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Cómo: crear cadenas mediante StringBuilder en Visual Basic

Este ejemplo crea una cadena larga a partir de muchas cadenas más pequeñas mediante la <xref:System.Text.StringBuilder> clase. La <xref:System.Text.StringBuilder> clase es más eficaz que el `&=` operador para concatenar muchas cadenas.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se crea una instancia de la <xref:System.Text.StringBuilder> clase, se anexan las cadenas 1.000 a esa instancia y, después, se devuelve su representación de cadena:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>Consulte también

- [Utilizar la clase StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [&= (operador)](../../../language-reference/operators/and-assignment-operator.md)
- [Cadenas](index.md)
- [Creación de cadenas](../../../../standard/base-types/creating-new.md)
- [Manipulación de cadenas](../../../../standard/base-types/best-practices-strings.md)
