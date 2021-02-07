---
description: 'Más información acerca de: <elemento> System. Web (configuración Web)'
title: Elemento <system.web> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 2adcd3eba1eb6d67bcb4dc82243cd70d31d64fe9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681908"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="a9321-103">Elemento \<system.web> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="a9321-103">\<system.web> Element (Web Settings)</span></span>

<span data-ttu-id="a9321-104">Contiene información sobre cómo el nivel de hospedaje de ASP.NET administra el comportamiento de todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="a9321-104">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a><span data-ttu-id="a9321-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9321-105">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9321-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a9321-106">Attributes and Elements</span></span>  

<span data-ttu-id="a9321-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a9321-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9321-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a9321-108">Attributes</span></span>  

<span data-ttu-id="a9321-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9321-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a9321-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a9321-110">Child Elements</span></span>  
  
|<span data-ttu-id="a9321-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9321-111">Element</span></span>|<span data-ttu-id="a9321-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9321-112">Description</span></span>|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="a9321-113">Especifica los valores de configuración para los grupos de aplicaciones de IIS en un archivo aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="a9321-113">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9321-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a9321-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a9321-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9321-115">Element</span></span>|<span data-ttu-id="a9321-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9321-116">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="a9321-117">Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9321-117">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9321-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a9321-118">Remarks</span></span>  

<span data-ttu-id="a9321-119">El `system.web` elemento y su `applicationPool` elemento secundario se agregaron a la .NET Framework a partir de .NET Framework 3,5 SP1.</span><span class="sxs-lookup"><span data-stu-id="a9321-119">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="a9321-120">Al ejecutar IIS 7,0 o versiones posteriores en el modo integrado, esta combinación de elementos le permite configurar el modo en que ASP.NET administra los subprocesos y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="a9321-120">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="a9321-121">Si ejecuta IIS 7,0 o versiones posteriores en el modo clásico o ISAPI, se omiten estos valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="a9321-121">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9321-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9321-122">Example</span></span>  

<span data-ttu-id="a9321-123">En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo de aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="a9321-123">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="a9321-124">En el ejemplo se da por supuesto que IIS se ejecuta en modo integrado y que la aplicación está usando .NET Framework 3,5 SP1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="a9321-124">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="a9321-125">Este comportamiento no se produce en las versiones de .NET Framework anteriores al .NET Framework 3,5 SP1.</span><span class="sxs-lookup"><span data-stu-id="a9321-125">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="a9321-126">Los valores del ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a9321-126">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="a9321-127">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="a9321-127">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9321-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a9321-128">Namespace</span></span>||  
|<span data-ttu-id="a9321-129">Nombre del esquema</span><span class="sxs-lookup"><span data-stu-id="a9321-129">Schema Name</span></span>||  
|<span data-ttu-id="a9321-130">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="a9321-130">Validation File</span></span>||  
|<span data-ttu-id="a9321-131">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="a9321-131">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a9321-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9321-132">See also</span></span>

- [<span data-ttu-id="a9321-133">\<applicationPool> (Elemento, configuración Web)</span><span class="sxs-lookup"><span data-stu-id="a9321-133">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
