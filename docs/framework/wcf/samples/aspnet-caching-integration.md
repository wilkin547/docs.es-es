---
description: Más información acerca de la integración del almacenamiento en caché de ASP.NET
title: Integración de almacenamiento en caché de ASP.NET
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: c366efdc95cfa67f4fad9b8534edb047ad98ab32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755959"
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="6c23b-103">Integración de almacenamiento en caché de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6c23b-103">ASP.NET Caching Integration</span></span>

<span data-ttu-id="6c23b-104">En este ejemplo se muestra cómo utilizar la memoria caché de resultados de ASP.NET con el modelo de programación HTTP wEB de WCF.</span><span class="sxs-lookup"><span data-stu-id="6c23b-104">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="6c23b-105">Este tema se centra en la característica de integración de la memoria caché de resultados de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6c23b-105">This topic focuses on the ASP.NET output cache integration feature.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="6c23b-106">Muestra</span><span class="sxs-lookup"><span data-stu-id="6c23b-106">Demonstrates</span></span>

<span data-ttu-id="6c23b-107">Integración con la memoria caché de resultados de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6c23b-107">Integration with the ASP.NET Output Cache</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c23b-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6c23b-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6c23b-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6c23b-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="6c23b-110">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6c23b-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6c23b-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6c23b-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a><span data-ttu-id="6c23b-112">Debate</span><span class="sxs-lookup"><span data-stu-id="6c23b-112">Discussion</span></span>

<span data-ttu-id="6c23b-113">En el ejemplo <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> se usa para utilizar el almacenamiento en caché de resultados ASP.net con el servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6c23b-113">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="6c23b-114"><xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> se aplica a las operaciones de servicio y proporciona el nombre de un perfil de la memoria caché en un archivo de configuración que se debería aplicar a las respuestas de la operación dada.</span><span class="sxs-lookup"><span data-stu-id="6c23b-114">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>

<span data-ttu-id="6c23b-115">En el archivo Service.cs del proyecto de servicio de ejemplo, las `GetCustomer` `GetCustomers` operaciones y se marcan con el <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> , que proporciona el nombre del perfil de caché "CacheFor60Seconds".</span><span class="sxs-lookup"><span data-stu-id="6c23b-115">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="6c23b-116">En el archivo Web.config del proyecto de servicio, el perfil de caché "CacheFor60Seconds" se proporciona bajo el <`caching`> elemento de <`system.web`>.</span><span class="sxs-lookup"><span data-stu-id="6c23b-116">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="6c23b-117">Para este perfil de caché, el valor del `duration` atributo es "60", por lo que las respuestas asociadas a este perfil se almacenan en caché en la memoria caché de resultados de ASP.net durante 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="6c23b-117">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="6c23b-118">Además, para este perfil de caché, el `varmByParam` atributo se establece en "format", por lo que las solicitudes con valores diferentes para el `format` parámetro de cadena de consulta tienen sus respuestas almacenadas en caché por separado.</span><span class="sxs-lookup"><span data-stu-id="6c23b-118">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="6c23b-119">Por último, el atributo del perfil de caché `varyByHeader` se establece en "Accept", por lo que las solicitudes con distintos valores de encabezado Accept tienen sus respuestas almacenadas en caché por separado.</span><span class="sxs-lookup"><span data-stu-id="6c23b-119">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>

<span data-ttu-id="6c23b-120">Program.cs en el proyecto cliente muestra el modo en que se puede crear este tipo de cliente utilizando <xref:System.Net.HttpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="6c23b-120">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="6c23b-121">Observe que se trata simplemente de una manera de tener acceso a un servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="6c23b-121">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="6c23b-122">También es posible tener acceso al servicio utilizando otras clases de .NET Framework como el generador de canales de WCF y <xref:System.Net.WebClient> .</span><span class="sxs-lookup"><span data-stu-id="6c23b-122">It is also possible to access the service using other .NET Framework classes like the WCF channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="6c23b-123">Otros ejemplos del SDK (como el ejemplo de [servicio http básico](basic-http-service.md) ) muestran cómo utilizar estas clases para comunicarse con un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="6c23b-123">Other samples in the SDK (such as the [Basic HTTP Service](basic-http-service.md) sample) illustrate how to use these classes to communicate with a WCF service.</span></span>

## <a name="to-run-the-sample"></a><span data-ttu-id="6c23b-124">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c23b-124">To run the sample</span></span>

<span data-ttu-id="6c23b-125">El ejemplo consta de tres proyectos:</span><span class="sxs-lookup"><span data-stu-id="6c23b-125">The sample consists of three projects:</span></span>

- <span data-ttu-id="6c23b-126">**Servicio**: proyecto de aplicación web que incluye un servicio http de WCF hospedado en ASP.net.</span><span class="sxs-lookup"><span data-stu-id="6c23b-126">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>

- <span data-ttu-id="6c23b-127">**Cliente**: proyecto de aplicación de consola que realiza llamadas al servicio.</span><span class="sxs-lookup"><span data-stu-id="6c23b-127">**Client**: A console application project that makes calls to the service.</span></span>

- <span data-ttu-id="6c23b-128">**Común**: biblioteca compartida que contiene el tipo de cliente utilizado por el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c23b-128">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>

<span data-ttu-id="6c23b-129">Cuando se ejecuta la aplicación de consola Cliente, el cliente realiza las solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="6c23b-129">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>

#### <a name="to-run-the-sample"></a><span data-ttu-id="6c23b-130">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c23b-130">To run the sample</span></span>

1. <span data-ttu-id="6c23b-131">Abra la solución para obtener el ejemplo de integración del almacenamiento en caché de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6c23b-131">Open the solution for the ASP.NET Caching Integration Sample.</span></span>

2. <span data-ttu-id="6c23b-132">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="6c23b-132">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="6c23b-133">Si la ventana de **Explorador de soluciones** aún no está abierta, presione Ctrl + W + S.</span><span class="sxs-lookup"><span data-stu-id="6c23b-133">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>

4. <span data-ttu-id="6c23b-134">En la ventana de **Explorador de soluciones** , haga clic con el botón derecho en el proyecto de **servicio** y seleccione **Iniciar nueva instancia**.</span><span class="sxs-lookup"><span data-stu-id="6c23b-134">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="6c23b-135">De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c23b-135">This launches the ASP.NET development server, which hosts the service.</span></span>

5. <span data-ttu-id="6c23b-136">En la ventana de **Explorador de soluciones** , haga clic con el botón derecho en el proyecto de **cliente** y seleccione **Iniciar nueva instancia**.</span><span class="sxs-lookup"><span data-stu-id="6c23b-136">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>

6. <span data-ttu-id="6c23b-137">La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.</span><span class="sxs-lookup"><span data-stu-id="6c23b-137">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="6c23b-138">Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.</span><span class="sxs-lookup"><span data-stu-id="6c23b-138">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>

7. <span data-ttu-id="6c23b-139">A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.</span><span class="sxs-lookup"><span data-stu-id="6c23b-139">As the sample runs, the client writes the status of the current activity.</span></span>

8. <span data-ttu-id="6c23b-140">Presione cualquier tecla para terminar la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="6c23b-140">Press any key to terminate the client console application.</span></span>

9. <span data-ttu-id="6c23b-141">Presione MAYÚS+F5 para dejar de depurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="6c23b-141">Press SHIFT+F5 to stop debugging the service.</span></span>

10. <span data-ttu-id="6c23b-142">En el área de notificación de Windows, haga clic con el botón derecho en el icono del servidor de desarrollo ASP.NET y seleccione **detener**.</span><span class="sxs-lookup"><span data-stu-id="6c23b-142">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
