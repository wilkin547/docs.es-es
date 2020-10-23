---
ms.openlocfilehash: 16994e9cd97b31a30c8c5ce49d2042ff79b3f60b
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050535"
---
### <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="502bc-101">NegotiateStream y SslStream permiten operaciones Begin sucesivas</span><span class="sxs-lookup"><span data-stu-id="502bc-101">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="502bc-102">Los casos de error en las secuencias de seguridad se administran de forma diferente y es posible que las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` ya no produzcan errores.</span><span class="sxs-lookup"><span data-stu-id="502bc-102">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="502bc-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="502bc-103">Version introduced</span></span>

<span data-ttu-id="502bc-104">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="502bc-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="502bc-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="502bc-105">Change description</span></span>

<span data-ttu-id="502bc-106">En versiones anteriores de .NET, las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` sin llamar primero a `EndAuthenticateAsServer` o `EndAuthenticateAsClient` dan como resultado una excepción <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="502bc-106">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="502bc-107">A partir de .NET 5.0, las llamadas sucesivas a `BeginAuthenticateAsServer` o `BeginAuthenticateAsClient` ya no inician una excepción <xref:System.NotSupportedException>, porque estas API están respaldadas por una implementación basada en <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="502bc-107">Starting in .NET 5.0, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="502bc-108">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="502bc-108">Reason for change</span></span>

<span data-ttu-id="502bc-109">El cambio de la implementación interna del modelo de programación asincrónica (APM) a otro basado en <xref:System.Threading.Tasks.Task> mejora el rendimiento y reduce la complejidad del código.</span><span class="sxs-lookup"><span data-stu-id="502bc-109">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="502bc-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="502bc-110">Recommended action</span></span>

<span data-ttu-id="502bc-111">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="502bc-111">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="502bc-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="502bc-112">Category</span></span>

<span data-ttu-id="502bc-113">Redes</span><span class="sxs-lookup"><span data-stu-id="502bc-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="502bc-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="502bc-114">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

-->
