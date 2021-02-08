---
description: "Más información acerca de: BC36532: la función anidada no tiene una signatura compatible con el delegado '<delegatename>"
title: La función anidada no tiene una signatura compatible con el delegado '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 2220faacdac065718a302ef7b086f99bf1e16cef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795669"
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
