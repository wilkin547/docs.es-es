---
title: El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 9b8f49c498699a8f7d1c4b329e82258501aa0c47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363103"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'

La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar. El método de extensión puede ser un `Sub` procedimiento o un `Function` procedimiento. Todos los métodos de extensión se deben marcar con el atributo `<Extension()>` de extensión,, del <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres. Opcionalmente, un módulo que contiene un método de extensión se puede marcar de la misma manera. Ningún otro uso del atributo de extensión es válido.

**Identificador de error:** BC36550

## <a name="to-correct-this-error"></a>Para corregir este error

- Quite el atributo de extensión.

- Rediseñe la extensión como un método, definido en un módulo envolvente.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define un `Print` método para el `String` tipo de datos.

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

## <a name="see-also"></a>Consulte también

- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
- [Métodos de extensión](../../programming-guide/language-features/procedures/extension-methods.md)
- [Module (Instrucción)](../statements/module-statement.md)
