---
title: El operando 'IsNot' de tipo 'nombreDeTipo' solo se puede comparar con 'Nothing', porque 'nombreDeTipo' es un tipo que acepta valores NULL
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 084978c1e047eebd60149af63c0ec9a1135225be
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163342"
---
# <a name="bc32128-isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a>BC32128: el operando ' IsNot ' de tipo ' TypeName ' solo se puede comparar con ' Nothing ', porque ' TypeName ' es un tipo que acepta valores NULL

Una variable declarada como un tipo de valor que acepta valores NULL se ha comparado con una expresión distinta de `Nothing` con el `IsNot` operador.

**Identificador de error:** BC32128

## <a name="to-correct-this-error"></a>Para corregir este error

Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` con el operador `IsNot` , llame al método `GetType` en el tipo que acepta valores NULL y compare el resultado con la expresión, como se muestra en el ejemplo siguiente.

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a>Vea también

- [Tipos de valor que aceptan valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Operador IsNot](../operators/isnot-operator.md)
