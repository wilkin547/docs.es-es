---
description: 'Más información sobre: Cómo: etiquetar instrucciones (Visual Basic)'
title: Procedimiento Instrucciones de etiquetas
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 4efb320dad7d52f6e9b94f6e6f81730f94b5966b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433257"
---
# <a name="how-to-label-statements-visual-basic"></a>Cómo: Aplicar etiquetas a las instrucciones (Visual Basic)

Los bloques de instrucciones se componen de líneas de código delimitadas por dos puntos. Se dice que las líneas de código precedidas de una cadena o un entero de identificación están *etiquetadas*. Las etiquetas de instrucción se usan para marcar una línea de código para identificarla para su uso con instrucciones como `On Error Goto` .

Las etiquetas pueden ser válidas Visual Basic identificadores, como los que identifican elementos de programación, o literales enteros. Una etiqueta debe aparecer al principio de una línea de código fuente y debe ir seguida de dos puntos, independientemente de si va seguido de una instrucción en la misma línea.

El compilador identifica las etiquetas comprobando si el principio de la línea coincide con cualquier identificador ya definido. Si no es así, el compilador supone que es una etiqueta.

Las etiquetas tienen su propio espacio de declaración y no interfieren con otros identificadores. El ámbito de una etiqueta es el cuerpo del método. La declaración de etiqueta tiene prioridad en cualquier situación ambigua.

> [!NOTE]
> Las etiquetas solo se pueden usar en instrucciones ejecutables dentro de métodos.

## <a name="to-label-a-line-of-code"></a>Para etiquetar una línea de código

Coloque un identificador seguido de un signo de dos puntos, al principio de la línea de código fuente.

Por ejemplo, las siguientes líneas de código se etiquetan con `Jump` y `120` , respectivamente:

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a>Vea también

- [Instrucciones](../language-features/statements.md)
- [Declared Element Names](../language-features/declared-elements/declared-element-names.md)
- [Convenciones de código y estructura de programas](program-structure-and-code-conventions.md)
