---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 3758f17634395236abf2cd7059418bf6f8b6c062
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630920"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)

Especifica que un argumento de procedimiento se puede omitir cuando se llama al procedimiento.

## <a name="remarks"></a>Comentarios

Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro. Si la expresión se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), se usa el valor predeterminado del tipo de datos Value como valor predeterminado del parámetro.

Si la lista de parámetros contiene un parámetro opcional, cada parámetro que siga también debe ser opcional.

El modificador `Optional` se puede utilizar en los contextos siguientes:

- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)

- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)

> [!NOTE]
> Cuando se llama a un procedimiento con o sin parámetros opcionales, se pueden pasar argumentos por posición o por nombre. Para obtener más información, vea [pasar argumentos por posición y por nombre](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).

> [!NOTE]
> También puede definir un procedimiento con parámetros opcionales mediante sobrecarga. Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepte el parámetro y otra que no lo sea. Para obtener más información, consulta [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define un procedimiento que tiene un parámetro opcional.

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo llamar a un procedimiento con argumentos pasados por posición y con argumentos pasados por nombre. El procedimiento tiene dos parámetros opcionales.

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a>Vea también

- [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
