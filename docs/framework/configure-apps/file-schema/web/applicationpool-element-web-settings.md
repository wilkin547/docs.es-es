---
title: "&lt;applicationPool&gt; elemento (configuración Web)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d75e9eedf42523301b3c1745c05d90bcdafbdbf5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltapplicationpoolgt-element-web-settings"></a><span data-ttu-id="b8e45-102">&lt;applicationPool&gt; elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="b8e45-102">&lt;applicationPool&gt; Element (Web Settings)</span></span>
<span data-ttu-id="b8e45-103">Especifica la configuración que usa ASP.NET para administrar el comportamiento de todo el proceso cuando una aplicación ASP.NET se ejecuta en modo integrado en [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="b8e45-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b8e45-104">Este elemento y la característica que admite solo funcionan si la aplicación ASP.NET se hospeda en [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b8e45-104">This element and the feature it supports only work if your ASP.NET application is hosted on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="b8e45-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b8e45-105">\<configuration></span></span>  
<span data-ttu-id="b8e45-106">\<System.Web > elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="b8e45-106">\<system.web> Element (Web Settings)</span></span>  
<span data-ttu-id="b8e45-107">\<applicationPool > elemento (configuración Web)</span><span class="sxs-lookup"><span data-stu-id="b8e45-107">\<applicationPool> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e45-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8e45-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8e45-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b8e45-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b8e45-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b8e45-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8e45-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b8e45-111">Attributes</span></span>  
  
|<span data-ttu-id="b8e45-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="b8e45-112">Attribute</span></span>|<span data-ttu-id="b8e45-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8e45-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="b8e45-114">Especifica cuántas solicitudes simultáneas permite ASP.NET por CPU.</span><span class="sxs-lookup"><span data-stu-id="b8e45-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="b8e45-115">Especifica cuántos subprocesos simultáneos pueden estar en ejecución para un grupo de aplicaciones para cada CPU.</span><span class="sxs-lookup"><span data-stu-id="b8e45-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="b8e45-116">Esto proporciona una manera alternativa para controlar la simultaneidad ASP.NET, ya que permite limitar el número de subprocesos administrados que se puede usar por CPU para atender las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="b8e45-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="b8e45-117">De forma predeterminada este valor es 0, lo que significa que ASP.NET no limita el número de subprocesos que se pueden crear por CPU, aunque el grupo de subprocesos CLR también limita el número de subprocesos que se pueden crear.</span><span class="sxs-lookup"><span data-stu-id="b8e45-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="b8e45-118">Especifica el número máximo de solicitudes que pueden poner en cola para ASP.NET en un único proceso.</span><span class="sxs-lookup"><span data-stu-id="b8e45-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="b8e45-119">Cuando dos o más aplicaciones de ASP.NET se ejecutan en un único grupo de aplicaciones, el conjunto acumulativo de solicitudes que se realizan a cualquier aplicación en el grupo de aplicaciones está sujeto a esta configuración.</span><span class="sxs-lookup"><span data-stu-id="b8e45-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8e45-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b8e45-120">Child Elements</span></span>  
 <span data-ttu-id="b8e45-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b8e45-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8e45-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b8e45-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b8e45-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8e45-123">Element</span></span>|<span data-ttu-id="b8e45-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8e45-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8e45-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="b8e45-125">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="b8e45-126">Contiene información sobre cómo ASP.NET interactúa con una aplicación host.</span><span class="sxs-lookup"><span data-stu-id="b8e45-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8e45-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8e45-127">Remarks</span></span>  
 <span data-ttu-id="b8e45-128">Al ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o una versión posterior en el modo integrado, esta combinación de elementos permite configurar cómo administra ASP.NET los subprocesos y las colas de solicitudes cuando la aplicación se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="b8e45-128">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="b8e45-129">Si ejecuta IIS 6 o ejecutar [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] en modo clásico o en modo ISAPI, estos valores se omiten.</span><span class="sxs-lookup"><span data-stu-id="b8e45-129">If you run IIS 6 or you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
 <span data-ttu-id="b8e45-130">El `applicationPool` configuración se aplica a todos los grupos de aplicaciones que se ejecutan en una versión concreta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8e45-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="b8e45-131">La configuración se encuentra en un archivo aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="b8e45-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="b8e45-132">Hay una versión de este archivo para las versiones 2.0 y 4.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8e45-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="b8e45-133">(Las versiones 3.0 y 3.5 de .NET Framework comparten el archivo aspnet.config con la versión 2.0.)</span><span class="sxs-lookup"><span data-stu-id="b8e45-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b8e45-134">Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] en [!INCLUDE[win7](../../../../../includes/win7-md.md)], puede configurar un archivo aspnet.config diferente para cada grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b8e45-134">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="b8e45-135">Esto le permite adaptar el rendimiento de los subprocesos para cada grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b8e45-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
 <span data-ttu-id="b8e45-136">Para el `maxConcurrentRequestsPerCPU` configuración, el valor predeterminado de "5000" la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] eficazmente desactiva la limitación de solicitudes controlada por ASP.NET, a menos que realmente tenga 5000 o más solicitudes por CPU.</span><span class="sxs-lookup"><span data-stu-id="b8e45-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="b8e45-137">La configuración predeterminada depende en su lugar, el grupo de subprocesos CLR para administrar automáticamente la simultaneidad por CPU.</span><span class="sxs-lookup"><span data-stu-id="b8e45-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="b8e45-138">Las aplicaciones que hacen un amplio uso de procesamiento de solicitudes asincrónicas, o que tienen muchas solicitudes de ejecución prolongada bloqueadas en E/S de red, puede beneficiarse de la mayor límite predeterminado de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8e45-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="b8e45-139">Establecer `maxConcurrentRequestsPerCPU` en cero el uso de los subprocesos administrados se desactiva para procesar solicitudes ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b8e45-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="b8e45-140">Cuando una aplicación se ejecuta en un grupo de aplicaciones de IIS, las solicitudes permanecen en el subproceso de E/S de IIS y, por tanto, la simultaneidad está limitada por la configuración de subprocesos IIS.</span><span class="sxs-lookup"><span data-stu-id="b8e45-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
 <span data-ttu-id="b8e45-141">El `requestQueueLimit` configuración funciona del mismo modo que la `requestQueueLimit` atributo de la [processModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) elemento, que se establece en los archivos Web.config para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b8e45-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="b8e45-142">Sin embargo, el `requestQueueLimit` configuración en un archivo aspnet.config invalida el `requestQueueLimit` en un archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="b8e45-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="b8e45-143">En otras palabras, si se establecen ambos atributos (de forma predeterminada, esto es true), el `requestQueueLimit` configuración en el archivo aspnet.config tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="b8e45-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8e45-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8e45-144">Example</span></span>  
 <span data-ttu-id="b8e45-145">En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso ASP.NET en el archivo aspnet.config en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="b8e45-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
-   <span data-ttu-id="b8e45-146">La aplicación se hospeda en un [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b8e45-146">The application is hosted in an [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] application pool.</span></span>  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]<span data-ttu-id="b8e45-147">se está ejecutando en el modo integrado.</span><span class="sxs-lookup"><span data-stu-id="b8e45-147"> is running in Integrated mode.</span></span>  
  
-   <span data-ttu-id="b8e45-148">La aplicación está utilizando el [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="b8e45-148">The application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span>  
  
 <span data-ttu-id="b8e45-149">Los valores en el ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b8e45-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="b8e45-150">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="b8e45-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8e45-151">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b8e45-151">Namespace</span></span>||  
|<span data-ttu-id="b8e45-152">Nombre de esquema</span><span class="sxs-lookup"><span data-stu-id="b8e45-152">Schema Name</span></span>||  
|<span data-ttu-id="b8e45-153">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="b8e45-153">Validation File</span></span>||  
|<span data-ttu-id="b8e45-154">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="b8e45-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="b8e45-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8e45-155">See Also</span></span>  
 [<span data-ttu-id="b8e45-156">Elemento \<system.web> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="b8e45-156">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
