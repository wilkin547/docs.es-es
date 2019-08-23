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
ms.openlocfilehash: 12c88db49dc7723fc269195e7d174bfa822c64d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963761"
---
# <a name="nothing-visual-basic"></a>Nothing (Visual Basic)
Representa el valor predeterminado de cualquier tipo de datos. En el caso de los tipos de referencia, `null` el valor predeterminado es la referencia. En el caso de los tipos de valor, el valor predeterminado depende de si el tipo de valor admite valores NULL.  
  
> [!NOTE]
> En el caso de los tipos de valor `Nothing` que no aceptan valores NULL `null` , C#en Visual Basic difiere de en. En Visual Basic, si establece una variable de un tipo de valor que no acepta valores NULL `Nothing`en, la variable se establece en el valor predeterminado para su tipo declarado. En C#, si asigna una variable de un tipo de valor que no acepta valores NULL `null`a, se produce un error en tiempo de compilación.  
  
## <a name="remarks"></a>Comentarios  
 `Nothing`representa el valor predeterminado de un tipo de datos. El valor predeterminado depende de si la variable es de un tipo de valor o de un tipo de referencia.  
  
 Una variable de un *tipo de valor* contiene directamente su valor. Los tipos de valor incluyen todos los tipos `Boolean`de `Char`datos `Date`numéricos,,,, todas las estructuras y todas las enumeraciones. Una variable de un *tipo de referencia* almacena una referencia a una instancia del objeto en memoria. Los tipos de referencia incluyen clases, matrices, delegados y cadenas. Para obtener más información, consulta [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Si una variable es de un tipo de valor, el comportamiento `Nothing` de depende de si la variable es de un tipo de datos que acepta valores NULL. Para representar un tipo de valor que acepta valores NULL `?` , agregue un modificador al nombre de tipo. La asignación `Nothing` a una variable que acepta valores NULL establece el valor `null`en. Para obtener más información y ejemplos, vea [tipos de valor que aceptan valores NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Si una variable es de un tipo de valor que no acepta valores NULL, si se `Nothing` asigna a, se establece en el valor predeterminado para su tipo declarado. Si ese tipo contiene miembros de variable, todos ellos se establecen en sus valores predeterminados. En el ejemplo siguiente se muestra esto para los tipos escalares.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 Si una variable es de un tipo de referencia, la asignación `Nothing` a la variable la establece en una `null` referencia del tipo de la variable. Una variable que se establece en una `null` referencia no está asociada a ningún objeto. En el siguiente ejemplo se muestra cómo hacerlo.  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 Al comprobar si una variable de referencia (o tipo de valor que acepta `null`valores NULL) es `= Nothing` , `<> Nothing`no utilice ni. Use `Is Nothing` siempre o `IsNot Nothing`.  
  
 En el caso de las cadenas de Visual Basic, la `Nothing`cadena vacía es igual a. Por lo `"" = Nothing` tanto, es true.  
  
 En el ejemplo siguiente se muestran comparaciones `Is` que `IsNot` usan los operadores y.  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 Si declara una variable sin usar una `As` cláusula y la establece en `Nothing`, la variable tiene un tipo de `Object`. Un ejemplo de esto es `Dim something = Nothing`. En este caso, se produce un error en tiempo `Option Strict` de compilación cuando `Option Infer` está activado y está desactivado.  
  
 Cuando se asigna `Nothing` a una variable de objeto, ya no hace referencia a ninguna instancia de objeto. Si la variable anteriormente hacía referencia a una instancia, si se establece `Nothing` en, no finaliza la propia instancia. La instancia se termina y se liberan los recursos de memoria y del sistema asociados a ella, solo después de que el recolector de elementos no utilizados (GC) detecte que no quedan referencias activas.  
  
 `Nothing`difiere del <xref:System.DBNull> objeto, que representa una variante no inicializada o una columna de base de datos inexistente.  
  
## <a name="see-also"></a>Vea también

- [Dim (instrucción)](../../visual-basic/language-reference/statements/dim-statement.md)
- [Duración del objeto: Cómo se crean y destruyen los objetos](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Duración en Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Is (operador)](../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot (operador)](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Tipos de valor que aceptan valores NULL](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
