---
title: La función anidada no tiene una signatura compatible con el delegado '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 28d07f01c0fd467cb68d73749988273eee95edf4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409431"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>La función anidada no tiene una signatura compatible con el delegado '\<delegatename>'

Se ha asignado una expresión lambda a un delegado que tiene una firma no compatible. Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros enteros.

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

El error se produce si una expresión lambda con un argumento se declara como tipo `Del` :

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

**Identificador de error:** BC36532

## <a name="to-correct-this-error"></a>Para corregir este error

Ajuste la definición de delegado o la expresión lambda asignada para que las firmas sean compatibles.

## <a name="see-also"></a>Consulte también

- [Conversión de delegado flexible](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
