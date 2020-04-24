---
title: 'Cómo: crear cadenas con StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645322"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Cómo: crear cadenas mediante StringBuilder en Visual Basic

En este ejemplo se construye una cadena <xref:System.Text.StringBuilder> larga a partir de muchas cadenas más pequeñas mediante la clase. La <xref:System.Text.StringBuilder> clase es más `&=` eficaz que el operador para concatenar muchas cadenas.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente <xref:System.Text.StringBuilder> se crea una instancia de la clase, se anexan 1.000 cadenas a esa instancia y, a continuación, se devuelve su representación de cadena:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>Consulte también

- [Uso de la clase StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [&- Operador](../../../language-reference/operators/and-assignment-operator.md)
- [Cadenas](index.md)
- [Creación de cadenas](../../../../standard/base-types/creating-new.md)
- [Manipulación de cadenas](../../../../standard/base-types/best-practices-strings.md)
