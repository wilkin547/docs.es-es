---
title: Implementación de ClickOnce para formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- ClickOnce deployment [Windows Forms]
- Windows Forms, ClickOnce deployment
- walkthroughs [Windows Forms], ClickOnce deployment
ms.assetid: 1451fce9-1965-4a03-b4d3-831b5fe4ad66
ms.openlocfilehash: 0b76e07a23b105f2c1b4fb55a0d25bb52bcb9dc2
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44130081"
---
# <a name="clickonce-deployment-for-windows-forms"></a><span data-ttu-id="bd9a8-102">Implementación de ClickOnce para formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd9a8-102">ClickOnce Deployment for Windows Forms</span></span>
<span data-ttu-id="bd9a8-103">Los temas siguientes describen [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], una tecnología que se usa para implementar fácilmente aplicaciones de Windows Forms en equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-103">The following topics describe [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], a technology used for easily deploying Windows Forms applications to client computers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bd9a8-104">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="bd9a8-104">Related Sections</span></span>  
 [<span data-ttu-id="bd9a8-105">Elegir una estrategia de implementación ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-105">Choosing a ClickOnce Deployment Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy)  
 <span data-ttu-id="bd9a8-106">Presenta varias opciones para implementar aplicaciones [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd9a8-106">Presents several options for deploying [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications.</span></span>  
  
 [<span data-ttu-id="bd9a8-107">Elegir una estrategia de actualización de ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-107">Choosing a ClickOnce Update Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-update-strategy)  
 <span data-ttu-id="bd9a8-108">Presenta varias opciones para actualizar aplicaciones [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd9a8-108">Presents several options for updating [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications.</span></span>  
  
 [<span data-ttu-id="bd9a8-109">Proteger las aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-109">Securing ClickOnce Applications</span></span>](/visualstudio/deployment/securing-clickonce-applications)  
 <span data-ttu-id="bd9a8-110">Explica las implicaciones de seguridad de las implementaciones [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd9a8-110">Explains the security implications of [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] deployment.</span></span>  
  
 [<span data-ttu-id="bd9a8-111">Solucionar problemas en implementaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-111">Troubleshooting ClickOnce Deployments</span></span>](/visualstudio/deployment/troubleshooting-clickonce-deployments)  
 <span data-ttu-id="bd9a8-112">Describe distintos problemas que pueden producirse al implementar aplicaciones [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] y documenta los mensajes de error de nivel superior que [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] podría generar.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-112">Describes various problems that can occur when deploying [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications, and documents the top-level error messages that [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] might generate.</span></span>  
  
 [<span data-ttu-id="bd9a8-113">ClickOnce y la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="bd9a8-113">ClickOnce and Application Settings</span></span>](/visualstudio/deployment/clickonce-and-application-settings)  
 <span data-ttu-id="bd9a8-114">Describe funciona la implementación [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] con la configuración de la aplicación, que almacena la configuración de la aplicación y del usuario para su posterior recuperación.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-114">Describes how [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] deployment works with application settings, which stores application and user settings for future retrieval.</span></span>  
  
 [<span data-ttu-id="bd9a8-115">Introducción a la implementación de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="bd9a8-115">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)  
 <span data-ttu-id="bd9a8-116">Describe una característica de [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] que permite a las aplicaciones de confianza ejecutarse con un nivel de permisos superior en equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-116">Describes a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] feature that allows trusted applications to run with a higher level of permission on client computers.</span></span>  
  
 [<span data-ttu-id="bd9a8-117">ClickOnce y Authenticode</span><span class="sxs-lookup"><span data-stu-id="bd9a8-117">ClickOnce and Authenticode</span></span>](/visualstudio/deployment/clickonce-and-authenticode)  
 <span data-ttu-id="bd9a8-118">Describe cómo se usa la tecnología Authenticode en la implementación de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-118">Describes how Authenticode technology is used in trusted application deployment.</span></span>  
  
 [<span data-ttu-id="bd9a8-119">Tutorial: Implementar manualmente una aplicación ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-119">Walkthrough: Manually Deploying a ClickOnce Application</span></span>](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)  
 <span data-ttu-id="bd9a8-120">Muestra cómo usar la línea de comandos y las herramientas de SDK para implementar una aplicación [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] sin usar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-120">Demonstrates using command-line and SDK tools to deploy a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application without using Visual Studio.</span></span>  
  
 [<span data-ttu-id="bd9a8-121">Cómo: Agregar un publicador de confianza a un equipo cliente para aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-121">How to: Add a Trusted Publisher to a Client Computer for ClickOnce Applications</span></span>](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications)  
 <span data-ttu-id="bd9a8-122">Muestra la configuración única de equipos cliente necesaria para la implementación de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-122">Demonstrates the one-time configuration of client computers required for trusted application deployment.</span></span>  
  
 [<span data-ttu-id="bd9a8-123">Cómo: Especificar una ubicación alternativa para las actualizaciones de la implementación</span><span class="sxs-lookup"><span data-stu-id="bd9a8-123">How to: Specify an Alternate Location for Deployment Updates</span></span>](/visualstudio/deployment/how-to-specify-an-alternate-location-for-deployment-updates)  
 <span data-ttu-id="bd9a8-124">Muestra cómo configurar una aplicación [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] con herramientas de SDK para elegir una ubicación diferente para las nuevas versiones de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-124">Demonstrates configuring a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application, using SDK tools, to check a different location for new versions of an application.</span></span>  
  
 [<span data-ttu-id="bd9a8-125">Tutorial: Descargar ensamblados a petición con la API de implementación ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-125">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api)  
 <span data-ttu-id="bd9a8-126">Muestra cómo usar llamadas a la API para recuperar un ensamblado la primera vez que la aplicación intenta cargarlo.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-126">Demonstrates using API calls to retrieve an assembly the first time your application attempts to load it.</span></span>  
  
 [<span data-ttu-id="bd9a8-127">Cómo: Recuperar información de la cadena de consulta de una aplicación ClickOnce en línea</span><span class="sxs-lookup"><span data-stu-id="bd9a8-127">How to: Retrieve Query String Information in an Online ClickOnce Application</span></span>](/visualstudio/deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application)  
 <span data-ttu-id="bd9a8-128">Muestra cómo recuperar los parámetros de la dirección URL usada para ejecutar una aplicación [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd9a8-128">Demonstrates retrieving parameters from the URL used to run a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application.</span></span>  
  
 [<span data-ttu-id="bd9a8-129">Información general sobre la memoria caché de ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-129">ClickOnce Cache Overview</span></span>](/visualstudio/deployment/clickonce-cache-overview)  
 <span data-ttu-id="bd9a8-130">Describe la caché usada para almacenar las aplicaciones [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="bd9a8-130">Describes the cache used to store [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications on the local computer.</span></span>  
  
 [<span data-ttu-id="bd9a8-131">Obtener acceso local o remoto a los datos en aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-131">Accessing Local and Remote Data in ClickOnce Applications</span></span>](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)  
 <span data-ttu-id="bd9a8-132">Describe cómo acceder acceso los archivos de datos locales y los orígenes de datos remotos desde una aplicación [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd9a8-132">Describes how to access local data files and remote data sources from a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application.</span></span>  
  
 [<span data-ttu-id="bd9a8-133">Cómo: Incluir un archivo de datos en una aplicación ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-133">How to: Include a Data File in a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application)  
 <span data-ttu-id="bd9a8-134">Muestra cómo marcar un archivo para que esté disponible en el directorio de datos de [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd9a8-134">Demonstrates how to mark a file so that it is available in the [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] data directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9a8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd9a8-135">See Also</span></span>  
 [<span data-ttu-id="bd9a8-136">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="bd9a8-136">Application Settings Overview</span></span>](../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="bd9a8-137">Publicar aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-137">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)  
 [<span data-ttu-id="bd9a8-138">Compilar aplicaciones ClickOnce desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="bd9a8-138">Building ClickOnce Applications from the Command Line</span></span>](/visualstudio/deployment/building-clickonce-applications-from-the-command-line)  
 [<span data-ttu-id="bd9a8-139">Depurar aplicaciones ClickOnce que usan System.Deployment.Application</span><span class="sxs-lookup"><span data-stu-id="bd9a8-139">Debugging ClickOnce Applications That Use System.Deployment.Application</span></span>](https://msdn.microsoft.com/library/86f31948-2ca8-47c0-8e8b-c2b817bbf79f)  
 [<span data-ttu-id="bd9a8-140">Implementar componentes COM con ClickOnce</span><span class="sxs-lookup"><span data-stu-id="bd9a8-140">Deploying COM Components with ClickOnce</span></span>](/visualstudio/deployment/deploying-com-components-with-clickonce)  
 [<span data-ttu-id="bd9a8-141">Cómo: Publicar una aplicación ClickOnce mediante el Asistente para publicación</span><span class="sxs-lookup"><span data-stu-id="bd9a8-141">How to: Publish a ClickOnce Application using the Publish Wizard</span></span>](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)
