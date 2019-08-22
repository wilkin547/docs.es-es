---
title: Elemento <webRequestModules> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: c30a7a0bcce62c99d7c1ec0ff17389b8c2cd2f17
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663940"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="6e2f6-102">\<webRequestModules > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="6e2f6-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="6e2f6-103">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="6e2f6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6e2f6-104">\<configuration></span></span>  
<span data-ttu-id="6e2f6-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6e2f6-105">\<system.net></span></span>  
<span data-ttu-id="6e2f6-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="6e2f6-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e2f6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e2f6-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e2f6-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6e2f6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6e2f6-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e2f6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e2f6-110">Attributes</span></span>  
 <span data-ttu-id="6e2f6-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e2f6-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6e2f6-112">Child Elements</span></span>  
  
|<span data-ttu-id="6e2f6-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="6e2f6-113">**Element**</span></span>|<span data-ttu-id="6e2f6-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6e2f6-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6e2f6-115">add</span><span class="sxs-lookup"><span data-stu-id="6e2f6-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="6e2f6-116">Agrega un módulo de solicitud web personalizado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="6e2f6-117">clear</span><span class="sxs-lookup"><span data-stu-id="6e2f6-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="6e2f6-118">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="6e2f6-119">remove</span><span class="sxs-lookup"><span data-stu-id="6e2f6-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="6e2f6-120">Quita un módulo de solicitud web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e2f6-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6e2f6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6e2f6-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="6e2f6-122">**Element**</span></span>|<span data-ttu-id="6e2f6-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6e2f6-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6e2f6-124">system.net</span><span class="sxs-lookup"><span data-stu-id="6e2f6-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="6e2f6-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e2f6-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6e2f6-126">Remarks</span></span>  
 <span data-ttu-id="6e2f6-127">El `webRequestModules` elemento registra descendientes de la clase <xref:System.Net.WebRequest> para controlar las solicitudes de información a los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="6e2f6-128">Los módulos de solicitud Web deben <xref:System.Net.IWebRequestCreate> implementar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="6e2f6-129">El .NET Framework incluye módulos de solicitud Web para los URI que `http://`comienzan `https://`por, `file://`y.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="6e2f6-130">Solo puede invalidar los módulos predeterminados Si registra un módulo personalizado en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6e2f6-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6e2f6-131">Configuration Files</span></span>  
 <span data-ttu-id="6e2f6-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6e2f6-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e2f6-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e2f6-133">Example</span></span>  
 <span data-ttu-id="6e2f6-134">En el ejemplo siguiente se registra el módulo HTTP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="6e2f6-135">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="6e2f6-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e2f6-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e2f6-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="6e2f6-137">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="6e2f6-137">Network Settings Schema</span></span>](index.md)
