---
title: La función anidada no tiene una signatura compatible con el delegado '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 0dde340164f1ba80d0e1d9fbb5d17ba6da0a5bc4
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160059"
---
# <a name="bc36532-nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>BC36532: la función anidada no tiene una signatura compatible con el delegado ' \<delegatename> '

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

## <a name="see-also"></a>Vea también

- [Conversión de delegado flexible](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
