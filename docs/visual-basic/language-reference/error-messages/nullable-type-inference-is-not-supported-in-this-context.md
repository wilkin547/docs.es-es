---
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 610d2dc427d882c412b87eb67f021a8a86025f25
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159933"
---
# <a name="bc36629-nullable-type-inference-is-not-supported-in-this-context"></a>BC36629: no se admite la inferencia de tipos que aceptan valores NULL en este contexto

Los tipos de valor y las estructuras se pueden declarar como valores NULL.

```vb
Dim a? As Integer
Dim b As Integer?
```

 Sin embargo, no puede utilizar la declaración que acepta valores NULL en combinación con la inferencia de tipos. En los ejemplos siguientes se produce este error.

```vb
' Not valid.
' Dim c? = 10
' Dim d? = a
```

 **Identificador de error:** BC36629

## <a name="to-correct-this-error"></a>Para corregir este error

- Use una `As` cláusula para declarar la variable como un tipo de valor que acepta valores NULL.

## <a name="see-also"></a>Vea también

- [Tipos de valor que aceptan valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Inferencia de tipo de variable local](../../programming-guide/language-features/variables/local-type-inference.md)
