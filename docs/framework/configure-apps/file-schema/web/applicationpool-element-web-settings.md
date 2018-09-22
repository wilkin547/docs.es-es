---
title: '&lt;applicationPool&gt; elemento (configuración Web)'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1a129abca5888120d03c42689ac825d768733a9d
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46583738"
---
# <a name="ltapplicationpoolgt-element-web-settings"></a><span data-ttu-id="88588-102">&lt;applicationPool&gt; elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="88588-102">&lt;applicationPool&gt; Element (Web Settings)</span></span>
<span data-ttu-id="88588-103">Especifica la configuración que se usa ASP.NET para administrar el comportamiento de todo el proceso cuando se ejecuta una aplicación ASP.NET en el modo integrado en [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="88588-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88588-104">Este elemento y la característica admite solo funcionan si la aplicación ASP.NET se hospeda en [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="88588-104">This element and the feature it supports only work if your ASP.NET application is hosted on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="88588-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="88588-105">\<configuration></span></span>  
<span data-ttu-id="88588-106">\<System.Web > elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="88588-106">\<system.web> Element (Web Settings)</span></span>  
<span data-ttu-id="88588-107">\<applicationPool > elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="88588-107">\<applicationPool> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88588-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88588-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88588-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88588-109">Attributes and Elements</span></span>  
 <span data-ttu-id="88588-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="88588-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88588-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="88588-111">Attributes</span></span>  
  
|<span data-ttu-id="88588-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="88588-112">Attribute</span></span>|<span data-ttu-id="88588-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="88588-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="88588-114">Especifica cuántas solicitudes simultáneas por CPU, ASP.NET permite.</span><span class="sxs-lookup"><span data-stu-id="88588-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="88588-115">Especifica cuántos subprocesos simultáneos pueden estar en ejecución para un grupo de aplicaciones para cada CPU.</span><span class="sxs-lookup"><span data-stu-id="88588-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="88588-116">Esto proporciona una manera alternativa para controlar la simultaneidad ASP.NET, ya que permite limitar el número de subprocesos administrados que puede utilizarse por CPU para atender las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="88588-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="88588-117">De forma predeterminada este valor es 0, lo que significa que ASP.NET no limita el número de subprocesos que se pueden crear por CPU, aunque el grupo de subprocesos CLR también limita el número de subprocesos que se pueden crear.</span><span class="sxs-lookup"><span data-stu-id="88588-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="88588-118">Especifica el número máximo de solicitudes que pueden poner en cola para ASP.NET en un único proceso.</span><span class="sxs-lookup"><span data-stu-id="88588-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="88588-119">Cuando dos o más aplicaciones de ASP.NET se ejecutan en un único grupo de aplicaciones, el conjunto acumulativo de las solicitudes realizadas a cualquier aplicación en el grupo de aplicaciones está sujeto a esta configuración.</span><span class="sxs-lookup"><span data-stu-id="88588-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88588-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88588-120">Child Elements</span></span>  
 <span data-ttu-id="88588-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="88588-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88588-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88588-122">Parent Elements</span></span>  
  
|<span data-ttu-id="88588-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="88588-123">Element</span></span>|<span data-ttu-id="88588-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="88588-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88588-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="88588-125">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="88588-126">Contiene información sobre cómo ASP.NET interactúa con una aplicación host.</span><span class="sxs-lookup"><span data-stu-id="88588-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88588-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88588-127">Remarks</span></span>  
 <span data-ttu-id="88588-128">Al ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o una versión posterior en el modo integrado, esta combinación de elemento le permite configurar cómo ASP.NET administra las solicitudes de subprocesos y las colas cuando la aplicación se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="88588-128">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="88588-129">Si se ejecuta IIS 6 o ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] en modo clásico o en modo ISAPI, estas opciones se omiten.</span><span class="sxs-lookup"><span data-stu-id="88588-129">If you run IIS 6 or you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
 <span data-ttu-id="88588-130">El `applicationPool` configuración se aplica a todos los grupos de aplicaciones que se ejecutan en una versión concreta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88588-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="88588-131">La configuración se encuentra en un archivo aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="88588-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="88588-132">Hay una versión de este archivo para las versiones 2.0 y 4.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88588-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="88588-133">(Las versiones 3.0 y 3.5 de .NET Framework comparten el archivo aspnet.config con la versión 2.0).</span><span class="sxs-lookup"><span data-stu-id="88588-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88588-134">Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] en [!INCLUDE[win7](../../../../../includes/win7-md.md)], puede configurar un archivo aspnet.config diferente para cada grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="88588-134">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="88588-135">Esto le permite adaptar el rendimiento de los subprocesos para cada grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="88588-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
 <span data-ttu-id="88588-136">Para el `maxConcurrentRequestsPerCPU` establecimiento, el valor predeterminado de "5000" la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] eficazmente desactiva la limitación de solicitudes controlada por ASP.NET, a menos que realmente tenga 5000 o más solicitudes por CPU.</span><span class="sxs-lookup"><span data-stu-id="88588-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="88588-137">El valor predeterminado depende de en su lugar, el grupo de subprocesos CLR administrar automáticamente la simultaneidad por CPU.</span><span class="sxs-lookup"><span data-stu-id="88588-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="88588-138">Las aplicaciones que hacen un uso extensivo de procesamiento de solicitudes asincrónicas, o que tienen muchas solicitudes de ejecución prolongada bloqueadas en E/S de red, se beneficiarán de la mayor límite predeterminado de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88588-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="88588-139">Establecer `maxConcurrentRequestsPerCPU` a cero, se desactivará el uso de subprocesos administrados para procesar las solicitudes ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="88588-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="88588-140">Cuando una aplicación se ejecuta en un grupo de aplicaciones de IIS, las solicitudes permanecen en el subproceso de E/S de IIS y, por tanto, simultaneidad está limitada por la configuración de subprocesos IIS.</span><span class="sxs-lookup"><span data-stu-id="88588-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
 <span data-ttu-id="88588-141">El `requestQueueLimit` configuración funciona del mismo modo que el `requestQueueLimit` atributo de la [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) elemento, que se establece en los archivos Web.config para aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="88588-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="88588-142">Sin embargo, el `requestQueueLimit` invalida la configuración en un archivo aspnet.config el `requestQueueLimit` en un archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="88588-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="88588-143">En otras palabras, si se establecen ambos atributos (de forma predeterminada, esto es true), el `requestQueueLimit` configuración en el archivo aspnet.config tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="88588-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88588-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88588-144">Example</span></span>  
 <span data-ttu-id="88588-145">El ejemplo siguiente muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="88588-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
-   <span data-ttu-id="88588-146">La aplicación se hospeda en un [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="88588-146">The application is hosted in an [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] application pool.</span></span>  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]<span data-ttu-id="88588-147"> se está ejecutando en el modo integrado.</span><span class="sxs-lookup"><span data-stu-id="88588-147"> is running in Integrated mode.</span></span>  
  
-   <span data-ttu-id="88588-148">La aplicación usa el [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="88588-148">The application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span>  
  
 <span data-ttu-id="88588-149">Los valores en el ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="88588-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="88588-150">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="88588-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88588-151">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="88588-151">Namespace</span></span>||  
|<span data-ttu-id="88588-152">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="88588-152">Schema Name</span></span>||  
|<span data-ttu-id="88588-153">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="88588-153">Validation File</span></span>||  
|<span data-ttu-id="88588-154">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="88588-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="88588-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="88588-155">See Also</span></span>  
 [<span data-ttu-id="88588-156">Elemento \<system.web> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="88588-156">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
