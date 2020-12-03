---
title: 'Cambio importante: NegotiateStream y SslStream permiten operaciones Begin sucesivas'
description: Obtenga información sobre el cambio importante en .NET 5.0 en el que los casos de error en las secuencias de seguridad se controlan de forma diferente, y las llamadas sucesivas a BeginAuthenticateAsServer o BeginAuthenticateAsClient ya no producen errores.
ms.date: 10/18/2020
ms.openlocfilehash: e0226d0f5586efca050ca3497ca1490fa21fd943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760142"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a>NegotiateStream y SslStream permiten operaciones Begin sucesivas

Los casos de error en las secuencias de seguridad se administran de forma diferente y es posible que las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` ya no produzcan errores.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` sin llamar primero a `EndAuthenticateAsServer` o `EndAuthenticateAsClient` dan como resultado una excepción <xref:System.NotSupportedException>. A partir de .NET 5.0, las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` ya no inician una excepción <xref:System.NotSupportedException>, porque estas API están respaldadas por una implementación basada en <xref:System.Threading.Tasks.Task>.

## <a name="reason-for-change"></a>Motivo del cambio

El cambio de la implementación interna del modelo de programación asincrónica (APM) a otro basado en <xref:System.Threading.Tasks.Task> mejora el rendimiento y reduce la complejidad del código.

## <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción por parte del desarrollador.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

### Category

Networking

-->
