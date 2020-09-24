---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: a321c10e04eca2c1a5204929966a1725e918cbdf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158531"
---
# \<chunkedCookieHandler>

<span data-ttu-id="9b39d-101">Configura el <xref:System.IdentityModel.Services.ChunkedCookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="9b39d-101">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="9b39d-102">Este elemento solo puede estar presente si el `mode` atributo del `<cookieHandler>` elemento es "default" o "fragmentado".</span><span class="sxs-lookup"><span data-stu-id="9b39d-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="9b39d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b39d-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b39d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9b39d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="9b39d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9b39d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b39d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b39d-106">Attributes</span></span>  
  
|<span data-ttu-id="9b39d-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="9b39d-107">Attribute</span></span>|<span data-ttu-id="9b39d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b39d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b39d-109">chunkSize</span><span class="sxs-lookup"><span data-stu-id="9b39d-109">chunkSize</span></span>|<span data-ttu-id="9b39d-110">Tamaño máximo, en caracteres, de los datos de cookies HTTP para cualquier cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="9b39d-110">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="9b39d-111">Debe tener cuidado al ajustar el tamaño del fragmento.</span><span class="sxs-lookup"><span data-stu-id="9b39d-111">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="9b39d-112">Los exploradores Web tienen límites diferentes en cuanto al tamaño de las cookies y el número permitido por dominio.</span><span class="sxs-lookup"><span data-stu-id="9b39d-112">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="9b39d-113">Por ejemplo, la especificación de Netscape original estipulaba estos límites: 300 cookies total, 4096 bytes por encabezado de cookie (incluidos los metadatos, no solo el valor de cookie) y 20 cookies por dominio.</span><span class="sxs-lookup"><span data-stu-id="9b39d-113">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="9b39d-114">El valor predeterminado es 2000.</span><span class="sxs-lookup"><span data-stu-id="9b39d-114">The default is 2000.</span></span> <span data-ttu-id="9b39d-115">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9b39d-115">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b39d-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9b39d-116">Child Elements</span></span>  

 <span data-ttu-id="9b39d-117">None</span><span class="sxs-lookup"><span data-stu-id="9b39d-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b39d-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9b39d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9b39d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b39d-119">Element</span></span>|<span data-ttu-id="9b39d-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b39d-120">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="9b39d-121">Configura el <xref:System.IdentityModel.Services.CookieHandler> que <xref:System.IdentityModel.Services.SessionAuthenticationModule> usa (SAM) para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="9b39d-121">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b39d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9b39d-122">Remarks</span></span>  

 <span data-ttu-id="9b39d-123">Cuando se especifica un estableciendo <xref:System.IdentityModel.Services.ChunkedCookieHandler> el `mode` atributo del `<cookieHandler>` elemento en "default" o "fragmentado", se puede especificar el tamaño del fragmento que el controlador de cookies utiliza para leer y escribir cookies incluyendo un `<chunkedCookieHandler>` elemento secundario y estableciendo su `chunkSize` atributo.</span><span class="sxs-lookup"><span data-stu-id="9b39d-123">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="9b39d-124">Si el `<chunkedCookieHandler>` elemento no está presente, se utiliza el tamaño de fragmento predeterminado de 2000 bytes.</span><span class="sxs-lookup"><span data-stu-id="9b39d-124">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="9b39d-125">No se puede especificar este elemento cuando el `mode` atributo se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="9b39d-125">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="9b39d-126">El `<chunkedCookieHandler>` elemento se representa mediante la <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> clase.</span><span class="sxs-lookup"><span data-stu-id="9b39d-126">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b39d-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b39d-127">Example</span></span>  

 <span data-ttu-id="9b39d-128">En el ejemplo siguiente se configura un controlador de cookies fragmentado que escribe cookies en fragmentos de 3000 bytes.</span><span class="sxs-lookup"><span data-stu-id="9b39d-128">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b39d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b39d-129">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
