---
description: '#pragma warning: Referencia de C#'
title: '#pragma warning: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 16582a74bd34f2c0d89950280f1d5fde25435eea
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99215997"
---
# <a name="pragma-warning-c-reference"></a>#pragma warning (Referencia de C#)

`#pragma warning` puede habilitar o deshabilitar determinadas advertencias.

## <a name="syntax"></a>Sintaxis

```csharp
#pragma warning disable warning-list
#pragma warning restore warning-list
```

## <a name="parameters"></a>Parámetros

 `warning-list` Una lista separada por comas de números de advertencia. El prefijo "CS" es opcional.

 Cuando no se especifica ningún número de advertencia, `disable` deshabilita todas las advertencias y `restore` habilita todas las advertencias.

> [!NOTE]
> Para buscar los números de advertencia en Visual Studio, compile el proyecto y después busque los números de advertencia en la ventana **Salida**.

## <a name="example"></a>Ejemplo

```csharp
// pragma_warning.cs
using System;

#pragma warning disable 414, CS3021
[CLSCompliant(false)]
public class C
{
    int i = 1;
    static void Main()
    {
    }
}
#pragma warning restore CS3021
[CLSCompliant(false)]  // CS3021
public class D
{
    int i = 1;
    public static void F()
    {
    }
}
```

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
- [Errores del compilador de C#](../compiler-messages/index.md)
- [Procedimiento para suprimir advertencias de análisis de código](../../../fundamentals/code-analysis/suppress-warnings.md)
