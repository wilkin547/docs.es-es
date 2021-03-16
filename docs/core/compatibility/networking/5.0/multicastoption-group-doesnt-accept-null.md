---
title: 'Cambio importante: MulticastOption.Group no acepta un valor NULL'
description: Obtenga información sobre el cambio importante en .NET 5, donde MulticastOption.Group ya no acepta un valor NULL.
ms.date: 08/18/2020
ms.openlocfilehash: 09c6415d275361abee8285aabdda13ccd9727043
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256457"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a>MulticastOption.Group no acepta un valor NULL

<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> ya no acepta un valor de `null`. Si establece la propiedad en `null`, se inicia <xref:System.ArgumentNullException>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, puede establecer la propiedad <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> en `null`. Si después se pasa <xref:System.Net.Sockets.MulticastOption> a <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, el entorno de ejecución genera <xref:System.NullReferenceException>.

En .NET 5 y versiones posteriores, se genera <xref:System.ArgumentNullException> si establece la propiedad en `null`.

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
