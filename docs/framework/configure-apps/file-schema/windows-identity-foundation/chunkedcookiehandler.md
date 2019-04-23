---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: d9c81d5de7bea343f0d67fa00037763fbae7b8c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120788"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="2a0fc-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="2a0fc-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="2a0fc-102">Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="2a0fc-103">Este elemento solo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Default" o "Fragmentada".</span><span class="sxs-lookup"><span data-stu-id="2a0fc-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="2a0fc-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="2a0fc-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="2a0fc-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="2a0fc-105">\<federationConfiguration></span></span>  
<span data-ttu-id="2a0fc-106">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="2a0fc-106">\<cookieHandler></span></span>  
<span data-ttu-id="2a0fc-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="2a0fc-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a0fc-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a0fc-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a0fc-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2a0fc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2a0fc-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a0fc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="2a0fc-111">Attributes</span></span>  
  
|<span data-ttu-id="2a0fc-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="2a0fc-112">Attribute</span></span>|<span data-ttu-id="2a0fc-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a0fc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a0fc-114">chunkSize</span><span class="sxs-lookup"><span data-stu-id="2a0fc-114">chunkSize</span></span>|<span data-ttu-id="2a0fc-115">El tamaño máximo, en caracteres, de los datos de cookies HTTP para una cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="2a0fc-116">Debe tener cuidado cuando ajuste el tamaño del fragmento.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="2a0fc-117">Los exploradores Web tienen distintos límites en el tamaño de las cookies y el número permitido por dominio.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="2a0fc-118">Por ejemplo, la especificación de Netscape original había estipulada estos límites: total de 300 cookies 4096 bytes por encabezado de cookie (incluidos los metadatos, no solo el valor de cookie) y 20 cookies por dominio.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="2a0fc-119">El valor predeterminado es 2000.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-119">The default is 2000.</span></span> <span data-ttu-id="2a0fc-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a0fc-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2a0fc-121">Child Elements</span></span>  
 <span data-ttu-id="2a0fc-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="2a0fc-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a0fc-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2a0fc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2a0fc-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a0fc-124">Element</span></span>|<span data-ttu-id="2a0fc-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a0fc-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a0fc-126">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="2a0fc-126">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="2a0fc-127">Configura el <xref:System.IdentityModel.Services.CookieHandler> que el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) se usa para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a0fc-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a0fc-128">Remarks</span></span>  
 <span data-ttu-id="2a0fc-129">Cuando se especifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> estableciendo el `mode` atributo de la `<cookieHandler>` elemento va a "Default" o "Chunked", puede especificar el tamaño del fragmento que usa el controlador de cookies para leer y escribir las cookies mediante la inclusión de un `<chunkedCookieHandler>` elemento secundario y establecer su `chunkSize` atributo.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="2a0fc-130">Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño del fragmento predeterminado de 2000 bytes.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="2a0fc-131">Este elemento no puede ser que se especificó cuando la `mode` atributo está establecido en "Custom".</span><span class="sxs-lookup"><span data-stu-id="2a0fc-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="2a0fc-132">El `<chunkedCookieHandler>` elemento representado por la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a0fc-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a0fc-133">Example</span></span>  
 <span data-ttu-id="2a0fc-134">El ejemplo siguiente configura un controlador de cookies fragmentado que escribe las cookies en fragmentos de 3000 bytes.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a0fc-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a0fc-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
