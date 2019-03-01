---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: b8dfc166681dbadf1d2f4ba5a985011f5427f50a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981431"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Representa el valor predeterminado de cualquier tipo de datos. Tipos de referencia, el valor predeterminado es el `null` referencia. Para los tipos de valor, el valor predeterminado depende de si el tipo de valor es que acepta valores NULL.  
  
> [!NOTE]
>  Para los tipos de valor distinto de null, `Nothing` en Visual Basic difiere `null` en C#. En Visual Basic, si establece una variable de un tipo de valor distinto de NULL para `Nothing`, la variable se establece en el valor predeterminado de su tipo declarado. En C#, si asigna una variable de un tipo de valor distinto de NULL en `null`, se produce un error de tiempo de compilación.  
  
## <a name="remarks"></a>Comentarios  
 `Nothing` representa el valor predeterminado de un tipo de datos. El valor predeterminado depende de si la variable es de un tipo de valor o de un tipo de referencia.  
  
 Una variable de un *tipo de valor* contiene directamente su valor. Tipos de valor incluyen todos los tipos de datos numéricos, `Boolean`, `Char`, `Date`, todas las estructuras y todas las enumeraciones. Una variable de un *tipo de referencia* almacena una referencia a una instancia del objeto en memoria. Tipos de referencia incluyen clases, delegados, matrices y cadenas. Para obtener más información, consulta [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Si una variable es de un valor de tipo, el comportamiento de `Nothing` depende de si la variable es de tipo de datos que acepta valores NULL. Para representar un tipo de valor que acepta valores NULL, agregue un `?` modificador para el nombre de tipo. Asignar `Nothing` a una variable que acepta valores NULL, Establece el valor en `null`. Para obtener más información y ejemplos, vea [los tipos de valor que acepta valores NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Si una variable es de un tipo de valor que no acepta valores NULL, asignando `Nothing` para lo establece en el valor predeterminado de su tipo declarado. Si ese tipo contiene a miembros de variable, están establecidos en sus valores predeterminados. El ejemplo siguiente muestra para tipos escalares.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 Si una variable es de un tipo de referencia, asignando `Nothing` a la variable lo establece en un `null` referencia del tipo de variable. Una variable que se establece en un `null` referencia no está asociada con ningún objeto. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 Al comprobar si una referencia (o el tipo de valor que acepta valores NULL) es la variable `null`, no use `= Nothing` o `<> Nothing`. Utilice siempre `Is Nothing` o `IsNot Nothing`.  
  
 Para las cadenas en Visual Basic, la cadena vacía es igual a `Nothing`. Por lo tanto, `"" = Nothing` es true.  
  
 El ejemplo siguiente muestra las comparaciones que usan la `Is` y `IsNot` operadores.  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 Si declara una variable sin usar un `As` cláusula y establézcalo en `Nothing`, la variable tiene un tipo de `Object`. Un ejemplo de esto es `Dim something = Nothing`. En este caso se produce un error de tiempo de compilación cuando `Option Strict` está activado y `Option Infer` está desactivada.  
  
 Al asignar `Nothing` a una variable de objeto, ya no hace referencia a cualquier instancia de objeto. Si la variable anteriormente hacía referencia a una instancia, si se establece en `Nothing` no finaliza la instancia de sí mismo. Finaliza la instancia y se liberan los recursos de memoria y el sistema asociados con él, solo una vez que el recolector de elementos no utilizados (GC) detecta que no hay quedan referencias activas.  
  
 `Nothing` difiere de la <xref:System.DBNull> objeto, que representa una variante no inicializada o una columna de base de datos que no existe.  
  
## <a name="see-also"></a>Vea también
- [Dim (instrucción)](../../visual-basic/language-reference/statements/dim-statement.md)
- [Duración del objeto: ¿Cómo se crean y destruyen objetos](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Duración en Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Is (operador)](../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot (operador)](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Tipos de valor que aceptan valores NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
