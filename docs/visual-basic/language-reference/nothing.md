---
title: Nothing (palabra clave)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 3bd4681341a33cc8db4ecbc2b284be243db56549
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344173"
---
# <a name="nothing-keyword-visual-basic"></a>Palabra clave Nothing (Visual Basic)

Representa el valor predeterminado de cualquier tipo de datos. En el caso de los tipos de referencia, el valor predeterminado es la referencia `null`. En el caso de los tipos de valor, el valor predeterminado depende de si el tipo de valor admite valores NULL.

> [!NOTE]
> En el caso de los tipos de valor que no aceptan valores NULL, `Nothing` en C#Visual Basic difiere de `null` en. En Visual Basic, si establece una variable de un tipo de valor que no acepta valores NULL en `Nothing`, la variable se establece en el valor predeterminado para su tipo declarado. En C#, si asigna una variable de un tipo de valor que no acepta valores null a `null`, se producirá un error en tiempo de compilación.

## <a name="remarks"></a>Comentarios

`Nothing` representa el valor predeterminado de un tipo de datos. El valor predeterminado depende de si la variable es de un tipo de valor o de un tipo de referencia.

Una variable de un *tipo de valor* contiene directamente su valor. Entre los tipos de valor se incluyen todos los tipos de datos numéricos, `Boolean`, `Char`, `Date`, todas las estructuras y todas las enumeraciones. Una variable de un *tipo de referencia* almacena una referencia a una instancia del objeto en memoria. Los tipos de referencia incluyen clases, matrices, delegados y cadenas. Para obtener más información, consulta [Value Types and Reference Types](../programming-guide/language-features/data-types/value-types-and-reference-types.md).

Si una variable es de un tipo de valor, el comportamiento de `Nothing` depende de si la variable es de un tipo de datos que acepta valores NULL. Para representar un tipo de valor que acepta valores NULL, agregue un modificador `?` al nombre de tipo. La asignación de `Nothing` a una variable que acepta valores NULL establece el valor en `null`. Para obtener más información y ejemplos, vea [tipos de valor que aceptan valores NULL](../programming-guide/language-features/data-types/nullable-value-types.md).

Si una variable es de un tipo de valor que no acepta valores NULL, si se asigna `Nothing`, se establece en el valor predeterminado para su tipo declarado. Si ese tipo contiene miembros de variable, todos ellos se establecen en sus valores predeterminados. En el ejemplo siguiente se muestra esto para los tipos escalares.

[!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]

Si una variable es de un tipo de referencia, la asignación de `Nothing` a la variable la establece en una referencia `null` del tipo de la variable. Una variable que se establece en una referencia `null` no está asociada a ningún objeto. En el siguiente ejemplo se muestra esto:

[!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]

Al comprobar si una variable de referencia (o tipo de valor que acepta valores NULL) está `null`, no use `= Nothing` ni `<> Nothing`. Utilice siempre `Is Nothing` o `IsNot Nothing`.

En el caso de las cadenas de Visual Basic, la cadena vacía es igual a `Nothing`. Por lo tanto, `"" = Nothing` es true.

En el ejemplo siguiente se muestran comparaciones que usan los operadores `Is` y `IsNot`:

[!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]

Si declara una variable sin usar una cláusula `As` y la establece en `Nothing`, la variable tiene un tipo de `Object`. Un ejemplo de esto es `Dim something = Nothing`. En este caso, se produce un error en tiempo de compilación cuando `Option Strict` está activada y `Option Infer` está desactivada.

Cuando asigna `Nothing` a una variable de objeto, ya no hace referencia a ninguna instancia de objeto. Si la variable anteriormente hacía referencia a una instancia, si se establece en `Nothing` no finaliza la propia instancia. La instancia se termina y se liberan los recursos de memoria y del sistema asociados a ella, solo después de que el recolector de elementos no utilizados (GC) detecte que no quedan referencias activas.

`Nothing` difiere del objeto <xref:System.DBNull>, que representa una variante no inicializada o una columna de base de datos inexistente.

## <a name="see-also"></a>Vea también

- [Dim (instrucción)](./statements/dim-statement.md)
- [Duración de los objetos: cómo se crean y destruyen](../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Duración en Visual Basic](../programming-guide/language-features/declared-elements/lifetime.md)
- [Is (operador)](./operators/is-operator.md)
- [IsNot (operador)](./operators/isnot-operator.md)
- [Tipos de valor que aceptan valores NULL](../programming-guide/language-features/data-types/nullable-value-types.md)
