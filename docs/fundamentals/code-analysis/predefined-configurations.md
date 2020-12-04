---
title: Archivos de configuración predefinidos (análisis de código)
description: Obtenga información sobre el uso de editorconfig y los archivos de conjunto de reglas predefinidos para tener como destino tipos específicos de análisis de código.
ms.date: 09/24/2020
ms.topic: conceptual
ms.openlocfilehash: 4937dcab1183fa3f63be4afc71627a7c7c08c6bd
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "96594372"
---
# <a name="predefined-configuration-files"></a><span data-ttu-id="e58d4-103">Archivos de configuración predefinidos</span><span class="sxs-lookup"><span data-stu-id="e58d4-103">Predefined configuration files</span></span>

<span data-ttu-id="e58d4-104">Los archivos de [conjunto de reglas](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) y EditorConfig predefinidos están disponibles para facilitar y agilizar la habilitación de una categoría de reglas de calidad de código, como reglas de seguridad o de diseño.</span><span class="sxs-lookup"><span data-stu-id="e58d4-104">Predefined EditorConfig and [rule set](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) files are available that make it quick and easy to enable a category of code quality rules, such as security or design rules.</span></span> <span data-ttu-id="e58d4-105">Al habilitar una categoría específica de reglas, puede identificar problemas de destino y condiciones específicas.</span><span class="sxs-lookup"><span data-stu-id="e58d4-105">By enabling a specific category of rules, you can identify targeted issues and specific conditions.</span></span> <span data-ttu-id="e58d4-106">Para tener acceso a estos archivos predefinidos, instale el paquete del analizador de NuGet [Microsoft. CodeAnalysis. NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) .</span><span class="sxs-lookup"><span data-stu-id="e58d4-106">To access these predefined files, install the [Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) NuGet analyzer package.</span></span>

<span data-ttu-id="e58d4-107">[Microsoft. CodeAnalysis. NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) incluye archivos EditorConfig y conjuntos de reglas predefinidos para las siguientes categorías de reglas:</span><span class="sxs-lookup"><span data-stu-id="e58d4-107">[Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) includes predefined EditorConfig files and rule sets for the following rule categories:</span></span>

- <span data-ttu-id="e58d4-108">Todas las reglas</span><span class="sxs-lookup"><span data-stu-id="e58d4-108">All rules</span></span>
- <span data-ttu-id="e58d4-109">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="e58d4-109">Dataflow</span></span>
- <span data-ttu-id="e58d4-110">Diseño</span><span class="sxs-lookup"><span data-stu-id="e58d4-110">Design</span></span>
- <span data-ttu-id="e58d4-111">Documentación</span><span class="sxs-lookup"><span data-stu-id="e58d4-111">Documentation</span></span>
- <span data-ttu-id="e58d4-112">Globalización</span><span class="sxs-lookup"><span data-stu-id="e58d4-112">Globalization</span></span>
- <span data-ttu-id="e58d4-113">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="e58d4-113">Interoperability</span></span>
- <span data-ttu-id="e58d4-114">Capacidad de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="e58d4-114">Maintainability</span></span>
- <span data-ttu-id="e58d4-115">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e58d4-115">Naming</span></span>
- <span data-ttu-id="e58d4-116">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="e58d4-116">Performance</span></span>
- <span data-ttu-id="e58d4-117">Trasladado desde FxCop</span><span class="sxs-lookup"><span data-stu-id="e58d4-117">Ported from FxCop</span></span>
- <span data-ttu-id="e58d4-118">Confiabilidad</span><span class="sxs-lookup"><span data-stu-id="e58d4-118">Reliability</span></span>
- <span data-ttu-id="e58d4-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e58d4-119">Security</span></span>
- <span data-ttu-id="e58d4-120">Uso</span><span class="sxs-lookup"><span data-stu-id="e58d4-120">Usage</span></span>

<span data-ttu-id="e58d4-121">Cada una de esas categorías de reglas tiene un EditorConfig o un archivo de conjunto de reglas para:</span><span class="sxs-lookup"><span data-stu-id="e58d4-121">Each of those categories of rules has an EditorConfig or rule set file to:</span></span>

- <span data-ttu-id="e58d4-122">Habilitar todas las reglas de la categoría (y deshabilitar todas las demás reglas)</span><span class="sxs-lookup"><span data-stu-id="e58d4-122">Enable all the rules in the category (and disable all other rules)</span></span>
- <span data-ttu-id="e58d4-123">Usar la gravedad predeterminada de cada regla y habilitarla de forma predeterminada (y deshabilitar todas las demás reglas)</span><span class="sxs-lookup"><span data-stu-id="e58d4-123">Use each rule's default severity and enabled by default setting (and disable all other rules)</span></span>

> [!TIP]
> <span data-ttu-id="e58d4-124">La categoría "todas las reglas" tiene un EditorConfig adicional o un archivo de conjunto de reglas para deshabilitar todas las reglas.</span><span class="sxs-lookup"><span data-stu-id="e58d4-124">The "all rules" category has an additional EditorConfig or rule set file to disable all rules.</span></span> <span data-ttu-id="e58d4-125">Use este archivo para deshacerse rápidamente de cualquier error o advertencia del analizador en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="e58d4-125">Use this file to quickly get rid of any analyzer warnings or errors in a project.</span></span>

## <a name="predefined-editorconfig-files"></a><span data-ttu-id="e58d4-126">Archivos EditorConfig predefinidos</span><span class="sxs-lookup"><span data-stu-id="e58d4-126">Predefined EditorConfig files</span></span>

<span data-ttu-id="e58d4-127">Los archivos EditorConfig predefinidos para el paquete Microsoft. CodeAnalysis. NetAnalyzers Analyzer se encuentran en el subdirectorio *EditorConfig* de donde se instaló el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="e58d4-127">The predefined EditorConfig files for the Microsoft.CodeAnalysis.NetAnalyzers analyzer package are located in the *editorconfig* subdirectory of where the NuGet package was installed.</span></span> <span data-ttu-id="e58d4-128">Por ejemplo, el archivo EditorConfig para habilitar todas las reglas de seguridad se encuentra en *EditorConfig/SecurityRulesEnabled/. EditorConfig*.</span><span class="sxs-lookup"><span data-stu-id="e58d4-128">For example, the EditorConfig file to enable all security rules is located at *editorconfig/SecurityRulesEnabled/.editorconfig*.</span></span>

<span data-ttu-id="e58d4-129">Copie el archivo *. editorconfig* elegido en el directorio raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e58d4-129">Copy the chosen *.editorconfig* file to your project's root directory.</span></span>

## <a name="predefined-rule-sets"></a><span data-ttu-id="e58d4-130">Conjunto de reglas predefinidas</span><span class="sxs-lookup"><span data-stu-id="e58d4-130">Predefined rule sets</span></span>

<span data-ttu-id="e58d4-131">Los archivos de conjunto de reglas predefinidos para el paquete Microsoft. CodeAnalysis. NetAnalyzers Analyzer se encuentran en el subdirectorio de *conjuntos* de reglas donde se instaló el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="e58d4-131">The predefined rule set files for the Microsoft.CodeAnalysis.NetAnalyzers analyzer package are located in the *rulesets* subdirectory of where the NuGet package was installed.</span></span> <span data-ttu-id="e58d4-132">Por ejemplo, el archivo de conjunto de reglas para habilitar todas las reglas de seguridad se encuentra en conjuntos de reglas */SecurityRulesEnabled. ruleset*.</span><span class="sxs-lookup"><span data-stu-id="e58d4-132">For example, the rule set file to enable all security rules is located at *rulesets/SecurityRulesEnabled.ruleset*.</span></span> <span data-ttu-id="e58d4-133">Copie uno o más conjuntos de reglas y péguelos en el directorio que contiene el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e58d4-133">Copy one or more of the rule sets and paste them in the directory that contains your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="e58d4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e58d4-134">See also</span></span>

- [<span data-ttu-id="e58d4-135">Configuración del analizador</span><span class="sxs-lookup"><span data-stu-id="e58d4-135">Analyzer configuration</span></span>](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [<span data-ttu-id="e58d4-136">Opciones de regla de estilo de código .NET para EditorConfig</span><span class="sxs-lookup"><span data-stu-id="e58d4-136">.NET code style rule options for EditorConfig</span></span>](code-style-rule-options.md)
