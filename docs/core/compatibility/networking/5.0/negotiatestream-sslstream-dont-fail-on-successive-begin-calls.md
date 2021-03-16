---
title: 'Cambio importante: NegotiateStream y SslStream permiten operaciones Begin sucesivas'
description: Obtenga información sobre el cambio importante en .NET 5 en el que los casos de error en las secuencias de seguridad se controlan de forma diferente, y las llamadas sucesivas a BeginAuthenticateAsServer o BeginAuthenticateAsClient ya no producen errores.
ms.date: 10/18/2020
ms.openlocfilehash: 5c042be01873849cc154111a31fc007521508c7b
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256444"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="eeb48-103">NegotiateStream y SslStream permiten operaciones Begin sucesivas</span><span class="sxs-lookup"><span data-stu-id="eeb48-103">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="eeb48-104">Los casos de error en las secuencias de seguridad se administran de forma diferente y es posible que las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` ya no produzcan errores.</span><span class="sxs-lookup"><span data-stu-id="eeb48-104">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="eeb48-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="eeb48-105">Version introduced</span></span>

<span data-ttu-id="eeb48-106">5.0</span><span class="sxs-lookup"><span data-stu-id="eeb48-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="eeb48-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="eeb48-107">Change description</span></span>

<span data-ttu-id="eeb48-108">En versiones anteriores de .NET, las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` sin llamar primero a `EndAuthenticateAsServer` o `EndAuthenticateAsClient` dan como resultado una excepción <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="eeb48-108">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="eeb48-109">A partir de .NET 5, las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` ya no inician una excepción <xref:System.NotSupportedException>, porque estas API están respaldadas por una implementación basada en <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="eeb48-109">Starting in .NET 5, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="eeb48-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="eeb48-110">Reason for change</span></span>

<span data-ttu-id="eeb48-111">El cambio de la implementación interna del modelo de programación asincrónica (APM) a otro basado en <xref:System.Threading.Tasks.Task> mejora el rendimiento y reduce la complejidad del código.</span><span class="sxs-lookup"><span data-stu-id="eeb48-111">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="eeb48-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="eeb48-112">Recommended action</span></span>

<span data-ttu-id="eeb48-113">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="eeb48-113">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="eeb48-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="eeb48-114">Affected APIs</span></span>

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
