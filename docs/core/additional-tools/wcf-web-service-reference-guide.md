---
title: Adición de WCF Web Service Reference
description: Información general sobre la herramienta Microsoft WCF Web Service Reference Provider, que agrega funciones para proyectos de .NET Core y ASP.NET Core, similares a Agregar referencia de servicio para proyectos de .NET Framework.
author: dasetser
ms.date: 10/29/2019
ms.custom: mvc
ms.openlocfilehash: cdd6b457d289dd7b752c97c5645f0797f24b72aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715681"
---
# <a name="use-the-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="f8935-103">Uso de la herramienta WCF Web Service Reference Provider</span><span class="sxs-lookup"><span data-stu-id="f8935-103">Use the WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="f8935-104">Durante años, muchos desarrolladores de Visual Studio han disfrutado de la productividad que ofrecía la herramienta [**Agregar referencia de servicio**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) cuando sus proyectos de .NET Framework necesitaban acceder a servicios web.</span><span class="sxs-lookup"><span data-stu-id="f8935-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="f8935-105">La herramienta **WCF Web Service Reference Provider** es una extensión de servicio conectada de Visual Studio que proporciona una experiencia similar a la función Agregar referencia de servicio para proyectos de .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f8935-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="f8935-106">Esta herramienta recupera metadatos de un servicio web en la solución actual, en una ubicación de red o desde un archivo WSDL, y genera un archivo de origen compatible con .NET Core. El archivo contiene el código de proxy de cliente e Windows Communication Foundation (WCF) y podrá usarlo para acceder al servicio web.</span><span class="sxs-lookup"><span data-stu-id="f8935-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8935-107">Solo debe hacer referencia a servicios desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="f8935-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="f8935-108">Si agrega referencias desde un origen que no es de confianza podría poner en peligro la seguridad.</span><span class="sxs-lookup"><span data-stu-id="f8935-108">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f8935-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f8935-109">Prerequisites</span></span>

- <span data-ttu-id="f8935-110">[Visual Studio 2017, versión 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f8935-110">[Visual Studio 2017 version 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) or later versions</span></span>

## <a name="how-to-use-the-extension"></a><span data-ttu-id="f8935-111">Cómo utilizar la extensión</span><span class="sxs-lookup"><span data-stu-id="f8935-111">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="f8935-112">La opción **WCF Web Service Reference** (Referencia de servicio web de WCF) se puede aplicar a proyectos creados mediante las siguientes plantillas de proyecto:</span><span class="sxs-lookup"><span data-stu-id="f8935-112">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
>
> - <span data-ttu-id="f8935-113">**Visual C#**  >  **.NET Core**</span><span class="sxs-lookup"><span data-stu-id="f8935-113">**Visual C#** > **.NET Core**</span></span>
> - <span data-ttu-id="f8935-114">**Visual C#**  >  **.NET Standard**</span><span class="sxs-lookup"><span data-stu-id="f8935-114">**Visual C#** > **.NET Standard**</span></span>
> - <span data-ttu-id="f8935-115">**Visual C#**  > **Web** > **Aplicación web de ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="f8935-115">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="f8935-116">En este artículo se usa la plantilla de proyecto **Aplicación web de ASP.NET Core** para explicar cómo agregar una referencia de servicio web de WCF al proyecto:</span><span class="sxs-lookup"><span data-stu-id="f8935-116">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="f8935-117">En el Explorador de soluciones, haga doble clic en el nodo **Servicios conectados** del proyecto (para un proyecto de .NET Core o .NET Standard, esta opción está disponible cuando hace clic con el botón derecho en el nodo **Dependencias** del proyecto en el Explorador de soluciones).</span><span class="sxs-lookup"><span data-stu-id="f8935-117">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

    <span data-ttu-id="f8935-118">Aparece la página **Servicios conectados**, como se muestra en esta imagen:</span><span class="sxs-lookup"><span data-stu-id="f8935-118">The **Connected Services** page appears as shown in the following image:</span></span>

    ![Pestaña Servicios conectados de Visual Studio para .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="f8935-120">En la página **Servicios conectados**, haga clic en **Microsoft WCF Web Service Reference Provider**.</span><span class="sxs-lookup"><span data-stu-id="f8935-120">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="f8935-121">Se abrirá el asistente para **Configurar referencia de servicio web de WCF**:</span><span class="sxs-lookup"><span data-stu-id="f8935-121">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

    ![Pestaña Punto de conexión de servicio de Visual Studio para .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="f8935-123">Seleccione un servicio.</span><span class="sxs-lookup"><span data-stu-id="f8935-123">Select a service.</span></span>

    <span data-ttu-id="f8935-124">3a.</span><span class="sxs-lookup"><span data-stu-id="f8935-124">3a.</span></span> <span data-ttu-id="f8935-125">Hay varias opciones de búsqueda de servicios disponibles en el asistente para **Configurar referencia de servicio web de WCF**:</span><span class="sxs-lookup"><span data-stu-id="f8935-125">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>

     * <span data-ttu-id="f8935-126">Para buscar servicios definidos en la solución actual, haga clic en el botón **Detectar**.</span><span class="sxs-lookup"><span data-stu-id="f8935-126">To search for services defined in the current solution, click the **Discover** button.</span></span>
     * <span data-ttu-id="f8935-127">Para buscar servicios hospedados en una dirección específica, escriba la dirección URL del servicio en el cuadro **Dirección** y haga clic en el botón **Ir**.</span><span class="sxs-lookup"><span data-stu-id="f8935-127">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="f8935-128">Para seleccionar un archivo WSDL que contiene la información de metadatos del servicio web, haga clic en el botón **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="f8935-128">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span>

    <span data-ttu-id="f8935-129">3b.</span><span class="sxs-lookup"><span data-stu-id="f8935-129">3b.</span></span> <span data-ttu-id="f8935-130">Seleccione el servicio de la lista de resultados de búsqueda en el cuadro **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="f8935-130">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="f8935-131">Si es necesario, escriba el espacio de nombres para el código generado en el cuadro de texto **Espacio de nombres** correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f8935-131">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>

    <span data-ttu-id="f8935-132">3c.</span><span class="sxs-lookup"><span data-stu-id="f8935-132">3c.</span></span> <span data-ttu-id="f8935-133">Haga clic en el botón **Siguiente** para abrir las páginas **Opciones de tipo de datos** y **Opciones de cliente**.</span><span class="sxs-lookup"><span data-stu-id="f8935-133">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="f8935-134">O bien, haga clic en el botón **Finalizar** para usar las opciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="f8935-134">Alternatively, click the **Finish** button to use the default options.</span></span>

4. <span data-ttu-id="f8935-135">El formulario **Opciones de tipo de datos** permite ajustar los valores de configuración de la referencia de servicio generada:</span><span class="sxs-lookup"><span data-stu-id="f8935-135">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

    ![Pestaña Tipo de datos de Visual Studio para .NET Core](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

    > [!NOTE]
    > <span data-ttu-id="f8935-137">La opción de la casilla **Reutilizar tipos en los ensamblados a los que se hace referencia** es útil cuando se definen los tipos de datos necesarios para la generación de código de referencia de servicio en uno de los ensamblados de referencia del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f8935-137">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="f8935-138">Es importante volver a usar esos tipos de datos existentes para evitar problemas de tiempo de ejecución o conflictos de tipo de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="f8935-138">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

    <span data-ttu-id="f8935-139">Puede haber un retraso mientras se carga la información de tipo, en función del número de dependencias del proyecto y otros factores de rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="f8935-139">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="f8935-140">El botón **Finalizar** está deshabilitado durante la carga, a menos que la casilla **Reutilizar tipos en los ensamblados a los que se hace referencia** esté desactivada.</span><span class="sxs-lookup"><span data-stu-id="f8935-140">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="f8935-141">Haga clic en **Finalizar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="f8935-141">Click **Finish** when you are done.</span></span>

<span data-ttu-id="f8935-142">Mientras muestra el progreso, la herramienta:</span><span class="sxs-lookup"><span data-stu-id="f8935-142">While displaying progress, the tool:</span></span>

- <span data-ttu-id="f8935-143">Descarga los metadatos del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="f8935-143">Downloads metadata from the WCF service.</span></span>
- <span data-ttu-id="f8935-144">Genera el código de referencia de servicio en un archivo con el nombre *reference.cs* y lo agrega al proyecto bajo el nodo **Servicios conectados**.</span><span class="sxs-lookup"><span data-stu-id="f8935-144">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span>
- <span data-ttu-id="f8935-145">Actualiza el archivo de proyecto (.csproj) con las referencias del paquete NuGet necesarias para compilarlo y ejecutarlo en la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="f8935-145">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![Ventana Progreso de Visual Studio](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="f8935-147">Cuando se completan estos procesos, puede crear una instancia del tipo de cliente WCF generado e invocar las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="f8935-147">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8935-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8935-148">See also</span></span>

- [<span data-ttu-id="f8935-149">Introducción a las aplicaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f8935-149">Get started with Windows Communication Foundation applications</span></span>](../../framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="f8935-150">Servicios de Windows Communication Foundation y servicios de datos WCF en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f8935-150">Windows Communication Foundation services and WCF data services in Visual Studio</span></span>](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio)
- [<span data-ttu-id="f8935-151">Características compatibles con WCF en .NET Core</span><span class="sxs-lookup"><span data-stu-id="f8935-151">WCF supported features on .NET Core</span></span>](https://github.com/dotnet/wcf/blob/master/release-notes/SupportedFeatures-v2.1.0.md)

## <a name="feedback--questions"></a><span data-ttu-id="f8935-152">Preguntas y comentarios</span><span class="sxs-lookup"><span data-stu-id="f8935-152">Feedback & questions</span></span>

<span data-ttu-id="f8935-153">Si tiene alguna pregunta o comentario, notifíquelo en la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/) mediante la herramienta [Notificar un problema](/visualstudio/ide/how-to-report-a-problem-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f8935-153">If you have any questions or feedback, report it at [Developer Community](https://developercommunity.visualstudio.com/) using the [Report a problem](/visualstudio/ide/how-to-report-a-problem-with-visual-studio) tool.</span></span>

## <a name="release-notes"></a><span data-ttu-id="f8935-154">Notas de la versión</span><span class="sxs-lookup"><span data-stu-id="f8935-154">Release notes</span></span>

- <span data-ttu-id="f8935-155">Eche un vistazo a las [notas de la versión](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) para obtener información actualizada sobre la versión, incluidos los problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="f8935-155">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span>
