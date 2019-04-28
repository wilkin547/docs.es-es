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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674602"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="2ab90-102">\<Borrar > elemento para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="2ab90-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="2ab90-103">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2ab90-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="2ab90-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2ab90-104">\<configuration></span></span>  
<span data-ttu-id="2ab90-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="2ab90-105">\<system.net></span></span>  
<span data-ttu-id="2ab90-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="2ab90-106">\<webRequestModules></span></span>  
<span data-ttu-id="2ab90-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="2ab90-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab90-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ab90-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ab90-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2ab90-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ab90-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2ab90-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ab90-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="2ab90-111">Attributes</span></span>  
 <span data-ttu-id="2ab90-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2ab90-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2ab90-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2ab90-113">Child Elements</span></span>  
 <span data-ttu-id="2ab90-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2ab90-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ab90-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2ab90-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2ab90-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="2ab90-116">**Element**</span></span>|<span data-ttu-id="2ab90-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2ab90-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2ab90-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="2ab90-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="2ab90-119">Especifica los módulos que se utilizan para solicitar información de hosts de la red.</span><span class="sxs-lookup"><span data-stu-id="2ab90-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ab90-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ab90-120">Remarks</span></span>  
 <span data-ttu-id="2ab90-121">El `clear` elemento quita todos los módulos de solicitud Web que se han definido anteriormente en el archivo de configuración o en un nivel superior de la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="2ab90-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2ab90-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2ab90-122">Configuration Files</span></span>  
 <span data-ttu-id="2ab90-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2ab90-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ab90-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ab90-124">Example</span></span>  
 <span data-ttu-id="2ab90-125">El ejemplo siguiente borra todos los módulos de solicitud Web y, a continuación, registra un módulo de solicitud Web para HTTP.</span><span class="sxs-lookup"><span data-stu-id="2ab90-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ab90-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ab90-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="2ab90-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="2ab90-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
