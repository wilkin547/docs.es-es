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
ms.openlocfilehash: 5dea238629b282776cb45f7b388e655fa557d084
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078985"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="6002d-102">\<Borrar > elemento para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="6002d-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="6002d-103">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6002d-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="6002d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6002d-104">\<configuration></span></span>  
<span data-ttu-id="6002d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6002d-105">\<system.net></span></span>  
<span data-ttu-id="6002d-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="6002d-106">\<webRequestModules></span></span>  
<span data-ttu-id="6002d-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="6002d-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6002d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6002d-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6002d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6002d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6002d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6002d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6002d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="6002d-111">Attributes</span></span>  
 <span data-ttu-id="6002d-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6002d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6002d-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6002d-113">Child Elements</span></span>  
 <span data-ttu-id="6002d-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6002d-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6002d-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6002d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6002d-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="6002d-116">**Element**</span></span>|<span data-ttu-id="6002d-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6002d-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6002d-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="6002d-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="6002d-119">Especifica los módulos que se utilizan para solicitar información de hosts de la red.</span><span class="sxs-lookup"><span data-stu-id="6002d-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6002d-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6002d-120">Remarks</span></span>  
 <span data-ttu-id="6002d-121">El `clear` elemento quita todos los módulos de solicitud Web que se han definido anteriormente en el archivo de configuración o en un nivel superior de la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="6002d-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6002d-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6002d-122">Configuration Files</span></span>  
 <span data-ttu-id="6002d-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6002d-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6002d-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6002d-124">Example</span></span>  
 <span data-ttu-id="6002d-125">El ejemplo siguiente borra todos los módulos de solicitud Web y, a continuación, registra un módulo de solicitud Web para HTTP.</span><span class="sxs-lookup"><span data-stu-id="6002d-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6002d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6002d-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="6002d-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="6002d-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
