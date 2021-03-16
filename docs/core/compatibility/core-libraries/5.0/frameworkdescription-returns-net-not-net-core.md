---
title: 'Cambio importante: El valor de FrameworkDescription es .NET en lugar de .NET Core'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET, donde RuntimeInformation.FrameworkDescription ahora devuelve ".NET" en lugar de ".NET Core".
ms.date: 11/01/2020
ms.openlocfilehash: 18aa9a30a149b3c38d4bbfe4a0c99446f4372f07
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257523"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a>El valor de FrameworkDescription es .NET en lugar de .NET Core

Ahora <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET" en lugar de ".NET Core".

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET Core" como parte de la cadena de descripción, por ejemplo, `.NET Core 3.1.1`.

A partir de .NET 5, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> devuelve ".NET" como parte de la cadena de descripción, por ejemplo, `.NET 5.0.0`.

## <a name="reason-for-change"></a>Motivo del cambio

Con .NET 5, `netcoreapp` se reemplaza por `net` como el moniker corto del marco de destino. Por coherencia, también se ha actualizado la descripción del marco. El cambio es cosmético, ya que `FrameworkName` solo se codifica en la propiedad <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Actualice cualquier código que busque ".NET Core" en la cadena devuelta por <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
