---
description: 'Más información sobre: BC36629: no se admite la inferencia de tipos que aceptan valores NULL en este contexto'
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 915f964d55068f39b0468e2c47cc6e5538be1a6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795630"
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
