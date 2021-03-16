---
title: Implementación de un proveedor de registro personalizado en .NET
description: Obtenga información sobre cómo implementar un proveedor de registro personalizado en las aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/25/2020
ms.topic: how-to
ms.openlocfilehash: 3a0af6296c2ade15ff1b75dce5a5f99bfe235ebf
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "102402072"
---
# <a name="implement-a-custom-logging-provider-in-net"></a><span data-ttu-id="50a0b-103">Implementación de un proveedor de registro personalizado en .NET</span><span class="sxs-lookup"><span data-stu-id="50a0b-103">Implement a custom logging provider in .NET</span></span>

<span data-ttu-id="50a0b-104">Hay muchos [proveedores de registro](logging-providers.md) disponibles para las necesidades de registro habituales.</span><span class="sxs-lookup"><span data-stu-id="50a0b-104">There are many [logging providers](logging-providers.md) available for common logging needs.</span></span> <span data-ttu-id="50a0b-105">Puede que tenga que implementar un <xref:Microsoft.Extensions.Logging.ILoggerProvider> personalizado cuando uno de los proveedores disponibles no se ajuste a las necesidades de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="50a0b-105">You may need to implement a custom <xref:Microsoft.Extensions.Logging.ILoggerProvider> when one of the available providers doesn't suit your application needs.</span></span> <span data-ttu-id="50a0b-106">En este artículo, aprenderá a implementar un proveedor de registro personalizado que se puede usar para colorear los registros en la consola.</span><span class="sxs-lookup"><span data-stu-id="50a0b-106">In this article, you'll learn how to implement a custom logging provider that can be used to colorize logs in the console.</span></span>

### <a name="sample-custom-logger-configuration"></a><span data-ttu-id="50a0b-107">Configuración de registrador personalizado de ejemplo</span><span class="sxs-lookup"><span data-stu-id="50a0b-107">Sample custom logger configuration</span></span>

<span data-ttu-id="50a0b-108">En el ejemplo se crean diferentes entradas de consola de color por nivel de registro e identificador de evento con el siguiente tipo de configuración:</span><span class="sxs-lookup"><span data-stu-id="50a0b-108">The sample creates different color console entries per log level and event ID using the following configuration type:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerConfiguration.cs":::

<span data-ttu-id="50a0b-109">El código anterior establece el nivel predeterminado en `Information`, el color en `Green` y el `EventId` en `0` de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="50a0b-109">The preceding code sets the default level to `Information`, the color to `Green`, and the `EventId` is implicitly `0`.</span></span>

### <a name="create-the-custom-logger"></a><span data-ttu-id="50a0b-110">Creación del registrador personalizado</span><span class="sxs-lookup"><span data-stu-id="50a0b-110">Create the custom logger</span></span>

<span data-ttu-id="50a0b-111">El nombre de la categoría de implementación `ILogger` es normalmente el origen del registro.</span><span class="sxs-lookup"><span data-stu-id="50a0b-111">The `ILogger` implementation category name is typically the logging source.</span></span> <span data-ttu-id="50a0b-112">Por ejemplo, el tipo en el que se crea el registrador:</span><span class="sxs-lookup"><span data-stu-id="50a0b-112">For example, the type where the logger is created:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs":::

<span data-ttu-id="50a0b-113">El código anterior:</span><span class="sxs-lookup"><span data-stu-id="50a0b-113">The preceding code:</span></span>

- <span data-ttu-id="50a0b-114">Crea una instancia del registrador por nombre de categoría.</span><span class="sxs-lookup"><span data-stu-id="50a0b-114">Creates a logger instance per category name.</span></span>
- <span data-ttu-id="50a0b-115">Comprueba `logLevel == _config.LogLevel` en `IsEnabled`, por lo que cada `logLevel` tiene un registrador único.</span><span class="sxs-lookup"><span data-stu-id="50a0b-115">Checks `logLevel == _config.LogLevel` in `IsEnabled`, so each `logLevel` has a unique logger.</span></span> <span data-ttu-id="50a0b-116">Los registradores también se deben habilitar para todos los niveles de registro superiores:</span><span class="sxs-lookup"><span data-stu-id="50a0b-116">Loggers should also be enabled for all higher log levels:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLogger.cs" range="16-17":::

## <a name="custom-logger-provider"></a><span data-ttu-id="50a0b-117">Proveedor de registrador personalizado</span><span class="sxs-lookup"><span data-stu-id="50a0b-117">Custom logger provider</span></span>

<span data-ttu-id="50a0b-118">El objeto `ILoggerProvider` es responsable de crear las instancias de registrador.</span><span class="sxs-lookup"><span data-stu-id="50a0b-118">The `ILoggerProvider` object is responsible for creating logger instances.</span></span> <span data-ttu-id="50a0b-119">Tal vez no sea necesario crear una instancia del registrador por categoría, pero esto tiene sentido para algunos registradores, como NLog o log4net.</span><span class="sxs-lookup"><span data-stu-id="50a0b-119">Maybe it is not needed to create a logger instance per category, but this makes sense for some loggers, like NLog or log4net.</span></span> <span data-ttu-id="50a0b-120">Al hacerlo, también se podrán elegir diferentes destinos de salida de registro por categoría, en caso necesario:</span><span class="sxs-lookup"><span data-stu-id="50a0b-120">Doing this you are also able to choose different logging output targets per category if needed:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/ColorConsoleLoggerProvider.cs":::

<span data-ttu-id="50a0b-121">En el código anterior, <xref:Microsoft.Build.Logging.LoggerDescription.CreateLogger%2A> crea una única instancia de `ColorConsoleLogger` por nombre de categoría y la almacena en [`ConcurrentDictionary<TKey,TValue>`](/dotnet/api/system.collections.concurrent.concurrentdictionary-2).</span><span class="sxs-lookup"><span data-stu-id="50a0b-121">In the preceding code, <xref:Microsoft.Build.Logging.LoggerDescription.CreateLogger%2A> creates a single instance of the `ColorConsoleLogger` per category name and stores it in the [`ConcurrentDictionary<TKey,TValue>`](/dotnet/api/system.collections.concurrent.concurrentdictionary-2).</span></span>

## <a name="usage-and-registration-of-the-custom-logger"></a><span data-ttu-id="50a0b-122">Uso y registro del registrador personalizado</span><span class="sxs-lookup"><span data-stu-id="50a0b-122">Usage and registration of the custom logger</span></span>

<span data-ttu-id="50a0b-123">Para agregar el proveedor de registro personalizado y el registrador correspondiente, agregue un <xref:Microsoft.Extensions.Logging.ILoggerProvider> con <xref:Microsoft.Extensions.Logging.ILoggingBuilder> desde <xref:Microsoft.Extensions.Hosting.HostingHostBuilderExtensions.ConfigureLogging(Microsoft.Extensions.Hosting.IHostBuilder,System.Action{Microsoft.Extensions.Logging.ILoggingBuilder})?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="50a0b-123">To add the custom logging provider and corresponding logger, add an <xref:Microsoft.Extensions.Logging.ILoggerProvider> with <xref:Microsoft.Extensions.Logging.ILoggingBuilder> from the <xref:Microsoft.Extensions.Hosting.HostingHostBuilderExtensions.ConfigureLogging(Microsoft.Extensions.Hosting.IHostBuilder,System.Action{Microsoft.Extensions.Logging.ILoggingBuilder})?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/Program.cs" range="23-39":::

<span data-ttu-id="50a0b-124">`ILoggingBuilder` crea una o más instancias de `ILogger`.</span><span class="sxs-lookup"><span data-stu-id="50a0b-124">The `ILoggingBuilder` creates one or more `ILogger` instances.</span></span> <span data-ttu-id="50a0b-125">El marco de trabajo usa las instancias de `ILogger` para registrar la información.</span><span class="sxs-lookup"><span data-stu-id="50a0b-125">The `ILogger` instances are used by the framework to log the information.</span></span>

<span data-ttu-id="50a0b-126">Para el código anterior, proporcione al menos un método de extensión para `ILoggerFactory`:</span><span class="sxs-lookup"><span data-stu-id="50a0b-126">For the preceding code, provide at least one extension method for the `ILoggerFactory`:</span></span>

:::code language="csharp" source="snippets/configuration/console-custom-logging/Extensions/ColorConsoleLoggerExtensions.cs":::

<span data-ttu-id="50a0b-127">La ejecución de esta aplicación simple se representará de forma similar a la siguiente ventana de la consola:</span><span class="sxs-lookup"><span data-stu-id="50a0b-127">Running this simple application will render similar to the following console window:</span></span>

:::image type="content" source="media/color-console-logger.png" alt-text="Salida de ejemplo del registrador de la consola de color":::

## <a name="see-also"></a><span data-ttu-id="50a0b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="50a0b-129">See also</span></span>

- <span data-ttu-id="50a0b-130">[Registro en .NET](logging.md).</span><span class="sxs-lookup"><span data-stu-id="50a0b-130">[Logging in .NET](logging.md).</span></span>
- <span data-ttu-id="50a0b-131">[Proveedores de registro en .NET](logging-providers.md).</span><span class="sxs-lookup"><span data-stu-id="50a0b-131">[Logging providers in .NET](logging-providers.md).</span></span>
- <span data-ttu-id="50a0b-132">[Registro de alto rendimiento en .NET](high-performance-logging.md).</span><span class="sxs-lookup"><span data-stu-id="50a0b-132">[High-performance logging in .NET](high-performance-logging.md).</span></span>
