---
description: 'Más información acerca de: <chunkedCookieHandler>'
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b0090706d3d7a9f62e17ae63ec16e4b3a869a812
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664293"
---
# \<chunkedCookieHandler>

<span data-ttu-id="d7d6b-102">Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="d7d6b-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="d7d6b-103">Este elemento solo puede estar presente si el `mode` atributo del `<cookieHandler>` elemento es "default" o "fragmentado".</span><span class="sxs-lookup"><span data-stu-id="d7d6b-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="d7d6b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7d6b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7d6b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d7d6b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d7d6b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7d6b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="d7d6b-107">Attributes</span></span>  
  
|<span data-ttu-id="d7d6b-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="d7d6b-108">Attribute</span></span>|<span data-ttu-id="d7d6b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7d6b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7d6b-110">chunkSize</span><span class="sxs-lookup"><span data-stu-id="d7d6b-110">chunkSize</span></span>|<span data-ttu-id="d7d6b-111">Tamaño máximo, en caracteres, de los datos de cookies HTTP para cualquier cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-111">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="d7d6b-112">Debe tener cuidado al ajustar el tamaño del fragmento.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-112">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="d7d6b-113">Los exploradores Web tienen límites diferentes en cuanto al tamaño de las cookies y el número permitido por dominio.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-113">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="d7d6b-114">Por ejemplo, la especificación de Netscape original estipulaba estos límites: 300 cookies total, 4096 bytes por encabezado de cookie (incluidos los metadatos, no solo el valor de cookie) y 20 cookies por dominio.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-114">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="d7d6b-115">El valor predeterminado es 2000.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-115">The default is 2000.</span></span> <span data-ttu-id="d7d6b-116">Necesario.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7d6b-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d7d6b-117">Child Elements</span></span>  

 <span data-ttu-id="d7d6b-118">None</span><span class="sxs-lookup"><span data-stu-id="d7d6b-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7d6b-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d7d6b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d7d6b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7d6b-120">Element</span></span>|<span data-ttu-id="d7d6b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7d6b-121">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="d7d6b-122">Configura el <xref:System.IdentityModel.Services.CookieHandler> que <xref:System.IdentityModel.Services.SessionAuthenticationModule> usa (SAM) para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-122">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7d6b-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d7d6b-123">Remarks</span></span>  

 <span data-ttu-id="d7d6b-124">Cuando se especifica un estableciendo <xref:System.IdentityModel.Services.ChunkedCookieHandler> el `mode` atributo del `<cookieHandler>` elemento en "default" o "fragmentado", se puede especificar el tamaño del fragmento que el controlador de cookies utiliza para leer y escribir cookies incluyendo un `<chunkedCookieHandler>` elemento secundario y estableciendo su `chunkSize` atributo.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-124">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="d7d6b-125">Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño de fragmento predeterminado de 2000 bytes.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-125">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="d7d6b-126">No se puede especificar este elemento cuando el `mode` atributo se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="d7d6b-126">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="d7d6b-127">El `<chunkedCookieHandler>` elemento se representa mediante la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-127">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d6b-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7d6b-128">Example</span></span>  

 <span data-ttu-id="d7d6b-129">En el ejemplo siguiente se configura un controlador de cookies fragmentado que escribe cookies en fragmentos de 3000 bytes.</span><span class="sxs-lookup"><span data-stu-id="d7d6b-129">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7d6b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7d6b-130">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
