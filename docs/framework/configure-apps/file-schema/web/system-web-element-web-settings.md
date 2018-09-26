---
title: '&lt;System.Web&gt; elemento (configuración Web)'
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 39d305d429490380c76e15bdcdde434f0d75457b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47202694"
---
# <a name="ltsystemwebgt-element-web-settings"></a><span data-ttu-id="219ea-102">&lt;System.Web&gt; elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="219ea-102">&lt;system.web&gt; Element (Web Settings)</span></span>
<span data-ttu-id="219ea-103">Contiene información sobre cómo administra el comportamiento de todo el proceso de la capa de hospedaje de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="219ea-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="219ea-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="219ea-104">\<configuration></span></span>  
<span data-ttu-id="219ea-105">\<System.Web > elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="219ea-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="219ea-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="219ea-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="219ea-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="219ea-107">Attributes and Elements</span></span>  
 <span data-ttu-id="219ea-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="219ea-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="219ea-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="219ea-109">Attributes</span></span>  
 <span data-ttu-id="219ea-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="219ea-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="219ea-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="219ea-111">Child Elements</span></span>  
  
|<span data-ttu-id="219ea-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="219ea-112">Element</span></span>|<span data-ttu-id="219ea-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="219ea-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="219ea-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="219ea-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="219ea-115">Especifica la configuración para grupos de aplicaciones de IIS en un archivo aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="219ea-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="219ea-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="219ea-116">Parent Elements</span></span>  
  
|<span data-ttu-id="219ea-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="219ea-117">Element</span></span>|<span data-ttu-id="219ea-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="219ea-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="219ea-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="219ea-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="219ea-120">Especifica el elemento raíz necesario en cada archivo de configuración usado por Common Language Runtime y por las aplicaciones de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="219ea-120">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="219ea-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="219ea-121">Remarks</span></span>  
 <span data-ttu-id="219ea-122">El `system.web` elemento y su elemento secundario `applicationPool` elemento se agregaron a la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] de [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219ea-122">The `system.web` element and its child `applicationPool` element were added to the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="219ea-123">Al ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo integrado, esta combinación de elemento le permite configurar cómo administra los subprocesos de ASP.NET y cómo pone en cola las solicitudes cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="219ea-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="219ea-124">Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en el modo ISAPI o clásico, se omiten estos valores.</span><span class="sxs-lookup"><span data-stu-id="219ea-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="219ea-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="219ea-125">Example</span></span>  
 <span data-ttu-id="219ea-126">El ejemplo siguiente muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="219ea-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="219ea-127">El ejemplo se supone que se está ejecutando IIS en integrado modo y que la aplicación está utilizando el [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="219ea-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="219ea-128">Este comportamiento no se produce en las versiones de la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] anterior a la [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="219ea-128">This behavior does not occur in versions of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="219ea-129">Los valores en el ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="219ea-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="219ea-130">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="219ea-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="219ea-131">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="219ea-131">Namespace</span></span>||  
|<span data-ttu-id="219ea-132">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="219ea-132">Schema Name</span></span>||  
|<span data-ttu-id="219ea-133">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="219ea-133">Validation File</span></span>||  
|<span data-ttu-id="219ea-134">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="219ea-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="219ea-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="219ea-135">See Also</span></span>  
 [<span data-ttu-id="219ea-136">Elemento \<applicationPool> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="219ea-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
