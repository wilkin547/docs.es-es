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
ms.openlocfilehash: b9a43c5f5141e364ab9aac1cfdff577a8fb8a161
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486679"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="e08ab-102">\<System.Web > elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="e08ab-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="e08ab-103">Contiene información sobre cómo administra el comportamiento de todo el proceso de la capa de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e08ab-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="e08ab-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e08ab-104">\<configuration></span></span>  
<span data-ttu-id="e08ab-105">\<System.Web > elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="e08ab-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e08ab-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e08ab-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e08ab-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e08ab-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e08ab-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e08ab-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e08ab-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e08ab-109">Attributes</span></span>  
 <span data-ttu-id="e08ab-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e08ab-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e08ab-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e08ab-111">Child Elements</span></span>  
  
|<span data-ttu-id="e08ab-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e08ab-112">Element</span></span>|<span data-ttu-id="e08ab-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e08ab-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e08ab-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="e08ab-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="e08ab-115">Especifica la configuración para grupos de aplicaciones de IIS en un archivo aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="e08ab-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e08ab-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e08ab-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e08ab-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e08ab-117">Element</span></span>|<span data-ttu-id="e08ab-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="e08ab-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e08ab-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e08ab-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="e08ab-120">Especifica el elemento raíz de cada archivo de configuración que usa el common language runtime y aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e08ab-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e08ab-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e08ab-121">Remarks</span></span>  
 <span data-ttu-id="e08ab-122">El `system.web` elemento y su elemento secundario `applicationPool` elemento se han agregado a .NET Framework a partir de .NET Framework 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="e08ab-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="e08ab-123">Cuando se ejecuta en modo integrado de IIS 7.0 o versiones posteriores, esta combinación de elementos permite configurar cómo administra los subprocesos de ASP.NET y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="e08ab-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="e08ab-124">Si se ejecutan IIS 7.0 o versiones posteriores en modo ISAPI o clásico, se omiten estos valores.</span><span class="sxs-lookup"><span data-stu-id="e08ab-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e08ab-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e08ab-125">Example</span></span>  
 <span data-ttu-id="e08ab-126">El ejemplo siguiente muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="e08ab-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="e08ab-127">El ejemplo se supone que se está ejecutando IIS en integrado modo y que la aplicación está utilizando .NET Framework 3.5 SP1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="e08ab-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="e08ab-128">Este comportamiento no se produce en las versiones de .NET Framework anteriores a .NET Framework 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="e08ab-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="e08ab-129">Los valores en el ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e08ab-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="e08ab-130">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="e08ab-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e08ab-131">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e08ab-131">Namespace</span></span>||  
|<span data-ttu-id="e08ab-132">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="e08ab-132">Schema Name</span></span>||  
|<span data-ttu-id="e08ab-133">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="e08ab-133">Validation File</span></span>||  
|<span data-ttu-id="e08ab-134">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="e08ab-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="e08ab-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e08ab-135">See also</span></span>

- [<span data-ttu-id="e08ab-136">Elemento \<applicationPool> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="e08ab-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
