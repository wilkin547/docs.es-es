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
ms.openlocfilehash: 7f2805283f89e6165d336b3e593d34054e02115d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154548"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="f7fcf-102">Elemento \<webRequestModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="f7fcf-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="f7fcf-103">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a><span data-ttu-id="f7fcf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7fcf-104">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7fcf-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f7fcf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f7fcf-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7fcf-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f7fcf-107">Attributes</span></span>  
 <span data-ttu-id="f7fcf-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7fcf-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f7fcf-109">Child Elements</span></span>  
  
|<span data-ttu-id="f7fcf-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="f7fcf-110">**Element**</span></span>|<span data-ttu-id="f7fcf-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f7fcf-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f7fcf-112">add</span><span class="sxs-lookup"><span data-stu-id="f7fcf-112">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="f7fcf-113">Agrega un módulo de solicitud web personalizado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-113">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="f7fcf-114">clear</span><span class="sxs-lookup"><span data-stu-id="f7fcf-114">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="f7fcf-115">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-115">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="f7fcf-116">remove</span><span class="sxs-lookup"><span data-stu-id="f7fcf-116">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="f7fcf-117">Quita un módulo de solicitud web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-117">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7fcf-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f7fcf-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f7fcf-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="f7fcf-119">**Element**</span></span>|<span data-ttu-id="f7fcf-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f7fcf-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f7fcf-121">system.net</span><span class="sxs-lookup"><span data-stu-id="f7fcf-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="f7fcf-122">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7fcf-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7fcf-123">Remarks</span></span>  
 <span data-ttu-id="f7fcf-124">El `webRequestModules` elemento registra descendientes de la <xref:System.Net.WebRequest> clase para controlar las solicitudes de información a los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-124">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="f7fcf-125">Los módulos de solicitud Web deben implementar la <xref:System.Net.IWebRequestCreate> interfaz.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-125">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="f7fcf-126">El .NET Framework incluye módulos de solicitud Web para los URI que comienzan por `http://` , `https://` y `file://` .</span><span class="sxs-lookup"><span data-stu-id="f7fcf-126">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="f7fcf-127">Solo puede invalidar los módulos predeterminados Si registra un módulo personalizado en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-127">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f7fcf-128">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f7fcf-128">Configuration Files</span></span>  
 <span data-ttu-id="f7fcf-129">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f7fcf-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7fcf-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7fcf-130">Example</span></span>  
 <span data-ttu-id="f7fcf-131">En el ejemplo siguiente se registra el módulo HTTP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-131">The following example registers the default HTTP module.</span></span> <span data-ttu-id="f7fcf-132">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="f7fcf-132">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f7fcf-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7fcf-133">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="f7fcf-134">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f7fcf-134">Network Settings Schema</span></span>](index.md)
