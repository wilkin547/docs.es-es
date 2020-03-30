---
title: Uso del paquete de compatibilidad de Windows para trasladar código a .NET Core
description: Obtenga información sobre el paquete de compatibilidad de Windows y cómo puede usarlo para migrar código existente de .NET Framework a .NET Core.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 166259ca37a2005d67f6c545e4843a940f05fb71
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228635"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a><span data-ttu-id="d9b44-103">Uso del paquete de compatibilidad de Windows para trasladar código a .NET Core</span><span class="sxs-lookup"><span data-stu-id="d9b44-103">Use the Windows Compatibility Pack to port code to .NET Core</span></span>

<span data-ttu-id="d9b44-104">Algunos de los problemas más comunes que se encuentran al trasladar código existente a .NET Core son las dependencias con API y las tecnologías que solo se encuentran en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d9b44-104">Some of the most common issues found when porting existing code to .NET Core are dependencies on APIs and technologies that are only found in .NET Framework.</span></span> <span data-ttu-id="d9b44-105">El *paquete de compatibilidad de Windows* proporciona muchas de estas tecnologías, por lo que es mucho más fácil crear aplicaciones de .NET Core y bibliotecas de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d9b44-105">The *Windows Compatibility Pack* provides many of these technologies, so it's much easier to build .NET Core applications and .NET Standard libraries.</span></span>

<span data-ttu-id="d9b44-106">El paquete de compatibilidad es una [extensión lógica de .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) que aumenta considerablemente el conjunto de API.</span><span class="sxs-lookup"><span data-stu-id="d9b44-106">The compatibility pack is a logical [extension of .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) that significantly increases the API set.</span></span> <span data-ttu-id="d9b44-107">El código existente se compila prácticamente sin modificaciones.</span><span class="sxs-lookup"><span data-stu-id="d9b44-107">Existing code compiles with almost no modifications.</span></span> <span data-ttu-id="d9b44-108">Para mantener su promesa de "el conjunto de API que proporcionan todas las implementaciones de .NET", .NET Standard no incluye tecnologías que no puedan funcionar en todas las plataformas, como el Registro, Instrumental de administración de Windows (WMI) o las API de emisión de la reflexión.</span><span class="sxs-lookup"><span data-stu-id="d9b44-108">To keep its promise of "the set of APIs that all .NET implementations provide", .NET Standard doesn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span> <span data-ttu-id="d9b44-109">El paquete de compatibilidad de Windows está un nivel por encima de .NET Standard y proporciona acceso a estas tecnologías que solo son de Windows.</span><span class="sxs-lookup"><span data-stu-id="d9b44-109">The Windows Compatibility Pack sits on top of .NET Standard and provides access to these Windows-only technologies.</span></span> <span data-ttu-id="d9b44-110">Es especialmente útil para los clientes que quieren migrar a .NET Core pero piensan permanecer en Windows, al menos como primer paso.</span><span class="sxs-lookup"><span data-stu-id="d9b44-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows, at least as a first step.</span></span> <span data-ttu-id="d9b44-111">En ese escenario, la posibilidad de usar tecnologías solo de Windows elimina el obstáculo de la migración.</span><span class="sxs-lookup"><span data-stu-id="d9b44-111">In that scenario, being able to use Windows-only technologies removes the migration hurdle.</span></span>

## <a name="package-contents"></a><span data-ttu-id="d9b44-112">Contenido del paquete</span><span class="sxs-lookup"><span data-stu-id="d9b44-112">Package contents</span></span>

<span data-ttu-id="d9b44-113">El paquete de compatibilidad de Windows se proporciona mediante el [paquete NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) y se puede hacer referencia a él desde proyectos para .NET Core o .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d9b44-113">The Windows Compatibility Pack is provided via the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects that target .NET Core or .NET Standard.</span></span>

<span data-ttu-id="d9b44-114">Proporciona unas 20.000 API, incluidas API solo de Windows y API de varias plataformas de las siguientes áreas tecnológicas:</span><span class="sxs-lookup"><span data-stu-id="d9b44-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

- <span data-ttu-id="d9b44-115">Páginas de códigos</span><span class="sxs-lookup"><span data-stu-id="d9b44-115">Code Pages</span></span>
- <span data-ttu-id="d9b44-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="d9b44-116">CodeDom</span></span>
- <span data-ttu-id="d9b44-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="d9b44-117">Configuration</span></span>
- <span data-ttu-id="d9b44-118">Servicios de directorio</span><span class="sxs-lookup"><span data-stu-id="d9b44-118">Directory Services</span></span>
- <span data-ttu-id="d9b44-119">Dibujo</span><span class="sxs-lookup"><span data-stu-id="d9b44-119">Drawing</span></span>
- <span data-ttu-id="d9b44-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="d9b44-120">ODBC</span></span>
- <span data-ttu-id="d9b44-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="d9b44-121">Permissions</span></span>
- <span data-ttu-id="d9b44-122">Puertos</span><span class="sxs-lookup"><span data-stu-id="d9b44-122">Ports</span></span>
- <span data-ttu-id="d9b44-123">Listas de control de acceso (ACL) de Windows</span><span class="sxs-lookup"><span data-stu-id="d9b44-123">Windows Access Control Lists (ACL)</span></span>
- <span data-ttu-id="d9b44-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="d9b44-124">Windows Communication Foundation (WCF)</span></span>
- <span data-ttu-id="d9b44-125">Criptografía de Windows</span><span class="sxs-lookup"><span data-stu-id="d9b44-125">Windows Cryptography</span></span>
- <span data-ttu-id="d9b44-126">Registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="d9b44-126">Windows EventLog</span></span>
- <span data-ttu-id="d9b44-127">Instrumental de administración de Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="d9b44-127">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="d9b44-128">Contadores de rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="d9b44-128">Windows Performance Counters</span></span>
- <span data-ttu-id="d9b44-129">Registro de Windows</span><span class="sxs-lookup"><span data-stu-id="d9b44-129">Windows Registry</span></span>
- <span data-ttu-id="d9b44-130">Memoria caché de tiempo de ejecución de Windows</span><span class="sxs-lookup"><span data-stu-id="d9b44-130">Windows Runtime Caching</span></span>
- <span data-ttu-id="d9b44-131">servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="d9b44-131">Windows Services</span></span>

<span data-ttu-id="d9b44-132">Para más información, vea las [especificaciones del paquete de compatibilidad](https://github.com/dotnet/designs/blob/master/accepted/2018/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d9b44-132">For more information, see the [specification of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/2018/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="d9b44-133">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="d9b44-133">Get started</span></span>

1. <span data-ttu-id="d9b44-134">Antes de migrar, asegúrese de echar un vistazo al [proceso de migración](index.md).</span><span class="sxs-lookup"><span data-stu-id="d9b44-134">Before porting, make sure to take a look at the [Porting process](index.md).</span></span>

2. <span data-ttu-id="d9b44-135">Al migrar código existente a .NET Core o .NET Standard, instale el [paquete NuGet Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="d9b44-135">When porting existing code to .NET Core or .NET Standard, install the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

   <span data-ttu-id="d9b44-136">Si quiere permanecer en Windows, ya está listo.</span><span class="sxs-lookup"><span data-stu-id="d9b44-136">If you want to stay on Windows, you're all set.</span></span>

3. <span data-ttu-id="d9b44-137">Si quiere ejecutar la aplicación .NET Core o la biblioteca de .NET Standard en Linux o macOS, use el [analizador de API](../../standard/analyzers/api-analyzer.md) para informarse de qué API no funcionan en varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="d9b44-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](../../standard/analyzers/api-analyzer.md) to find usage of APIs that won't work cross-platform.</span></span>

4. <span data-ttu-id="d9b44-138">Quite esas API, reemplácelas con alternativas multiplataforma o restrínjalas con una comprobación de plataforma, como:</span><span class="sxs-lookup"><span data-stu-id="d9b44-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="d9b44-139">Para ver una demostración, vaya al [vídeo de Channel 9 sobre el paquete de compatibilidad de Windows](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="d9b44-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>
