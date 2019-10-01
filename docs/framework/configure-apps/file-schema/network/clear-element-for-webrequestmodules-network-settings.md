---
title: Elemento <clear> para webRequestModules (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 95a190dac3a9512b404a054c60c48de9c4574790
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698338"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="e2028-102">\<clear elemento > para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e2028-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="e2028-103">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2028-103">Removes all registered Web request modules from the application.</span></span>  
  
[<span data-ttu-id="e2028-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e2028-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e2028-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e2028-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="e2028-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e2028-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="e2028-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="e2028-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2028-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2028-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2028-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e2028-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e2028-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e2028-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2028-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e2028-111">Attributes</span></span>  
 <span data-ttu-id="e2028-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e2028-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2028-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e2028-113">Child Elements</span></span>  
 <span data-ttu-id="e2028-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e2028-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2028-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e2028-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e2028-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="e2028-116">**Element**</span></span>|<span data-ttu-id="e2028-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e2028-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e2028-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="e2028-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="e2028-119">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="e2028-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2028-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2028-120">Remarks</span></span>  
 <span data-ttu-id="e2028-121">El elemento `clear` quita todos los módulos de solicitud Web registrados que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="e2028-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e2028-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e2028-122">Configuration Files</span></span>  
 <span data-ttu-id="e2028-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e2028-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2028-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2028-124">Example</span></span>  
 <span data-ttu-id="e2028-125">En el ejemplo siguiente se borran todos los módulos de solicitud Web y, a continuación, se registra un módulo de solicitud Web para HTTP.</span><span class="sxs-lookup"><span data-stu-id="e2028-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2028-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2028-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="e2028-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e2028-127">Network Settings Schema</span></span>](index.md)
