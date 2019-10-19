---
title: El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 2ed3a10cdf941bb8d1d7c00379736e04e8cad4d7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583182"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'

La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar. El método de extensión puede ser un procedimiento `Sub` o un procedimiento `Function`. Todos los métodos de extensión se deben marcar con el atributo de extensión, `<Extension()>`, del espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>. Opcionalmente, un módulo que contiene un método de extensión se puede marcar de la misma manera. Ningún otro uso del atributo de extensión es válido.

**Identificador de error:** BC36550

## <a name="to-correct-this-error"></a>Para corregir este error

- Quite el atributo de extensión.

- Rediseñe la extensión como un método, definido en un módulo envolvente.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define un método `Print` para el tipo de datos `String`.

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a>Vea también

- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Métodos de extensión](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
