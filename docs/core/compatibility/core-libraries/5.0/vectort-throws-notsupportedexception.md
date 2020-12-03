---
title: 'Cambio importante: Vector<T> inicia una excepción NotSupportedException'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET, donde Vector<T> siempre inicia una excepción para los parámetros de tipo no admitidos.
ms.date: 11/01/2020
ms.openlocfilehash: 63db7c6b720735b180ed11098227b31a14008f74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760182"
---
# <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a>Vector\<T> siempre inicia una excepción NotSupportedException en el caso de tipos no admitidos

<xref:System.Numerics.Vector%601?displayProperty=nameWithType> ahora inicia siempre una excepción <xref:System.NotSupportedException> para los parámetros de tipo no admitidos.

## <a name="change-description"></a>Descripción del cambio

Antes, los miembros de <xref:System.Numerics.Vector%601> no siempre iniciaban una excepción <xref:System.NotSupportedException> cuando `T` era un [tipo no admitido](#unsupported-types). La excepción no se iniciaba siempre debido a las rutas de acceso de código que permitían la aceleración de hardware. Por ejemplo, `Vector<bool> + Vector<bool>` devolvía `default` en lugar de iniciar una excepción en plataformas que no tienen aceleración de hardware, como ARM32. En el caso de los tipos no admitidos, los miembros <xref:System.Numerics.Vector%601> exhibían un comportamiento incoherente en distintas plataformas y configuraciones de hardware.

A partir de .NET 5.0, los miembros <xref:System.Numerics.Vector%601> siempre inician una excepción <xref:System.NotSupportedException> en todas las configuraciones de hardware cuando `T` no es un tipo admitido.

### <a name="unsupported-types"></a>Tipos no admitidos

Los tipos admitidos del parámetro de tipo de <xref:System.Numerics.Vector%601> son:

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

Los tipos admitidos no han cambiado, pero pueden cambiar en el futuro.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

No utilice un tipo no admitido como parámetro de tipo de <xref:System.Numerics.Vector%601>.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Numerics.Vector%601?displayProperty=fullName> y todos sus miembros

<!--

#### Category

Core .NET libraries

### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
