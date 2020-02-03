---
title: Implementación ClickOnce
ms.date: 03/30/2017
helpviewer_keywords:
- ClickOnce deployment [Windows Forms]
- Windows Forms, ClickOnce deployment
- walkthroughs [Windows Forms], ClickOnce deployment
ms.assetid: 1451fce9-1965-4a03-b4d3-831b5fe4ad66
ms.openlocfilehash: 13b65173e8aff81a554350942d2559cf2b5395ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746334"
---
# <a name="clickonce-deployment-for-windows-forms"></a><span data-ttu-id="54a0c-102">Implementación de ClickOnce para formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="54a0c-102">ClickOnce Deployment for Windows Forms</span></span>
<span data-ttu-id="54a0c-103">En los temas siguientes se describe ClickOnce, una tecnología que se usa para implementar fácilmente aplicaciones Windows Forms en equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="54a0c-103">The following topics describe ClickOnce, a technology used for easily deploying Windows Forms applications to client computers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="54a0c-104">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="54a0c-104">Related Sections</span></span>  
 [<span data-ttu-id="54a0c-105">Elegir una estrategia de implementación ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-105">Choosing a ClickOnce Deployment Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy)  
 <span data-ttu-id="54a0c-106">Presenta varias opciones para implementar aplicaciones ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="54a0c-106">Presents several options for deploying ClickOnce applications.</span></span>  
  
 [<span data-ttu-id="54a0c-107">Elegir una estrategia de actualización de ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-107">Choosing a ClickOnce Update Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-update-strategy)  
 <span data-ttu-id="54a0c-108">Presenta varias opciones para actualizar las aplicaciones ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="54a0c-108">Presents several options for updating ClickOnce applications.</span></span>  
  
 [<span data-ttu-id="54a0c-109">Proteger las aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-109">Securing ClickOnce Applications</span></span>](/visualstudio/deployment/securing-clickonce-applications)  
 <span data-ttu-id="54a0c-110">Explica las implicaciones de seguridad de la implementación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="54a0c-110">Explains the security implications of ClickOnce deployment.</span></span>  
  
 [<span data-ttu-id="54a0c-111">Solucionar problemas en implementaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-111">Troubleshooting ClickOnce Deployments</span></span>](/visualstudio/deployment/troubleshooting-clickonce-deployments)  
 <span data-ttu-id="54a0c-112">Describe varios problemas que pueden producirse al implementar aplicaciones ClickOnce y documenta los mensajes de error de nivel superior que puede generar ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="54a0c-112">Describes various problems that can occur when deploying ClickOnce applications, and documents the top-level error messages that ClickOnce might generate.</span></span>  
  
 [<span data-ttu-id="54a0c-113">ClickOnce y la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="54a0c-113">ClickOnce and Application Settings</span></span>](/visualstudio/deployment/clickonce-and-application-settings)  
 <span data-ttu-id="54a0c-114">Describe cómo funciona la implementación ClickOnce con la configuración de la aplicación, que almacena la configuración de la aplicación y del usuario para su posterior recuperación.</span><span class="sxs-lookup"><span data-stu-id="54a0c-114">Describes how ClickOnce deployment works with application settings, which stores application and user settings for future retrieval.</span></span>  
  
 [<span data-ttu-id="54a0c-115">Introducción a la implementación de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="54a0c-115">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)  
 <span data-ttu-id="54a0c-116">Describe una característica ClickOnce que permite a las aplicaciones de confianza ejecutarse con un nivel de permiso superior en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="54a0c-116">Describes a ClickOnce feature that allows trusted applications to run with a higher level of permission on client computers.</span></span>  
  
 [<span data-ttu-id="54a0c-117">ClickOnce y Authenticode</span><span class="sxs-lookup"><span data-stu-id="54a0c-117">ClickOnce and Authenticode</span></span>](/visualstudio/deployment/clickonce-and-authenticode)  
 <span data-ttu-id="54a0c-118">Describe cómo se usa la tecnología Authenticode en la implementación de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="54a0c-118">Describes how Authenticode technology is used in trusted application deployment.</span></span>  
  
 [<span data-ttu-id="54a0c-119">Tutorial: Implementar manualmente una aplicación ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-119">Walkthrough: Manually Deploying a ClickOnce Application</span></span>](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)  
 <span data-ttu-id="54a0c-120">Muestra cómo usar las herramientas de línea de comandos y SDK para implementar una aplicación ClickOnce sin usar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="54a0c-120">Demonstrates using command-line and SDK tools to deploy a ClickOnce application without using Visual Studio.</span></span>  
  
 [<span data-ttu-id="54a0c-121">Cómo: Agregar un publicador de confianza a un equipo cliente para aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-121">How to: Add a Trusted Publisher to a Client Computer for ClickOnce Applications</span></span>](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications)  
 <span data-ttu-id="54a0c-122">Muestra la configuración única de equipos cliente necesaria para la implementación de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="54a0c-122">Demonstrates the one-time configuration of client computers required for trusted application deployment.</span></span>  
  
 [<span data-ttu-id="54a0c-123">Cómo: Especificar una ubicación alternativa para las actualizaciones de la implementación</span><span class="sxs-lookup"><span data-stu-id="54a0c-123">How to: Specify an Alternate Location for Deployment Updates</span></span>](/visualstudio/deployment/how-to-specify-an-alternate-location-for-deployment-updates)  
 <span data-ttu-id="54a0c-124">Muestra cómo configurar una aplicación ClickOnce mediante herramientas de SDK, para comprobar una ubicación diferente para las nuevas versiones de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="54a0c-124">Demonstrates configuring a ClickOnce application, using SDK tools, to check a different location for new versions of an application.</span></span>  
  
 [<span data-ttu-id="54a0c-125">Tutorial: Descargar ensamblados a petición con la API de implementación ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-125">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api)  
 <span data-ttu-id="54a0c-126">Muestra cómo usar llamadas a la API para recuperar un ensamblado la primera vez que la aplicación intenta cargarlo.</span><span class="sxs-lookup"><span data-stu-id="54a0c-126">Demonstrates using API calls to retrieve an assembly the first time your application attempts to load it.</span></span>  
  
 [<span data-ttu-id="54a0c-127">Cómo: Recuperar información de la cadena de consulta de una aplicación ClickOnce en línea</span><span class="sxs-lookup"><span data-stu-id="54a0c-127">How to: Retrieve Query String Information in an Online ClickOnce Application</span></span>](/visualstudio/deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application)  
 <span data-ttu-id="54a0c-128">Muestra cómo recuperar los parámetros de la dirección URL usada para ejecutar una aplicación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="54a0c-128">Demonstrates retrieving parameters from the URL used to run a ClickOnce application.</span></span>  
  
 [<span data-ttu-id="54a0c-129">Información general sobre la memoria caché de ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-129">ClickOnce Cache Overview</span></span>](/visualstudio/deployment/clickonce-cache-overview)  
 <span data-ttu-id="54a0c-130">Describe la memoria caché que se usa para almacenar las aplicaciones ClickOnce en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="54a0c-130">Describes the cache used to store ClickOnce applications on the local computer.</span></span>  
  
 [<span data-ttu-id="54a0c-131">Obtener acceso local o remoto a los datos en aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-131">Accessing Local and Remote Data in ClickOnce Applications</span></span>](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)  
 <span data-ttu-id="54a0c-132">Describe cómo obtener acceso a los archivos de datos locales y los orígenes de datos remotos desde una aplicación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="54a0c-132">Describes how to access local data files and remote data sources from a ClickOnce application.</span></span>  
  
 [<span data-ttu-id="54a0c-133">How to: Include a Data File in a ClickOnce Application</span><span class="sxs-lookup"><span data-stu-id="54a0c-133">How to: Include a Data File in a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application)  
 <span data-ttu-id="54a0c-134">Muestra cómo marcar un archivo para que esté disponible en el directorio de datos de ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="54a0c-134">Demonstrates how to mark a file so that it is available in the ClickOnce data directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a0c-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54a0c-135">See also</span></span>

- [<span data-ttu-id="54a0c-136">Introducción a la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="54a0c-136">Application Settings Overview</span></span>](./advanced/application-settings-overview.md)
- [<span data-ttu-id="54a0c-137">Publicar aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-137">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)
- [<span data-ttu-id="54a0c-138">Compilar aplicaciones ClickOnce desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="54a0c-138">Building ClickOnce Applications from the Command Line</span></span>](/visualstudio/deployment/building-clickonce-applications-from-the-command-line)
- [<span data-ttu-id="54a0c-139">Depurar aplicaciones ClickOnce que usan System.Deployment.Application</span><span class="sxs-lookup"><span data-stu-id="54a0c-139">Debugging ClickOnce Applications That Use System.Deployment.Application</span></span>](/visualstudio/deployment/debugging-clickonce-applications-that-use-system-deployment-application)
- [<span data-ttu-id="54a0c-140">Implementar componentes COM con ClickOnce</span><span class="sxs-lookup"><span data-stu-id="54a0c-140">Deploying COM Components with ClickOnce</span></span>](/visualstudio/deployment/deploying-com-components-with-clickonce)
- [<span data-ttu-id="54a0c-141">Cómo: Publicar una aplicación ClickOnce mediante el Asistente para publicación</span><span class="sxs-lookup"><span data-stu-id="54a0c-141">How to: Publish a ClickOnce Application using the Publish Wizard</span></span>](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)
