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
ms.openlocfilehash: 5c5c857d4494b6d78b819e56bae4213abc5e2035
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699093"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="542f8-102">@no__t elemento > -0SYSTEM. Web (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="542f8-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="542f8-103">Contiene información sobre cómo el nivel de hospedaje de ASP.NET administra el comportamiento de todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="542f8-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="542f8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="542f8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="542f8-105">&nbsp; @ no__t-1 **@no__t -3system. web >**</span><span class="sxs-lookup"><span data-stu-id="542f8-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="542f8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="542f8-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="542f8-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="542f8-107">Attributes and Elements</span></span>  

<span data-ttu-id="542f8-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="542f8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="542f8-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="542f8-109">Attributes</span></span>  

<span data-ttu-id="542f8-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="542f8-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="542f8-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="542f8-111">Child Elements</span></span>  
  
|<span data-ttu-id="542f8-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="542f8-112">Element</span></span>|<span data-ttu-id="542f8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="542f8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="542f8-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="542f8-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="542f8-115">Especifica los valores de configuración para los grupos de aplicaciones de IIS en un archivo Aspnet. config.</span><span class="sxs-lookup"><span data-stu-id="542f8-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="542f8-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="542f8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="542f8-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="542f8-117">Element</span></span>|<span data-ttu-id="542f8-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="542f8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="542f8-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="542f8-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="542f8-120">Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="542f8-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="542f8-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="542f8-121">Remarks</span></span>  

<span data-ttu-id="542f8-122">El elemento `system.web` y su elemento secundario `applicationPool` se agregaron a la .NET Framework a partir de .NET Framework 3,5 SP1.</span><span class="sxs-lookup"><span data-stu-id="542f8-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="542f8-123">Al ejecutar IIS 7,0 o versiones posteriores en el modo integrado, esta combinación de elementos le permite configurar el modo en que ASP.NET administra los subprocesos y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="542f8-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="542f8-124">Si ejecuta IIS 7,0 o versiones posteriores en el modo clásico o ISAPI, se omiten estos valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="542f8-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="542f8-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="542f8-125">Example</span></span>  

<span data-ttu-id="542f8-126">En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo Aspnet. config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="542f8-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="542f8-127">En el ejemplo se da por supuesto que IIS se ejecuta en modo integrado y que la aplicación está usando .NET Framework 3,5 SP1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="542f8-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="542f8-128">Este comportamiento no se produce en las versiones de .NET Framework anteriores al .NET Framework 3,5 SP1.</span><span class="sxs-lookup"><span data-stu-id="542f8-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="542f8-129">Los valores del ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="542f8-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="542f8-130">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="542f8-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="542f8-131">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="542f8-131">Namespace</span></span>||  
|<span data-ttu-id="542f8-132">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="542f8-132">Schema Name</span></span>||  
|<span data-ttu-id="542f8-133">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="542f8-133">Validation File</span></span>||  
|<span data-ttu-id="542f8-134">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="542f8-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="542f8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="542f8-135">See also</span></span>

- [<span data-ttu-id="542f8-136">Elemento \<applicationPool> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="542f8-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
