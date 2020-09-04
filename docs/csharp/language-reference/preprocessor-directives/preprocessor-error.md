---
description: '#error: Referencia de C#'
title: '#error: Referencia de C#'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138103"
---
# <a name="error-c-reference"></a>#error (Referencia de C#)

`#error` permite generar un error [CS1029](../compiler-messages/cs1029.md) definido por el usuario desde una ubicación específica en el código. Por ejemplo:

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> El compilador trata `#error version` de forma especial e informa de un error del compilador, CS8304, con un mensaje que contiene las versiones que se usan del compilador y del lenguaje.

## <a name="remarks"></a>Observaciones

Un uso común de `#error` es en una directiva condicional.

También es posible generar una advertencia definida por el usuario con [#warning](./preprocessor-warning.md).

## <a name="example"></a>Ejemplo

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
