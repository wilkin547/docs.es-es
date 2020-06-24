---
title: Acceder al servicio desde un explorador web (Inicio rápido de Data Services de WCF)
description: Aprenda a iniciar WCF Data Services en Visual Studio y a deshabilitar la lectura de fuentes en un explorador. Obtiene el documento de definición de servicio y obtiene acceso a los recursos del servicio de datos.
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 713436c31bc3f622c4f44a83e33fff3fcbba1c1c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247783"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="f8f02-104">Acceder al servicio desde un explorador web (Inicio rápido de Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="f8f02-104">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="f8f02-105">Esta es la segunda tarea de la guía de inicio rápido de WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="f8f02-105">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="f8f02-106">En esta tarea, iniciará el WCF Data Services desde Visual Studio y, opcionalmente, deshabilitará la lectura de fuentes en el explorador Web.</span><span class="sxs-lookup"><span data-stu-id="f8f02-106">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="f8f02-107">A continuación, recupere el documento de definición de servicio, así como el acceso a los recursos del servicio de datos mediante el envío de solicitudes HTTP GET a través de un explorador Web a los recursos expuestos.</span><span class="sxs-lookup"><span data-stu-id="f8f02-107">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="f8f02-108">De forma predeterminada, Visual Studio asigna automáticamente un número de puerto al URI `localhost` en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f8f02-108">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="f8f02-109">En esta tarea se usa el número de puerto `12345` en los ejemplos de URI.</span><span class="sxs-lookup"><span data-stu-id="f8f02-109">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="f8f02-110">Para obtener más información sobre cómo establecer un número de puerto específico en el proyecto de Visual Studio, vea [crear el servicio de datos](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="f8f02-110">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="f8f02-111">Para solicitar el documento de servicio predeterminado utilizando Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="f8f02-111">To request the default service document by using Internet Explorer</span></span>

1. <span data-ttu-id="f8f02-112">En Internet Explorer, en el menú **herramientas** , seleccione **Opciones de Internet**, haga clic en la pestaña **contenido** , haga clic en **configuración**y desactive **activar la visualización de fuentes**.</span><span class="sxs-lookup"><span data-stu-id="f8f02-112">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="f8f02-113">De este modo, se garantiza que la lectura de fuentes queda deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="f8f02-113">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="f8f02-114">Si no deshabilita esta funcionalidad, el explorador web tratará el documento codificado como AtomPub devuelto como si fuera una fuente XML en lugar de mostrar los datos XML sin formato.</span><span class="sxs-lookup"><span data-stu-id="f8f02-114">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8f02-115">Si el explorador no puede mostrar la fuente como datos XML sin formato, todavía debería poder ver la fuente como el código fuente de la página.</span><span class="sxs-lookup"><span data-stu-id="f8f02-115">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2. <span data-ttu-id="f8f02-116">En Visual Studio, presione la tecla **F5** para iniciar la depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8f02-116">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3. <span data-ttu-id="f8f02-117">Abra un explorador web en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f8f02-117">Open a Web browser on the local computer.</span></span> <span data-ttu-id="f8f02-118">En la barra de direcciones, escriba el siguiente URI:</span><span class="sxs-lookup"><span data-stu-id="f8f02-118">In the address bar, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="f8f02-119">De esta forma, se devuelve el documento de servicio predeterminado, que contiene una lista de los conjuntos de entidades expuestos por este servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="f8f02-119">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="f8f02-120">Para tener acceso a los recursos del conjunto de entidades desde un explorador web</span><span class="sxs-lookup"><span data-stu-id="f8f02-120">To access entity set resources from a Web browser</span></span>

1. <span data-ttu-id="f8f02-121">En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8f02-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="f8f02-122">Esto devuelve un conjunto de todos los clientes de la base de datos de ejemplo Northwind.</span><span class="sxs-lookup"><span data-stu-id="f8f02-122">This returns a set of all customers in the Northwind sample database.</span></span>

2. <span data-ttu-id="f8f02-123">En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8f02-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="f8f02-124">De esta forma, se devuelve una instancia de la entidad para un cliente concreto, `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="f8f02-124">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3. <span data-ttu-id="f8f02-125">En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8f02-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="f8f02-126">De esta forma, se recorre la relación entre clientes y pedidos para devolver un conjunto de todos los pedidos para ese cliente, `ALFKI`.</span><span class="sxs-lookup"><span data-stu-id="f8f02-126">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4. <span data-ttu-id="f8f02-127">En el campo de la barra de direcciones del explorador web, escriba el URI siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8f02-127">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="f8f02-128">De esta forma, se filtran los pedidos que pertenecen a un cliente determinado, `ALFKI`, de modo que solo se devuelve un pedido concreto dependiendo del valor proporcionado para `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="f8f02-128">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8f02-129">Pasos a seguir</span><span class="sxs-lookup"><span data-stu-id="f8f02-129">Next Steps</span></span>

<span data-ttu-id="f8f02-130">Ha tenido acceso correctamente al WCF Data Services desde un explorador Web, con el explorador emitiendo solicitudes GET de HTTP a los recursos especificados.</span><span class="sxs-lookup"><span data-stu-id="f8f02-130">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="f8f02-131">Un explorador web es un modo sencillo de experimentar con la sintaxis de direccionamiento de las solicitudes y de ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="f8f02-131">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="f8f02-132">Sin embargo, este método no se suele emplear para obtener acceso a un servicio de datos de producción.</span><span class="sxs-lookup"><span data-stu-id="f8f02-132">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="f8f02-133">Habitualmente, las aplicaciones interactúan con el servicio de datos mediante el código de la aplicación o los lenguajes de script.</span><span class="sxs-lookup"><span data-stu-id="f8f02-133">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="f8f02-134">A continuación, creará una aplicación cliente que usa las bibliotecas de cliente para tener acceso a los recursos del servicio de datos como si fueran objetos de Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="f8f02-134">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f8f02-135">Creación de la aplicación cliente de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f8f02-135">Creating the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="f8f02-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8f02-136">See also</span></span>

- [<span data-ttu-id="f8f02-137">Acceso a recursos de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="f8f02-137">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
