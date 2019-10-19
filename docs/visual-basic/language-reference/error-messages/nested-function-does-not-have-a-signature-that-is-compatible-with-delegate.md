---
title: La función anidada no tiene una signatura compatible con el delegado '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: d65c8eab661675c955ff6562098248c04036d6e7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580644"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>La función anidada no tiene una signatura compatible con el delegado ' \<delegatename > '

Se ha asignado una expresión lambda a un delegado que tiene una firma no compatible. Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros de entero.

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

El error se produce si una expresión lambda con un argumento se declara como de tipo `Del`:

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

**Identificador de error:** BC36532

## <a name="to-correct-this-error"></a>Para corregir este error

Ajuste la definición de delegado o la expresión lambda asignada para que las firmas sean compatibles.

## <a name="see-also"></a>Vea también

- [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
