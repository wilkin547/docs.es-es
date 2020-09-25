---
title: Elemento <applicationPool> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 963b25e57ae8c2cc59dcc3e50ae2a52cc04f54a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185644"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="4c7e6-102">Elemento \<applicationPool> (configuración web)</span><span class="sxs-lookup"><span data-stu-id="4c7e6-102">\<applicationPool> Element (Web Settings)</span></span>

<span data-ttu-id="4c7e6-103">Especifica los valores de configuración que usa ASP.NET para administrar el comportamiento de todo el proceso cuando una aplicación ASP.NET se ejecuta en modo integrado en IIS 7,0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4c7e6-104">Este elemento y la característica que admite solo funcionan si la aplicación ASP.NET se hospeda en IIS 7,0 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**  
  
## <a name="syntax"></a><span data-ttu-id="4c7e6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c7e6-105">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c7e6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4c7e6-106">Attributes and Elements</span></span>  

<span data-ttu-id="4c7e6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c7e6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="4c7e6-108">Attributes</span></span>  
  
|<span data-ttu-id="4c7e6-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="4c7e6-109">Attribute</span></span>|<span data-ttu-id="4c7e6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c7e6-110">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="4c7e6-111">Especifica cuántas solicitudes simultáneas ASP.NET permite por CPU.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-111">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="4c7e6-112">Especifica el número de subprocesos simultáneos que se pueden ejecutar para un grupo de aplicaciones para cada CPU.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-112">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="4c7e6-113">Esto proporciona una manera alternativa de controlar la simultaneidad de ASP.NET, ya que puede limitar el número de subprocesos administrados que se pueden usar por CPU para atender las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-113">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="4c7e6-114">De forma predeterminada, este valor es 0, lo que significa que ASP.NET no limita el número de subprocesos que se pueden crear por CPU, aunque el grupo de subprocesos de CLR también limita el número de subprocesos que se pueden crear.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-114">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="4c7e6-115">Especifica el número máximo de solicitudes que se pueden poner en cola para ASP.NET en un único proceso.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-115">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="4c7e6-116">Cuando dos o más aplicaciones ASP.NET se ejecutan en un único grupo de aplicaciones, el conjunto acumulativo de solicitudes que se realizan a cualquier aplicación en el grupo de aplicaciones está sujeto a esta configuración.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-116">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c7e6-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4c7e6-117">Child Elements</span></span>  

 <span data-ttu-id="4c7e6-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c7e6-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4c7e6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4c7e6-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c7e6-120">Element</span></span>|<span data-ttu-id="4c7e6-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c7e6-121">Description</span></span>|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|<span data-ttu-id="4c7e6-122">Contiene información sobre cómo interactúa ASP.NET con una aplicación host.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-122">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c7e6-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c7e6-123">Remarks</span></span>  

<span data-ttu-id="4c7e6-124">Al ejecutar IIS 7,0 o una versión posterior en el modo integrado, esta combinación de elementos le permite configurar el modo en que ASP.NET administra los subprocesos y pone en cola las solicitudes cuando la aplicación se hospeda en un grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-124">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="4c7e6-125">Si ejecuta IIS 6 o ejecuta IIS 7,0 en modo clásico o en modo ISAPI, se omite esta configuración.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-125">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="4c7e6-126">La `applicationPool` configuración se aplica a todos los grupos de aplicaciones que se ejecutan en una versión determinada del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-126">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="4c7e6-127">La configuración se encuentra en un archivo de aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-127">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="4c7e6-128">Hay una versión de este archivo para las versiones 2,0 y 4,0 del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-128">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="4c7e6-129">(Las versiones 3,0 y 3,5 del .NET Framework compartir el archivo de aspnet.config con la versión 2,0).</span><span class="sxs-lookup"><span data-stu-id="4c7e6-129">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4c7e6-130">Si ejecuta IIS 7,0 en Windows 7, puede configurar un archivo de aspnet.config independiente para cada grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-130">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="4c7e6-131">Esto le permite adaptar el rendimiento de los subprocesos de cada grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-131">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="4c7e6-132">En el caso de la `maxConcurrentRequestsPerCPU` configuración, el valor predeterminado de "5000" en el .NET Framework 4 desactiva eficazmente la limitación de solicitudes que está controlada por ASP.net, a menos que tenga en realidad 5000 o más solicitudes por CPU.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-132">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="4c7e6-133">La configuración predeterminada depende en su lugar del grupo de subprocesos de CLR para administrar automáticamente la simultaneidad por CPU.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-133">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="4c7e6-134">Las aplicaciones que hacen un uso intensivo del procesamiento de solicitudes asincrónicas, o que tienen muchas solicitudes de ejecución prolongada bloqueadas en e/s de red, se beneficiarán del aumento del límite predeterminado en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-134">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="4c7e6-135">Si `maxConcurrentRequestsPerCPU` se establece en cero, se desactiva el uso de subprocesos administrados para procesar solicitudes ASP.net.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-135">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="4c7e6-136">Cuando una aplicación se ejecuta en un grupo de aplicaciones de IIS, las solicitudes permanecen en el subproceso de e/s de IIS y, por lo tanto, la simultaneidad se limita mediante la configuración del subproceso de IIS.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-136">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="4c7e6-137">La `requestQueueLimit` configuración funciona de la misma manera que el `requestQueueLimit` atributo del elemento [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) , que se establece en la Web.config archivos para las aplicaciones ASP.net.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-137">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="4c7e6-138">Sin embargo, la `requestQueueLimit` configuración de un archivo de aspnet.config invalida la `requestQueueLimit` configuración de un archivo de Web.config.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-138">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="4c7e6-139">En otras palabras, si se establecen ambos atributos (de forma predeterminada, es true), la `requestQueueLimit` configuración del archivo aspnet.config tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-139">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c7e6-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c7e6-140">Example</span></span>  

<span data-ttu-id="4c7e6-141">En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo aspnet.config en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="4c7e6-141">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="4c7e6-142">La aplicación se hospeda en un grupo de aplicaciones de IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-142">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="4c7e6-143">IIS 7,0 se está ejecutando en modo integrado.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-143">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="4c7e6-144">La aplicación está usando .NET Framework 3,5 SP1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-144">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="4c7e6-145">Los valores del ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="4c7e6-145">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="4c7e6-146">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="4c7e6-146">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c7e6-147">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4c7e6-147">Namespace</span></span>||  
|<span data-ttu-id="4c7e6-148">Nombre del esquema</span><span class="sxs-lookup"><span data-stu-id="4c7e6-148">Schema Name</span></span>||  
|<span data-ttu-id="4c7e6-149">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="4c7e6-149">Validation File</span></span>||  
|<span data-ttu-id="4c7e6-150">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="4c7e6-150">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="4c7e6-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c7e6-151">See also</span></span>

- [<span data-ttu-id="4c7e6-152">\<system.web> (Elemento, configuración Web)</span><span class="sxs-lookup"><span data-stu-id="4c7e6-152">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
