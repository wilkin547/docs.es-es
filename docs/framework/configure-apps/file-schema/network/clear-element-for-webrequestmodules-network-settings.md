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
ms.openlocfilehash: 5832d120824df75d374fc94cb0aa4e08189cb965
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088500"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="4f90b-102">Elemento \<clear> para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4f90b-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="4f90b-103">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f90b-103">Removes all registered Web request modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="4f90b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f90b-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f90b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f90b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4f90b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f90b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f90b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f90b-107">Attributes</span></span>  
 <span data-ttu-id="4f90b-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f90b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4f90b-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f90b-109">Child Elements</span></span>  
 <span data-ttu-id="4f90b-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f90b-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f90b-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f90b-111">Parent Elements</span></span>  
  
|<span data-ttu-id="4f90b-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="4f90b-112">**Element**</span></span>|<span data-ttu-id="4f90b-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4f90b-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4f90b-114">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="4f90b-114">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="4f90b-115">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="4f90b-115">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f90b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f90b-116">Remarks</span></span>  
 <span data-ttu-id="4f90b-117">El `clear` elemento quita todos los módulos de solicitud Web registrados que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="4f90b-117">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4f90b-118">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4f90b-118">Configuration Files</span></span>  
 <span data-ttu-id="4f90b-119">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4f90b-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f90b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f90b-120">Example</span></span>  
 <span data-ttu-id="4f90b-121">En el ejemplo siguiente se borran todos los módulos de solicitud Web y, a continuación, se registra un módulo de solicitud Web para HTTP.</span><span class="sxs-lookup"><span data-stu-id="4f90b-121">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4f90b-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f90b-122">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="4f90b-123">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="4f90b-123">Network Settings Schema</span></span>](index.md)
