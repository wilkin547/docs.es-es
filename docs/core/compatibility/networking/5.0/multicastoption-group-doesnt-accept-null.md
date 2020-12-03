---
title: 'Cambio importante: MulticastOption.Group no acepta un valor NULL'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde MulticastOption.Group ya no acepta un valor NULL.
ms.date: 08/18/2020
ms.openlocfilehash: 164ac8c2c8dd14f9e0758017e54eeb377f88a7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760143"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a>MulticastOption.Group no acepta un valor NULL

<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> ya no acepta un valor de `null`. Si establece la propiedad en `null`, se inicia <xref:System.ArgumentNullException>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, puede establecer la propiedad <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> en `null`. Si después se pasa <xref:System.Net.Sockets.MulticastOption> a <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, el entorno de ejecución genera <xref:System.NullReferenceException>.

En .NET 5.0 y versiones posteriores, se genera <xref:System.ArgumentNullException> si establece la propiedad en `null`.

## <a name="reason-for-change"></a>Motivo del cambio

Por coherencia con las directrices de diseño de .NET Framework, la propiedad se ha actualizado para generar <xref:System.ArgumentNullException> si el valor es `null`.

## <a name="recommended-action"></a>Acción recomendada

Asegúrese de que no establece <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> en `null`.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
