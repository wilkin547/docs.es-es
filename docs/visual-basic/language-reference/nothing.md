---
description: 'Más información sobre: palabra clave Nothing (Visual Basic)'
title: Nothing (palabra clave)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: c77f39c0a431dd05aabd24a235fb2dc88ea29e69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674732"
---
# <a name="nothing-keyword-visual-basic"></a>Palabra clave Nothing (Visual Basic)

Representa el valor predeterminado de cualquier tipo de datos. En el caso de los tipos de referencia, el valor predeterminado es la `null` referencia. En el caso de los tipos de valor, el valor predeterminado depende de si el tipo de valor admite valores NULL.

> [!NOTE]
> En el caso de los tipos de valor que no aceptan valores NULL, `Nothing` en Visual Basic difiere de `null` en C#. En Visual Basic, si establece una variable de un tipo de valor que no acepta valores NULL en `Nothing` , la variable se establece en el valor predeterminado para su tipo declarado. En C#, si asigna una variable de un tipo de valor que no acepta valores NULL a `null` , se produce un error en tiempo de compilación.

## <a name="remarks"></a>Observaciones

`Nothing` representa el valor predeterminado de un tipo de datos. El valor predeterminado depende de si la variable es de un tipo de valor o de un tipo de referencia.

Una variable de un *tipo de valor* contiene directamente su valor. Los tipos de valor incluyen todos los tipos de datos numéricos,, `Boolean` `Char` , `Date` , todas las estructuras y todas las enumeraciones. Una variable de un *tipo de referencia* almacena una referencia a una instancia del objeto en memoria. Los tipos de referencia incluyen clases, matrices, delegados y cadenas. Para obtener más información, vea [tipos de valor y tipos de referencia](../programming-guide/language-features/data-types/value-types-and-reference-types.md).

Si una variable es de un tipo de valor, el comportamiento de `Nothing` depende de si la variable es de un tipo de datos que acepta valores NULL. Para representar un tipo de valor que acepta valores NULL, agregue un `?` modificador al nombre de tipo. `Nothing`La asignación a una variable que acepta valores NULL establece el valor en `null` . Para obtener más información y ejemplos, vea [tipos de valor que aceptan valores NULL](../programming-guide/language-features/data-types/nullable-value-types.md).

Si una variable es de un tipo de valor que no acepta valores NULL, si se asigna `Nothing` a, se establece en el valor predeterminado para su tipo declarado. Si ese tipo contiene miembros de variable, todos ellos se establecen en sus valores predeterminados. En el ejemplo siguiente se muestra esto para los tipos escalares.

[!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]

Si una variable es de un tipo de referencia, la asignación `Nothing` a la variable la establece en una `null` Referencia del tipo de la variable. Una variable que se establece en una `null` referencia no está asociada a ningún objeto. En el siguiente ejemplo se muestra esto:

[!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]

Al comprobar si una variable de referencia (o tipo de valor que acepta valores NULL) es `null` , no utilice `= Nothing` ni `<> Nothing` . Use siempre `Is Nothing` o `IsNot Nothing` .

En el caso de las cadenas de Visual Basic, la cadena vacía es igual a `Nothing` . Por lo tanto, `"" = Nothing` es true.

En el ejemplo siguiente se muestran comparaciones que usan los `Is` `IsNot` operadores y:

[!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]

Si declara una variable sin usar una `As` cláusula y la establece en `Nothing` , la variable tiene un tipo de `Object` . Un ejemplo de esto es `Dim something = Nothing` . En este caso, se produce un error en tiempo de compilación cuando `Option Strict` está activado y `Option Infer` está desactivado.

Cuando se asigna `Nothing` a una variable de objeto, ya no hace referencia a ninguna instancia de objeto. Si la variable anteriormente hacía referencia a una instancia, si se establece en, `Nothing` no finaliza la propia instancia. La instancia se termina y se liberan los recursos de memoria y del sistema asociados a ella, solo después de que el recolector de elementos no utilizados (GC) detecte que no quedan referencias activas.

`Nothing` difiere del <xref:System.DBNull> objeto, que representa una variante no inicializada o una columna de base de datos inexistente.

## <a name="see-also"></a>Vea también

- [Instrucción Dim](./statements/dim-statement.md)
- [Duración de los objetos: cómo se crean y destruyen](../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Período de duración en Visual Basic](../programming-guide/language-features/declared-elements/lifetime.md)
- [Operador Is](./operators/is-operator.md)
- [Operador IsNot](./operators/isnot-operator.md)
- [Tipos de valor que aceptan valores NULL](../programming-guide/language-features/data-types/nullable-value-types.md)
