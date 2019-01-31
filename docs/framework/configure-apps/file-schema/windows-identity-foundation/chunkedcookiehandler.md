---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 383ce39816ec7d3f2567765549b537073ee7e081
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277035"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="ba032-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="ba032-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="ba032-102">Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="ba032-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="ba032-103">Este elemento solo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Default" o "Fragmentada".</span><span class="sxs-lookup"><span data-stu-id="ba032-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="ba032-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="ba032-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="ba032-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="ba032-105">\<federationConfiguration></span></span>  
<span data-ttu-id="ba032-106">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="ba032-106">\<cookieHandler></span></span>  
<span data-ttu-id="ba032-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="ba032-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba032-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba032-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba032-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ba032-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba032-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ba032-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba032-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba032-111">Attributes</span></span>  
  
|<span data-ttu-id="ba032-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="ba032-112">Attribute</span></span>|<span data-ttu-id="ba032-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba032-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba032-114">chunkSize</span><span class="sxs-lookup"><span data-stu-id="ba032-114">chunkSize</span></span>|<span data-ttu-id="ba032-115">El tamaño máximo, en caracteres, de los datos de cookies HTTP para una cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="ba032-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="ba032-116">Debe tener cuidado cuando ajuste el tamaño del fragmento.</span><span class="sxs-lookup"><span data-stu-id="ba032-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="ba032-117">Los exploradores Web tienen distintos límites en el tamaño de las cookies y el número permitido por dominio.</span><span class="sxs-lookup"><span data-stu-id="ba032-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="ba032-118">Por ejemplo, la especificación de Netscape original había estipulada estos límites: total de 300 cookies 4096 bytes por encabezado de cookie (incluidos los metadatos, no solo el valor de cookie) y 20 cookies por dominio.</span><span class="sxs-lookup"><span data-stu-id="ba032-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="ba032-119">El valor predeterminado es 2000.</span><span class="sxs-lookup"><span data-stu-id="ba032-119">The default is 2000.</span></span> <span data-ttu-id="ba032-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ba032-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba032-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ba032-121">Child Elements</span></span>  
 <span data-ttu-id="ba032-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ba032-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba032-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba032-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ba032-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba032-124">Element</span></span>|<span data-ttu-id="ba032-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba032-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba032-126">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="ba032-126">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="ba032-127">Configura el <xref:System.IdentityModel.Services.CookieHandler> que el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) se usa para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="ba032-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba032-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba032-128">Remarks</span></span>  
 <span data-ttu-id="ba032-129">Cuando se especifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> estableciendo el `mode` atributo de la `<cookieHandler>` elemento va a "Default" o "Chunked", puede especificar el tamaño del fragmento que usa el controlador de cookies para leer y escribir las cookies mediante la inclusión de un `<chunkedCookieHandler>` elemento secundario y establecer su `chunkSize` atributo.</span><span class="sxs-lookup"><span data-stu-id="ba032-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="ba032-130">Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño del fragmento predeterminado de 2000 bytes.</span><span class="sxs-lookup"><span data-stu-id="ba032-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="ba032-131">Este elemento no puede ser que se especificó cuando la `mode` atributo está establecido en "Custom".</span><span class="sxs-lookup"><span data-stu-id="ba032-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="ba032-132">El `<chunkedCookieHandler>` elemento representado por la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase.</span><span class="sxs-lookup"><span data-stu-id="ba032-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba032-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba032-133">Example</span></span>  
 <span data-ttu-id="ba032-134">El ejemplo siguiente configura un controlador de cookies fragmentado que escribe las cookies en fragmentos de 3000 bytes.</span><span class="sxs-lookup"><span data-stu-id="ba032-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba032-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba032-135">See also</span></span>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
