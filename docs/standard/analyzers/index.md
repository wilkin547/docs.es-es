---
title: Los analizadores basados en Roslyn - .NET
description: "Obtenga información sobre los analizadores basados en Roslyn que detectan problemas y sugieren soluciones para esos problemas."
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/24/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 8c6524716ba403bc426df8dc33e64b8b2934d3d7
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="the-roslyn-based-analyzers"></a><span data-ttu-id="5fd7a-104">Los analizadores basados en Roslyn</span><span class="sxs-lookup"><span data-stu-id="5fd7a-104">The Roslyn based Analyzers</span></span>

<span data-ttu-id="5fd7a-105">Los analizadores basados en Roslyn usan el SDK de .NET Compiler (API de Roslyn) para analizar el código fuente de su proyecto a fin de detectar problemas y sugerir soluciones.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-105">Roslyn-based analyzers use the .NET Compiler SDK (Roslyn APIs) to analyze your project's source code to find issues and suggest corrections.</span></span> <span data-ttu-id="5fd7a-106">Los diferentes analizadores buscan distintas clases de problemas, que van desde prácticas susceptibles de generar errores a inquietudes de seguridad relativas a la compatibilidad de la API.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-106">Different analyzers look for different classes of issues, ranging from practices that are likely to cause bugs to security concerns to API compatibility.</span></span>

<span data-ttu-id="5fd7a-107">Los analizadores basados en Roslyn trabajan de forma interactiva y durante las compilaciones.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-107">Roslyn-based analyzers work both interactively and during builds.</span></span> <span data-ttu-id="5fd7a-108">El analizador proporciona diversas instrucciones tanto en Visual Studio como en las compilaciones de líneas de comandos.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-108">The analyzer provides different guidance when in Visual Studio or in command-line builds.</span></span>

<span data-ttu-id="5fd7a-109">Mientras edita código en Visual Studio, los analizadores se ejecutan al realizar cambios, detectando posibles problemas tan pronto como cree código que desencadene preocupaciones.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-109">While you edit code in Visual Studio, the analyzers run as you make changes, catching possible issues as soon as you create code that trigger concerns.</span></span> <span data-ttu-id="5fd7a-110">Algunos problemas se resaltan con subrayados ondulados.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-110">Any issues are highlighted with squiggles under any issue.</span></span> <span data-ttu-id="5fd7a-111">Visual Studio muestra una bombilla y, al hacer clic en ella, el analizador sugerirá posibles soluciones a ese problema.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-111">Visual Studio displays a light bulb, and when you click on it the analyzer will suggest possible fixes for that issue.</span></span> <span data-ttu-id="5fd7a-112">Al crear el proyecto, ya sea en Visual Studio o desde la línea de comandos, se analiza todo el código fuente y el analizador proporciona una lista completa de posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-112">When you build the project, either in Visual Studio or from the command line, all the source code is analyzed and the analyzer provides a full list of potential issues.</span></span> <span data-ttu-id="5fd7a-113">En la siguiente ilustración se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-113">The following figure shows one example.</span></span>

![problemas notificados por el analizador de marco](./media/framework-analyzers-2.png)

<span data-ttu-id="5fd7a-115">Los analizadores basados en Roslyn notifican posibles problemas como errores, advertencias o información en función de la gravedad del problema.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-115">Roslyn-based analyzers report potential issues as errors, warnings, or information based on the severity of the issue.</span></span>

<span data-ttu-id="5fd7a-116">Puede instalar los analizadores basados en Roslyn como paquetes NuGet en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-116">You install Roslyn-based analyzers as NuGet packages in your project.</span></span> <span data-ttu-id="5fd7a-117">Los analizadores configurados y la configuración de cada uno de ellos se restauran y se ejecutan en la máquina de ese proyecto de los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-117">The configured analyzers and any settings for each analyzer are restored and run on any developer's machine for that project.</span></span>

> [!NOTE]
> <span data-ttu-id="5fd7a-118">La experiencia de usuario en el caso de los analizadores basados en Roslyn es distinta de la de bibliotecas de análisis de código como las versiones anteriores de FxCop y las herramientas de análisis de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-118">The user experience for Roslyn-based analyzers is different than that of the Code Analysis libraries like the older versions of FxCop and the security analysis tools.</span></span>  <span data-ttu-id="5fd7a-119">No es necesario que ejecute de forma explícita los analizadores basados en Roslyn.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-119">You don't need to explicitly run the Roslyn-based analyzers.</span></span> <span data-ttu-id="5fd7a-120">Tampoco hace falta usar los elementos de menú "Ejecutar análisis de código" en el menú "Analizar" de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-120">There's no need to use the "Run Code Analysis" menu items on the "Analyze" menu in Visual Studio.</span></span> <span data-ttu-id="5fd7a-121">Los analizadores basados en Roslyn se ejecutan de forma asincrónica mientras trabaja.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-121">Roslyn-based analyzers run asychronously as you work.</span></span> 

## <a name="more-information-on-specific-analyzers"></a><span data-ttu-id="5fd7a-122">Más información sobre analizadores específicos</span><span class="sxs-lookup"><span data-stu-id="5fd7a-122">More information on specific analyzers</span></span>

<span data-ttu-id="5fd7a-123">Los siguientes analizadores se tratan en esta sección:</span><span class="sxs-lookup"><span data-stu-id="5fd7a-123">The following analyzers are covered in this section:</span></span>

<span data-ttu-id="5fd7a-124">[Analizador de API](api-analyzer.md): este analizador examina su código en busca de posibles riesgos de compatibilidad o usos de API en desuso.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-124">[API Analyzer](api-analyzer.md): This analyzer examines your code for potential compatibility risks or uses of deprecated APIs.</span></span>    
<span data-ttu-id="5fd7a-125">[Analizador de marco](framework-analyzer.md): este analizador examina su código para garantizar que siga las instrucciones de las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-125">[Framework Analyzer](framework-analyzer.md): This analyzer examines your code to ensure it follows the guidelines for .NET Framework applications.</span></span> <span data-ttu-id="5fd7a-126">Estas reglas incluyen varias recomendaciones basadas en seguridad.</span><span class="sxs-lookup"><span data-stu-id="5fd7a-126">These rules include several security-based recommendations.</span></span>
