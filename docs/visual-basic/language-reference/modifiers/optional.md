---
description: 'Más información acerca de: opcional (Visual Basic)'
title: Opcional
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: d9a61371364d87745203363dbc0a641cec9660a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666087"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)

Especifica que un argumento de procedimiento se puede omitir cuando se llama al procedimiento.

## <a name="remarks"></a>Observaciones

Para cada parámetro opcional, debe especificar una expresión constante como valor predeterminado de ese parámetro. Si la expresión se evalúa como [Nothing](../nothing.md), se usa el valor predeterminado del tipo de datos Value como valor predeterminado del parámetro.

Si la lista de parámetros contiene un parámetro opcional, cada parámetro que siga también debe ser opcional.

El modificador `Optional` se puede utilizar en los contextos siguientes:

- [Declare Statement](../statements/declare-statement.md)

- [Instrucción Function](../statements/function-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Instrucción Sub](../statements/sub-statement.md)

> [!NOTE]
> Cuando se llama a un procedimiento con o sin parámetros opcionales, se pueden pasar argumentos por posición o por nombre. Para obtener más información, vea [pasar argumentos por posición y por nombre](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).

> [!NOTE]
> También puede definir un procedimiento con parámetros opcionales mediante sobrecarga. Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepte el parámetro y otra que no lo sea. Para obtener más información, consulta [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).

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

- [Lista de parámetros](../statements/parameter-list.md)
- [Parámetros opcionales](../../programming-guide/language-features/procedures/optional-parameters.md)
- [Palabras clave](../keywords/index.md)
