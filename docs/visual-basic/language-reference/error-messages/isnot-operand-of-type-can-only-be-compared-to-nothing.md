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
# <a name="bc32128-isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="ce968-102">BC32128: el operando ' IsNot ' de tipo ' TypeName ' solo se puede comparar con ' Nothing ', porque ' TypeName ' es un tipo que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="ce968-102">BC32128: 'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>

<span data-ttu-id="ce968-103">Una variable declarada como un tipo de valor que acepta valores NULL se ha comparado con una expresión distinta de `Nothing` con el `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="ce968-103">A variable declared as a nullable value type has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>

<span data-ttu-id="ce968-104">**Identificador de error:** BC32128</span><span class="sxs-lookup"><span data-stu-id="ce968-104">**Error ID:** BC32128</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ce968-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ce968-105">To correct this error</span></span>

<span data-ttu-id="ce968-106">Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` con el operador `IsNot` , llame al método `GetType` en el tipo que acepta valores NULL y compare el resultado con la expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce968-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a><span data-ttu-id="ce968-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce968-107">See also</span></span>

- [<span data-ttu-id="ce968-108">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="ce968-108">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="ce968-109">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="ce968-109">IsNot Operator</span></span>](../operators/isnot-operator.md)
