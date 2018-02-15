---
title: "Cómo implementar aplicaciones de .NET existentes al servicio de aplicaciones de Azure"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cómo implementar aplicaciones de .NET existentes al servicio de aplicaciones de Azure"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 84bffe7aad6bbffb40519c9146d8156159d55850
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a><span data-ttu-id="21708-103">Cómo implementar aplicaciones de .NET existentes al servicio de aplicaciones de Azure</span><span class="sxs-lookup"><span data-stu-id="21708-103">How to deploy existing .NET apps to Azure App Service</span></span> 

<span data-ttu-id="21708-104">La característica de las aplicaciones Web de servicio de aplicaciones de Azure es una plataforma de proceso totalmente administrado que está optimizada para hospedar aplicaciones web y sitios Web.</span><span class="sxs-lookup"><span data-stu-id="21708-104">The Web Apps feature of Azure App Service is a fully managed compute platform that is optimized for hosting websites and web apps.</span></span> <span data-ttu-id="21708-105">Esta oferta de PaaS en Microsoft Azure permite centrarse en la lógica de negocios, mientras Azure se encarga de la infraestructura para ejecutar y escalar sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="21708-105">This PaaS offering in Microsoft Azure lets you focus on your business logic, while Azure takes care of the infrastructure to run and scale your apps.</span></span>

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a><span data-ttu-id="21708-106">Validar sitios y migrar al servicio de aplicación con el Asistente de migración de Azure aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="21708-106">Validate sites and migrate to App Service with Azure App Service Migration Assistant</span></span>

<span data-ttu-id="21708-107">Cuando se crea una nueva aplicación en Visual Studio, mover la aplicación al servicio de aplicaciones normalmente es sencillo.</span><span class="sxs-lookup"><span data-stu-id="21708-107">When you create a new application in Visual Studio, moving the app to App Service usually is straightforward.</span></span> <span data-ttu-id="21708-108">Sin embargo, si va a migrar una aplicación existente al servicio de aplicaciones, primero debe evaluar si todas las dependencias de su aplicación son compatibles con el servicio de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="21708-108">However, if you are planning to migrate an existing application to App Service, first you need to evaluate whether all your application's dependencies are compatible with App Service.</span></span> <span data-ttu-id="21708-109">Esto incluye las dependencias como sistema operativo del servidor y cualquier software de terceros que está instalado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="21708-109">This includes dependencies like server OS and any third-party software that's installed on the server.</span></span>

<span data-ttu-id="21708-110">Puede usar [Azure aplicación servicio Migration Assistant](https://www.migratetoazure.net/) para analizar sitios y, a continuación, migrarlos al servicio de aplicaciones de servidores web de Windows y Linux.</span><span class="sxs-lookup"><span data-stu-id="21708-110">You can use [Azure App Service Migration Assistant](https://www.migratetoazure.net/) to analyze sites and then migrate them from Windows and Linux web servers to App Service.</span></span> <span data-ttu-id="21708-111">Como parte de la migración, la herramienta crea aplicaciones web y bases de datos de Azure según sea necesario, publica contenido y publica la base de datos.</span><span class="sxs-lookup"><span data-stu-id="21708-111">As part of the migration, the tool creates web apps and databases on Azure as needed, publishes content, and publishes your database.</span></span>

<span data-ttu-id="21708-112">Azure aplicación servicio Migration Assistant admite la migración de IIS que se ejecuta en Windows Server a la nube.</span><span class="sxs-lookup"><span data-stu-id="21708-112">Azure App Service Migration Assistant supports migrating from IIS running on Windows Server to the cloud.</span></span> <span data-ttu-id="21708-113">Servicio de aplicaciones es compatible con Windows Server 2003 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="21708-113">App Service supports Windows Server 2003 and later versions.</span></span>

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> <span data-ttu-id="21708-115">**Figura 4-5.**</span><span class="sxs-lookup"><span data-stu-id="21708-115">**Figure 4-5.**</span></span> <span data-ttu-id="21708-116">Usar el Asistente de migración de servicio de aplicaciones de Azure</span><span class="sxs-lookup"><span data-stu-id="21708-116">Using Azure App Service Migration Assistant</span></span>

<span data-ttu-id="21708-117">Asistente para la migración del servicio de aplicación es una herramienta que mueve los sitios Web de los servidores web a la nube de Azure.</span><span class="sxs-lookup"><span data-stu-id="21708-117">App Service Migration Assistant is a tool that moves your websites from your web servers to the Azure cloud.</span></span>

<span data-ttu-id="21708-118">Después de migra un sitio Web al servicio de aplicaciones, el sitio tiene todo que lo necesario para ejecutar de forma segura y eficaz.</span><span class="sxs-lookup"><span data-stu-id="21708-118">After a website is migrated to App Service, the site has everything it needs to run safely and efficiently.</span></span> <span data-ttu-id="21708-119">Los sitios se configuran y ejecutan automáticamente en el servicio de PaaS de nube de Azure (servicio de aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="21708-119">Sites are set up and run automatically in the Azure cloud PaaS service (App Service).</span></span>

<span data-ttu-id="21708-120">La herramienta de migración de servicio de aplicaciones puede analizar los sitios Web e informar sobre su compatibilidad para mover a un servicio de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="21708-120">The App Service migration tool can analyze your websites and report on their compatibility for moving to App Service.</span></span> <span data-ttu-id="21708-121">Si está satisfecho con el análisis, puede dejar que el Asistente para la migración de servicio aplicación migrar contenido, datos y configuración.</span><span class="sxs-lookup"><span data-stu-id="21708-121">If you're happy with the analysis, you can let App Service Migration Assistant migrate content, data, and settings for you.</span></span> <span data-ttu-id="21708-122">Si un sitio no es bastante compatible, la herramienta de migración indica lo que necesita ajustar para que funcione.</span><span class="sxs-lookup"><span data-stu-id="21708-122">If a site is not quite compatible, the migration tool tells you what you need to adjust to make it work.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="21708-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="21708-123">Additional resources</span></span>

-   <span data-ttu-id="21708-124">**Asistente de migración de servicio de aplicaciones de Azure**</span><span class="sxs-lookup"><span data-stu-id="21708-124">**Azure App Service Migration Assistant**</span></span>

    [<span data-ttu-id="21708-125">https://www.migratetoazure.net/</span><span class="sxs-lookup"><span data-stu-id="21708-125">https://www.migratetoazure.net/</span></span>](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
<span data-ttu-id="21708-126">[Anterior](what-about-cloud-optimized-applications.md)
[Siguiente](deploy-existing-net-apps-as-windows-containers.md)</span><span class="sxs-lookup"><span data-stu-id="21708-126">[Previous](what-about-cloud-optimized-applications.md)
[Next](deploy-existing-net-apps-as-windows-containers.md)</span></span>
