---
title: "Migración a .NET Core: Uso del paquete de compatibilidad de Windows"
description: "Obtenga información sobre el paquete de compatibilidad de Windows y cómo puede usarlo para migrar código existente de .NET Framework a .NET Core"
keywords: .NET, .NET Core, Windows, Compatibilidad
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 3b1fe02aad4f78499158ecb7fa9b8521cb7d992e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="4b2bc-104">Uso del paquete de compatibilidad de Windows</span><span class="sxs-lookup"><span data-stu-id="4b2bc-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="4b2bc-105">Uno de los problemas más comunes al que se enfrentan los desarrolladores al migrar el código existente a .NET Core es que dependen de API y tecnologías que solo existen en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="4b2bc-106">El *paquete de compatibilidad de Windows* proporciona muchas de estas tecnologías para que compilar aplicaciones .NET Core y bibliotecas de .NET Standard sea mucho más viable para el código existente.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="4b2bc-107">Este paquete es una [extensión lógica de .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) que aumenta considerablemente las compilaciones del conjunto de API y el código existente prácticamente sin modificaciones.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="4b2bc-108">Pero con el fin de mantener la promesa de .NET Standard ("es el conjunto de API que proporcionan todas las implementaciones de .NET"), no incluye tecnologías que no puedan funcionar en todas las plataformas, como el Registro, Windows Management Instrumentation (WMI) o las API de emisión de la reflexión.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="4b2bc-109">El *paquete de compatibilidad de Windows* está un nivel por encima de .NET Standard y proporciona acceso a tecnologías que solo son de Windows.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="4b2bc-110">Es especialmente útil para los clientes que quieren migrar a .NET Core pero piensan permanecer en Windows como primer paso.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="4b2bc-111">En ese escenario, la imposibilidad de usar tecnologías solo de Windows es únicamente un escollo para la migración con cero ventajas arquitectónicas.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="4b2bc-112">Contenido del paquete</span><span class="sxs-lookup"><span data-stu-id="4b2bc-112">Package contents</span></span>

<span data-ttu-id="4b2bc-113">El *paquete de compatibilidad de Windows* se proporciona mediante el paquete NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) y se puede hacer referencia a él desde proyectos para .NET Core o .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="4b2bc-114">Proporciona unas 20.000 API, incluidas API solo de Windows y API de varias plataformas de las siguientes áreas tecnológicas:</span><span class="sxs-lookup"><span data-stu-id="4b2bc-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="4b2bc-115">Páginas de códigos</span><span class="sxs-lookup"><span data-stu-id="4b2bc-115">Code Pages</span></span>
* <span data-ttu-id="4b2bc-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="4b2bc-116">CodeDom</span></span>
* <span data-ttu-id="4b2bc-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="4b2bc-117">Configuration</span></span>
* <span data-ttu-id="4b2bc-118">Servicios de directorio</span><span class="sxs-lookup"><span data-stu-id="4b2bc-118">Directory Services</span></span>
* <span data-ttu-id="4b2bc-119">Dibujo</span><span class="sxs-lookup"><span data-stu-id="4b2bc-119">Drawing</span></span>
* <span data-ttu-id="4b2bc-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="4b2bc-120">ODBC</span></span>
* <span data-ttu-id="4b2bc-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="4b2bc-121">Permissions</span></span>
* <span data-ttu-id="4b2bc-122">Puertos</span><span class="sxs-lookup"><span data-stu-id="4b2bc-122">Ports</span></span>
* <span data-ttu-id="4b2bc-123">Listas de control de acceso (ACL) de Windows</span><span class="sxs-lookup"><span data-stu-id="4b2bc-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="4b2bc-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="4b2bc-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="4b2bc-125">Criptografía de Windows</span><span class="sxs-lookup"><span data-stu-id="4b2bc-125">Windows Cryptography</span></span>
* <span data-ttu-id="4b2bc-126">Registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="4b2bc-126">Windows EventLog</span></span>
* <span data-ttu-id="4b2bc-127">Instrumental de administración de Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="4b2bc-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="4b2bc-128">Contadores de rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="4b2bc-128">Windows Performance Counters</span></span>
* <span data-ttu-id="4b2bc-129">Registro de Windows</span><span class="sxs-lookup"><span data-stu-id="4b2bc-129">Windows Registry</span></span>
* <span data-ttu-id="4b2bc-130">Memoria caché de tiempo de ejecución de Windows</span><span class="sxs-lookup"><span data-stu-id="4b2bc-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="4b2bc-131">servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="4b2bc-131">Windows Services</span></span>

<span data-ttu-id="4b2bc-132">Para más información, vea las [especificaciones del paquete de compatibilidad](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4b2bc-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="4b2bc-133">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="4b2bc-133">Get started</span></span>

1. <span data-ttu-id="4b2bc-134">Antes de migrar, asegúrese de echar un vistazo al [proceso de migración](index.md).</span><span class="sxs-lookup"><span data-stu-id="4b2bc-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="4b2bc-135">Al migrar código existente a .NET Core o .NET Standard, instale el paquete NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="4b2bc-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="4b2bc-136">Si quiere permanecer en Windows, ya está listo.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="4b2bc-137">Si quiere ejecutar la aplicación .NET Core o la biblioteca de .NET Standard en Linux o macOS, use el [analizador de API](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) para informarse de qué API no funcionan en varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="4b2bc-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="4b2bc-138">Quite esas API, reemplácelas con alternativas multiplataforma o restrínjalas con una comprobación de plataforma, como:</span><span class="sxs-lookup"><span data-stu-id="4b2bc-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="4b2bc-139">Para ver una demostración, vaya al [vídeo de Channel 9 sobre el paquete de compatibilidad de Windows](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="4b2bc-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

