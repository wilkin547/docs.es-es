---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 193b783e44fe4386d3575e180dc5baa6a7f9a8be
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758378"
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="b6236-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="b6236-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="b6236-103">Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="b6236-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="b6236-104">Este elemento sólo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Default" o "Fragmentada".</span><span class="sxs-lookup"><span data-stu-id="b6236-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="b6236-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="b6236-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="b6236-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b6236-106">\<federationConfiguration></span></span>  
<span data-ttu-id="b6236-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="b6236-107">\<cookieHandler></span></span>  
<span data-ttu-id="b6236-108">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="b6236-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6236-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6236-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6236-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b6236-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b6236-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b6236-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6236-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b6236-112">Attributes</span></span>  
  
|<span data-ttu-id="b6236-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b6236-113">Attribute</span></span>|<span data-ttu-id="b6236-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6236-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6236-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="b6236-115">chunkSize</span></span>|<span data-ttu-id="b6236-116">El tamaño máximo, en caracteres, de los datos de cookies HTTP para una cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="b6236-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="b6236-117">Debe tener cuidado al ajustar el tamaño del fragmento.</span><span class="sxs-lookup"><span data-stu-id="b6236-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="b6236-118">Los exploradores Web tienen distintos límites en el tamaño de las cookies y el número permitido para cada dominio.</span><span class="sxs-lookup"><span data-stu-id="b6236-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="b6236-119">Por ejemplo, la especificación Netscape original estipulada estos límites: total de 300 cookies, 4096 bytes por encabezado cookie HTTP (incluidos los metadatos, no solo el valor de la cookie) y 20 cookies por dominio.</span><span class="sxs-lookup"><span data-stu-id="b6236-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="b6236-120">El valor predeterminado es 2000.</span><span class="sxs-lookup"><span data-stu-id="b6236-120">The default is 2000.</span></span> <span data-ttu-id="b6236-121">Requerido.</span><span class="sxs-lookup"><span data-stu-id="b6236-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6236-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b6236-122">Child Elements</span></span>  
 <span data-ttu-id="b6236-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b6236-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6236-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b6236-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b6236-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6236-125">Element</span></span>|<span data-ttu-id="b6236-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6236-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6236-127">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="b6236-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="b6236-128">Configura el <xref:System.IdentityModel.Services.CookieHandler> que la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) se utiliza para leer y escribir las cookies.</span><span class="sxs-lookup"><span data-stu-id="b6236-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6236-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6236-129">Remarks</span></span>  
 <span data-ttu-id="b6236-130">Cuando se especifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> estableciendo la `mode` atributo de la `<cookieHandler>` elemento a "Default" o "Chunked", puede especificar el tamaño del fragmento que usa el controlador de cookie para leer y escribir las cookies mediante la inclusión de un `<chunkedCookieHandler>` elemento secundario y establecer su `chunkSize` atributo.</span><span class="sxs-lookup"><span data-stu-id="b6236-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="b6236-131">Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño del fragmento predeterminado de 2000 bytes.</span><span class="sxs-lookup"><span data-stu-id="b6236-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="b6236-132">Este elemento no puede ser especificado cuando el `mode` atributo se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="b6236-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="b6236-133">El `<chunkedCookieHandler>` elemento representado por la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase.</span><span class="sxs-lookup"><span data-stu-id="b6236-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6236-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6236-134">Example</span></span>  
 <span data-ttu-id="b6236-135">En el ejemplo siguiente se configura un controlador de cookie fragmentada que escribe las cookies en fragmentos de 3000 bytes.</span><span class="sxs-lookup"><span data-stu-id="b6236-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6236-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6236-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
