---
title: 'Cambio importante: Las comprobaciones intrínsecas de IsSupported de hardware pueden diferir en los tipos anidados'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde ahora la comprobación de objetos intrínsecos de hardware en X64.IsSupported puede generar un resultado diferente.
ms.date: 11/01/2020
ms.openlocfilehash: 9acef15860de76a9743621cb4c5edba5aac3931c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760201"
---
# <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a>Las comprobaciones intrínsecas de IsSupported de hardware pueden diferir en los tipos anidados

La comprobación de `<Isa>.X64.IsSupported`, donde `<Isa>` hace referencia a las clases del espacio de nombres <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType>, ahora puede generar un resultado diferente en versiones anteriores de .NET.

> [!TIP]
> *ISA* representa la arquitectura estándar del sector.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, algunos de los tipos intrínsecos de hardware de <xref:System.Runtime.Intrinsics.X86>, por ejemplo, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, no exponían una clase anidada de `X64` . Para estos tipos, la llamada a `<Isa>.X64.IsSupported` se resolvía en una propiedad `IsSupported` en una clase `X64` anidada de una clase principal `<Isa>`. Esto significaba que la propiedad podía devolver `true` incluso cuando `<Isa>.IsSupported` devuelve `false`.

En .NET 5.0 y versiones posteriores, todos los tipos <xref:System.Runtime.Intrinsics.X86> exponen una clase `X64` anidada que notifica correctamente la compatibilidad. Esto garantiza que la jerarquía general siga siendo correcta y que si `<Isa>.X64.IsSupported` es `true`, también se puede suponer que `<Isa>.IsSupported` es `true`.

## <a name="reason-for-change"></a>Motivo del cambio

Estaba previsto que, si `<Isa>.X64.IsSupported` es `true`, `<Isa>.IsSupported` debía ser `true`. Sin embargo, debido a cómo funciona la resolución de miembros en C#, las clases que no tenían una clase `X64` anidada exponían una situación en la que este no siempre era el caso y se generaban errores en el código de usuario.

## <a name="recommended-action"></a>Acción recomendada

Si es necesario, ajuste el código que comprueba `IsSupported` para buscar el ISA adecuado.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
