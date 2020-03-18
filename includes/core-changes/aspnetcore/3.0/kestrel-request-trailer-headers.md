---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393887"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a><span data-ttu-id="7c4a5-101">Kestrel: se han movido los encabezados de finalizador de solicitud a una nueva recopilación</span><span class="sxs-lookup"><span data-stu-id="7c4a5-101">Kestrel: Request trailer headers moved to new collection</span></span>

<span data-ttu-id="7c4a5-102">En versiones anteriores, Kestrel agregaba encabezados de finalizador fragmentados de HTTP/1.1 en la recopilación de encabezados de solicitud cuando el cuerpo de la solicitud se leía al final.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-102">In prior versions, Kestrel added HTTP/1.1 chunked trailer headers into the request headers collection when the request body was read to the end.</span></span> <span data-ttu-id="7c4a5-103">Este comportamiento provocó problemas de ambigüedad entre encabezados y finalizadores.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-103">This behavior caused concerns about ambiguity between headers and trailers.</span></span> <span data-ttu-id="7c4a5-104">Se tomó la decisión de mover los finalizadores a una nueva recopilación.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-104">The decision was made to move the trailers to a new collection.</span></span>

<span data-ttu-id="7c4a5-105">Los finalizadores de solicitudes HTTP/2 no estaban disponibles en ASP.NET Core 2.2, pero ahora también están disponibles en esta nueva recopilación en ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-105">HTTP/2 request trailers were unavailable in ASP.NET Core 2.2 but are now also available in this new collection in ASP.NET Core 3.0.</span></span>

<span data-ttu-id="7c4a5-106">Se han agregado métodos nuevos de extensión de solicitud para tener acceso a estos finalizadores.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-106">New request extension methods have been added to access these trailers.</span></span>

<span data-ttu-id="7c4a5-107">Los finalizadores de HTTP/1.1 están disponibles una vez que se ha leído todo el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-107">HTTP/1.1 trailers are available once the entire request body has been read.</span></span>

<span data-ttu-id="7c4a5-108">Los finalizadores de HTTP/2 están disponibles una vez que se han recibido del cliente.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-108">HTTP/2 trailers are available once they're received from the client.</span></span> <span data-ttu-id="7c4a5-109">El cliente no enviará los finalizadores hasta que el servidor haya almacenado en búfer como mínimo el cuerpo de la solicitud completo.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-109">The client won't send the trailers until the entire request body has been at least buffered by the server.</span></span> <span data-ttu-id="7c4a5-110">Es posible que deba leer el cuerpo de la solicitud para liberar espacio en búfer.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-110">You may need to read the request body to free up buffer space.</span></span> <span data-ttu-id="7c4a5-111">Los finalizadores siempre están disponibles si lee el cuerpo de la solicitud hasta el final.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-111">Trailers are always available if you read the request body to the end.</span></span> <span data-ttu-id="7c4a5-112">Los finalizadores marcan el final del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-112">The trailers mark the end of the body.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7c4a5-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7c4a5-113">Version introduced</span></span>

<span data-ttu-id="7c4a5-114">3.0</span><span class="sxs-lookup"><span data-stu-id="7c4a5-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7c4a5-115">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="7c4a5-115">Old behavior</span></span>

<span data-ttu-id="7c4a5-116">Los encabezados de finalizador de solicitud se agregarán a la recopilación `HttpRequest.Headers`.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-116">Request trailer headers would be added to the `HttpRequest.Headers` collection.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7c4a5-117">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="7c4a5-117">New behavior</span></span>

<span data-ttu-id="7c4a5-118">Los encabezados de finalizador de solicitud **no están presentes** en la recopilación `HttpRequest.Headers`.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-118">Request trailer headers **aren't present** in the `HttpRequest.Headers` collection.</span></span> <span data-ttu-id="7c4a5-119">Use los métodos de extensión siguientes en `HttpRequest` para tener acceso a ellos:</span><span class="sxs-lookup"><span data-stu-id="7c4a5-119">Use the following extension methods on `HttpRequest` to access them:</span></span>

- <span data-ttu-id="7c4a5-120">`GetDeclaredTrailers()`: obtiene el encabezado de "finalizador" de la solicitud que muestra los finalizadores que se esperan después del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-120">`GetDeclaredTrailers()` - Gets the request "Trailer" header that lists which trailers to expect after the body.</span></span>
- <span data-ttu-id="7c4a5-121">`SupportsTrailers()`: indica si la solicitud admite la recepción de encabezados de finalizador.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-121">`SupportsTrailers()` - Indicates if the request supports receiving trailer headers.</span></span>
- <span data-ttu-id="7c4a5-122">`CheckTrailersAvailable()`: determina si la solicitud admite finalizadores y si están disponible para lectura.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-122">`CheckTrailersAvailable()` - Determines if the request supports trailers and if they're available for reading.</span></span>
- <span data-ttu-id="7c4a5-123">`GetTrailer(string trailerName)`: obtiene el encabezado de finalización solicitado de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-123">`GetTrailer(string trailerName)` - Gets the requested trailing header from the response.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7c4a5-124">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="7c4a5-124">Reason for change</span></span>

<span data-ttu-id="7c4a5-125">Los finalizadores son una característica clave en escenarios como gRPC.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-125">Trailers are a key feature in scenarios like gRPC.</span></span> <span data-ttu-id="7c4a5-126">Combinar los finalizadores en los encabezados de solicitud ha sido confuso para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-126">Merging the trailers in to request headers was confusing to users.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7c4a5-127">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7c4a5-127">Recommended action</span></span>

<span data-ttu-id="7c4a5-128">Use los métodos de extensión relacionados con el finalizador en `HttpRequest` para tener acceso a los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="7c4a5-128">Use the trailer-related extension methods on `HttpRequest` to access trailers.</span></span>

#### <a name="category"></a><span data-ttu-id="7c4a5-129">Categoría</span><span class="sxs-lookup"><span data-stu-id="7c4a5-129">Category</span></span>

<span data-ttu-id="7c4a5-130">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7c4a5-130">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7c4a5-131">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7c4a5-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
