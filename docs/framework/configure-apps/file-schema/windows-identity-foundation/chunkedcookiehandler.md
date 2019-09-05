---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252109"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="8d008-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="8d008-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="8d008-102">Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="8d008-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="8d008-103">Este elemento solo puede estar presente si el `mode` atributo `<cookieHandler>` del elemento es "default" o "fragmentado".</span><span class="sxs-lookup"><span data-stu-id="8d008-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
<span data-ttu-id="8d008-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8d008-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8d008-105">&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="8d008-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="8d008-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="8d008-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="8d008-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> cookieHandler**](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="8d008-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="8d008-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> chunkedCookieHandler**</span><span class="sxs-lookup"><span data-stu-id="8d008-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d008-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d008-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d008-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8d008-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8d008-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8d008-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d008-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8d008-112">Attributes</span></span>  
  
|<span data-ttu-id="8d008-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8d008-113">Attribute</span></span>|<span data-ttu-id="8d008-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8d008-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d008-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="8d008-115">chunkSize</span></span>|<span data-ttu-id="8d008-116">Tamaño máximo, en caracteres, de los datos de cookies HTTP para cualquier cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d008-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="8d008-117">Debe tener cuidado al ajustar el tamaño del fragmento.</span><span class="sxs-lookup"><span data-stu-id="8d008-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="8d008-118">Los exploradores Web tienen límites diferentes en cuanto al tamaño de las cookies y el número permitido por dominio.</span><span class="sxs-lookup"><span data-stu-id="8d008-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="8d008-119">Por ejemplo, la especificación de Netscape original estipulaba estos límites: 300 cookies en total, 4096 bytes por encabezado de cookie (incluidos los metadatos, no solo el valor de cookie) y 20 cookies por dominio.</span><span class="sxs-lookup"><span data-stu-id="8d008-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="8d008-120">El valor predeterminado es 2000.</span><span class="sxs-lookup"><span data-stu-id="8d008-120">The default is 2000.</span></span> <span data-ttu-id="8d008-121">Necesario.</span><span class="sxs-lookup"><span data-stu-id="8d008-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d008-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8d008-122">Child Elements</span></span>  
 <span data-ttu-id="8d008-123">None</span><span class="sxs-lookup"><span data-stu-id="8d008-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d008-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8d008-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8d008-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="8d008-125">Element</span></span>|<span data-ttu-id="8d008-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8d008-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d008-127">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="8d008-127">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="8d008-128">Configura el <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> que usa (SAM) para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="8d008-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d008-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d008-129">Remarks</span></span>  
 <span data-ttu-id="8d008-130">Cuando se especifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> estableciendo el `mode` atributo del `<cookieHandler>` elemento en "default" o "fragmentado", se puede especificar el tamaño del fragmento que el controlador de cookies utiliza para leer y escribir cookies incluyendo `<chunkedCookieHandler>` un elemento secundario y establecer su `chunkSize` atributo.</span><span class="sxs-lookup"><span data-stu-id="8d008-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="8d008-131">Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño de fragmento predeterminado de 2000 bytes.</span><span class="sxs-lookup"><span data-stu-id="8d008-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="8d008-132">No se puede especificar este elemento cuando `mode` el atributo se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="8d008-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="8d008-133">El elemento se representa mediante la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase. `<chunkedCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="8d008-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d008-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d008-134">Example</span></span>  
 <span data-ttu-id="8d008-135">En el ejemplo siguiente se configura un controlador de cookies fragmentado que escribe cookies en fragmentos de 3000 bytes.</span><span class="sxs-lookup"><span data-stu-id="8d008-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d008-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d008-136">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
