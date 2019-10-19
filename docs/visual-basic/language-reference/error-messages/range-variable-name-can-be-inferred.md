---
title: El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: ca50ddd86cfbba8db0148ed315645714acabc18d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582421"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos

Un elemento de programación que toma uno o más argumentos se incluye en una consulta LINQ. El compilador no puede inferir una variable de rango de ese elemento de programación.

**Identificador de error:** BC36599

## <a name="to-correct-this-error"></a>Para corregir este error

Proporcione un nombre de variable explícito para el elemento de programación, tal y como se muestra en el código siguiente:

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
