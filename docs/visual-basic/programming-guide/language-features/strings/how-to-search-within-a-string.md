---
description: 'Más información acerca de cómo: buscar dentro de una cadena (Visual Basic)'
title: 'Cómo: buscar en una cadena'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: dab9faf91eef2e6d845805693227e1a6735ec796
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429734"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Cómo: buscar en una cadena (Visual Basic)

En este artículo se muestra un ejemplo de cómo buscar dentro de una cadena en Visual Basic.

## <a name="example"></a>Ejemplo

En este ejemplo se llama al <xref:System.String.IndexOf%2A> método en un <xref:System.String> objeto para notificar el índice de la primera aparición de una subcadena:

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a>Programación sólida

El <xref:System.String.IndexOf%2A> método devuelve la ubicación del primer carácter de la primera aparición de la subcadena. El índice es de base 0, lo que significa que el primer carácter de una cadena tiene un índice de 0.

Si <xref:System.String.IndexOf%2A> no encuentra la subcadena, devuelve-1.

El <xref:System.String.IndexOf%2A> método distingue entre mayúsculas y minúsculas y usa la referencia cultural actual.

Para un control de errores óptimo, es posible que desee incluir la búsqueda de cadenas en el `Try` bloque de una [instrucción try... Detectar... Construcción de la instrucción Finally](../../../language-reference/statements/try-catch-finally-statement.md) .

## <a name="see-also"></a>Vea también

- <xref:System.String.IndexOf%2A>
- [Try...Catch...Finally (instrucción)](../../../language-reference/statements/try-catch-finally-statement.md)
- [Introducción a las cadenas en Visual Basic](introduction-to-strings.md)
- [Cadenas](index.md)
