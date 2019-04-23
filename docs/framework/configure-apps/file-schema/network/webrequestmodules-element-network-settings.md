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
ms.openlocfilehash: e5d1780a204b2e99593d51179a479845fd49e608
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187010"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="a861d-102">\<webRequestModules > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="a861d-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="a861d-103">Especifica los módulos que se utilizan para solicitar información de hosts de la red.</span><span class="sxs-lookup"><span data-stu-id="a861d-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="a861d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a861d-104">\<configuration></span></span>  
<span data-ttu-id="a861d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a861d-105">\<system.net></span></span>  
<span data-ttu-id="a861d-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="a861d-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a861d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a861d-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a861d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a861d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a861d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a861d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a861d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a861d-110">Attributes</span></span>  
 <span data-ttu-id="a861d-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a861d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a861d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a861d-112">Child Elements</span></span>  
  
|<span data-ttu-id="a861d-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="a861d-113">**Element**</span></span>|<span data-ttu-id="a861d-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a861d-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a861d-115">add</span><span class="sxs-lookup"><span data-stu-id="a861d-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="a861d-116">Agrega un módulo de solicitud Web personalizado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a861d-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="a861d-117">clear</span><span class="sxs-lookup"><span data-stu-id="a861d-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="a861d-118">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a861d-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="a861d-119">remove</span><span class="sxs-lookup"><span data-stu-id="a861d-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="a861d-120">Quita un módulo de solicitud Web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a861d-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a861d-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a861d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a861d-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="a861d-122">**Element**</span></span>|<span data-ttu-id="a861d-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a861d-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a861d-124">system.net</span><span class="sxs-lookup"><span data-stu-id="a861d-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="a861d-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="a861d-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a861d-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a861d-126">Remarks</span></span>  
 <span data-ttu-id="a861d-127">El `webRequestModules` elemento registra descendientes de la <xref:System.Net.WebRequest> clase para controlar las solicitudes de información a los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="a861d-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="a861d-128">Módulos de solicitud Web deben implementar la <xref:System.Net.IWebRequestCreate> interfaz.</span><span class="sxs-lookup"><span data-stu-id="a861d-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="a861d-129">.NET Framework incluye módulos de solicitud Web para los identificadores URI que comienzan por `http://`, `https://`, y `file://`.</span><span class="sxs-lookup"><span data-stu-id="a861d-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="a861d-130">Puede invalidar los módulos predeterminados sólo mediante el registro de un módulo personalizado en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a861d-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a861d-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a861d-131">Configuration Files</span></span>  
 <span data-ttu-id="a861d-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a861d-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a861d-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a861d-133">Example</span></span>  
 <span data-ttu-id="a861d-134">El ejemplo siguiente registra el módulo HTTP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a861d-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="a861d-135">Debe reemplazar los valores de versión y PublicKeyToken con los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="a861d-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a861d-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a861d-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="a861d-137">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a861d-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
