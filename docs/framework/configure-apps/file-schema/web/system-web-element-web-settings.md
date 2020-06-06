---
title: Elemento <system.web> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152846"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="c3613-102">Elemento \<system.web> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="c3613-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="c3613-103">Contiene información sobre cómo el nivel de hospedaje de ASP.NET administra el comportamiento de todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="c3613-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a><span data-ttu-id="c3613-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3613-104">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3613-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c3613-105">Attributes and Elements</span></span>  

<span data-ttu-id="c3613-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c3613-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3613-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c3613-107">Attributes</span></span>  

<span data-ttu-id="c3613-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c3613-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c3613-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c3613-109">Child Elements</span></span>  
  
|<span data-ttu-id="c3613-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3613-110">Element</span></span>|<span data-ttu-id="c3613-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3613-111">Description</span></span>|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="c3613-112">Especifica los valores de configuración para los grupos de aplicaciones de IIS en un archivo Aspnet. config.</span><span class="sxs-lookup"><span data-stu-id="c3613-112">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3613-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c3613-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c3613-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3613-114">Element</span></span>|<span data-ttu-id="c3613-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3613-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="c3613-116">Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3613-116">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3613-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3613-117">Remarks</span></span>  

<span data-ttu-id="c3613-118">El `system.web` elemento y su `applicationPool` elemento secundario se agregaron a la .NET Framework a partir de .NET Framework 3,5 SP1.</span><span class="sxs-lookup"><span data-stu-id="c3613-118">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="c3613-119">Al ejecutar IIS 7,0 o versiones posteriores en el modo integrado, esta combinación de elementos le permite configurar el modo en que ASP.NET administra los subprocesos y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="c3613-119">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="c3613-120">Si ejecuta IIS 7,0 o versiones posteriores en el modo clásico o ISAPI, se omiten estos valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="c3613-120">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3613-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3613-121">Example</span></span>  

<span data-ttu-id="c3613-122">En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo Aspnet. config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="c3613-122">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="c3613-123">En el ejemplo se da por supuesto que IIS se ejecuta en modo integrado y que la aplicación está usando .NET Framework 3,5 SP1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="c3613-123">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="c3613-124">Este comportamiento no se produce en las versiones de .NET Framework anteriores al .NET Framework 3,5 SP1.</span><span class="sxs-lookup"><span data-stu-id="c3613-124">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="c3613-125">Los valores del ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c3613-125">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="c3613-126">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="c3613-126">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3613-127">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c3613-127">Namespace</span></span>||  
|<span data-ttu-id="c3613-128">Nombre del esquema</span><span class="sxs-lookup"><span data-stu-id="c3613-128">Schema Name</span></span>||  
|<span data-ttu-id="c3613-129">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="c3613-129">Validation File</span></span>||  
|<span data-ttu-id="c3613-130">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="c3613-130">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="c3613-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3613-131">See also</span></span>

- [<span data-ttu-id="c3613-132">\<applicationPool>(Elemento, configuración Web)</span><span class="sxs-lookup"><span data-stu-id="c3613-132">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
