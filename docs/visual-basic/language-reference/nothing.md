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
ms.openlocfilehash: fb1af7d748faac78b26177af453a0e858f9e97c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Representa el valor predeterminado de cualquier tipo de datos. Para los tipos de referencia, el valor predeterminado es el `null` referencia. Para los tipos de valor, el valor predeterminado depende de si el tipo de valor es que aceptan valores NULL.  
  
> [!NOTE]
>  Para los tipos de valor no acepta valores NULL, `Nothing` en Visual Basic difiere de `null` en C#. En Visual Basic, si establece una variable de un tipo de valor no acepta valores NULL a `Nothing`, la variable se establece en el valor predeterminado de su tipo declarado. En C#, si asigna una variable de un tipo de valor no acepta valores NULL a `null`, se produce un error en tiempo de compilación.  
  
## <a name="remarks"></a>Comentarios  
 `Nothing` representa el valor predeterminado de un tipo de datos. El valor predeterminado depende de si la variable es de un tipo de valor o de un tipo de referencia.  
  
 Una variable de un *tipo de valor* contiene directamente su valor. Tipos de valor incluyen todos los tipos de datos numéricos, `Boolean`, `Char`, `Date`, todas las estructuras y todas las enumeraciones. Una variable de un *tipo de referencia* almacena una referencia a una instancia del objeto en la memoria. Tipos de referencia incluyen clases, matrices, delegados y cadenas. Para obtener más información, consulta [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Si una variable es de un valor de tipo, el comportamiento de `Nothing` depende de si la variable es de un tipo de datos que aceptan valores NULL. Para representar un tipo de valor que aceptan valores NULL, agregue un `?` modificador al nombre de tipo. Asignar `Nothing` a una variable que acepta valores NULL, Establece el valor en `null`. Para obtener más información y ejemplos, vea [tipos de valor que aceptan valores NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Si una variable es de un tipo de valor que no acepta valores NULL, asignando `Nothing` a establece en el valor predeterminado para su tipo declarado. Si ese tipo contiene a miembros de variables, están establecidos en sus valores predeterminados. En el ejemplo siguiente se muestra esto para tipos escalares.  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 Si una variable es de un tipo de referencia, asignando `Nothing` a la variable lo establece en un `null` referencia de tipo de la variable. Una variable que se establece en un `null` referencia no está asociada a ningún objeto. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 Al comprobar si una referencia (o tipo de valor que aceptan valores NULL) es variable `null`, no use `= Nothing` o `<> Nothing`. Utilice siempre `Is Nothing` o `IsNot Nothing`.  
  
 Para las cadenas en Visual Basic, la cadena vacía es igual a `Nothing`. Por lo tanto, `"" = Nothing` es true.  
  
 El ejemplo siguiente muestra las comparaciones que usan la `Is` y `IsNot` operadores.  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 Si se declara una variable sin utilizar un `As` cláusula y establézcalo en `Nothing`, la variable tiene un tipo de `Object`. Un ejemplo de esto es `Dim something = Nothing`. En este caso se produce un error de tiempo de compilación cuando `Option Strict` se encuentra en y `Option Infer` está desactivada.  
  
 Al asignar `Nothing` a una variable de objeto, ya no hace referencia a cualquier instancia de objeto. Si la variable anteriormente hacía referencia a una instancia, si se establece en `Nothing` no termina con la propia instancia. Finaliza la instancia y se liberan los recursos de memoria y del sistema asociados a él, solo una vez que el recolector de elementos no utilizados (GC) detecta que no hay quedan referencias activas.  
  
 `Nothing` difiere de la <xref:System.DBNull> objeto, que representa una variante no inicializada o una columna de base de datos no existe.  
  
## <a name="see-also"></a>Vea también  
 [Dim (instrucción)](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Duración de los objetos: cómo se crean y destruyen](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Duración en Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Is (operador)](../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot (operador)](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Tipos de valor que aceptan valores NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
