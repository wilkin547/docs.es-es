---
description: 'Más información sobre: <clear> elemento para webRequestModules (configuración de red)'
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
ms.openlocfilehash: 0782bf9edeafed2d61a368c3f6a8b37ef226c990
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740423"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="17248-103">Elemento \<clear> para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="17248-103">\<clear> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="17248-104">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17248-104">Removes all registered Web request modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="17248-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17248-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17248-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="17248-106">Attributes and Elements</span></span>  

 <span data-ttu-id="17248-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="17248-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17248-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="17248-108">Attributes</span></span>  

 <span data-ttu-id="17248-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="17248-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="17248-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="17248-110">Child Elements</span></span>  

 <span data-ttu-id="17248-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="17248-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17248-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="17248-112">Parent Elements</span></span>  
  
|<span data-ttu-id="17248-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="17248-113">**Element**</span></span>|<span data-ttu-id="17248-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="17248-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="17248-115">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="17248-115">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="17248-116">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="17248-116">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17248-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="17248-117">Remarks</span></span>  

 <span data-ttu-id="17248-118">El `clear` elemento quita todos los módulos de solicitud Web registrados que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="17248-118">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="17248-119">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="17248-119">Configuration Files</span></span>  

 <span data-ttu-id="17248-120">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="17248-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="17248-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17248-121">Example</span></span>  

 <span data-ttu-id="17248-122">En el ejemplo siguiente se borran todos los módulos de solicitud Web y, a continuación, se registra un módulo de solicitud Web para HTTP.</span><span class="sxs-lookup"><span data-stu-id="17248-122">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17248-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="17248-123">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="17248-124">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="17248-124">Network Settings Schema</span></span>](index.md)
