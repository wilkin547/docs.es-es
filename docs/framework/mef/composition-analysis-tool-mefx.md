---
title: Herramienta de análisis de composición (Mefx)
description: Obtenga información sobre la herramienta de análisis de composición (Mefx), que analiza los archivos DLL y EXE que contienen elementos de Managed Extensibility Framework (MEF) en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- Composition Analysis Tool [MEF]
- MEF, Composition Analysis Tool
- Mefx [MEF], Composition Analysis Tool
ms.assetid: c48a7f93-83bb-4a06-aea0-d8e7bd1502ad
ms.openlocfilehash: d3f3a282cfa9274a1939d312987dd58b24eab2af
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255798"
---
# <a name="composition-analysis-tool-mefx"></a><span data-ttu-id="9301c-103">Herramienta de análisis de composición (Mefx)</span><span class="sxs-lookup"><span data-stu-id="9301c-103">Composition Analysis Tool (Mefx)</span></span>

<span data-ttu-id="9301c-104">La herramienta de análisis de composición (Mefx) es una aplicación de línea de comandos que analiza los archivos de biblioteca (.dll) y los archivos de aplicación (.exe) que contienen elementos de Managed Extensibility Framework (MEF).</span><span class="sxs-lookup"><span data-stu-id="9301c-104">The Composition Analysis Tool (Mefx) is a command-line application that analyzes library (.dll) and application (.exe) files containing Managed Extensibility Framework (MEF) parts.</span></span> <span data-ttu-id="9301c-105">El propósito principal de Mefx es ofrecer a los desarrolladores una manera de diagnosticar errores de composición en sus aplicaciones de MEF sin el engorro de tener que agregar código de seguimiento a la propia aplicación.</span><span class="sxs-lookup"><span data-stu-id="9301c-105">The primary purpose of Mefx is to provide developers a way to diagnose composition failures in their MEF applications without the requirement to add cumbersome tracing code to the application itself.</span></span> <span data-ttu-id="9301c-106">También puede ser útil para ayudar a comprender los elementos de una biblioteca de terceros.</span><span class="sxs-lookup"><span data-stu-id="9301c-106">It can also be useful to help understand parts from a library provided by a third party.</span></span> <span data-ttu-id="9301c-107">En este tema se describe cómo usar Mefx y se proporciona una referencia de su sintaxis.</span><span class="sxs-lookup"><span data-stu-id="9301c-107">This topic describes how to use Mefx and provides a reference for its syntax.</span></span>  
  
<a name="getting_mefx"></a>

## <a name="getting-mefx"></a><span data-ttu-id="9301c-108">Obtener Mefx</span><span class="sxs-lookup"><span data-stu-id="9301c-108">Getting Mefx</span></span>  

 <span data-ttu-id="9301c-109">Mefx está disponible en GitHub, en [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0).</span><span class="sxs-lookup"><span data-stu-id="9301c-109">Mefx is available on GitHub at [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0).</span></span> <span data-ttu-id="9301c-110">Simplemente descargue y descomprima la herramienta.</span><span class="sxs-lookup"><span data-stu-id="9301c-110">Simply download and unzip the tool.</span></span>  
  
<a name="basic_syntax"></a>

## <a name="basic-syntax"></a><span data-ttu-id="9301c-111">Sintaxis básica</span><span class="sxs-lookup"><span data-stu-id="9301c-111">Basic Syntax</span></span>  

 <span data-ttu-id="9301c-112">Mefx se invoca desde la línea de comandos en el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="9301c-112">Mefx is invoked from the command line in the following format:</span></span>  
  
```console
mefx [files and directories] [action] [options]  
```  
  
 <span data-ttu-id="9301c-113">El primer conjunto de argumentos especifica los archivos y los directorios desde los que se cargan elementos para el análisis.</span><span class="sxs-lookup"><span data-stu-id="9301c-113">The first set of arguments specify the files and directories from which to load parts for analysis.</span></span> <span data-ttu-id="9301c-114">Especifique un archivo con el modificador `/file:` conmutador y un directorio con el modificador `/directory:` .</span><span class="sxs-lookup"><span data-stu-id="9301c-114">Specify a file with the `/file:` switch, and a directory with the `/directory:` switch.</span></span> <span data-ttu-id="9301c-115">Puede especificar varios archivos o directorios, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9301c-115">You can specify multiple files or directories, as shown in the following example:</span></span>  
  
```console  
mefx /file:MyAddIn.dll /directory:Program\AddIns [action...]  
```  
  
> [!NOTE]
> <span data-ttu-id="9301c-116">Cada archivo .dll o .exe solo se debe cargar una vez.</span><span class="sxs-lookup"><span data-stu-id="9301c-116">Each .dll or .exe should only be loaded one time.</span></span> <span data-ttu-id="9301c-117">Si se carga un archivo varias veces, la herramienta puede devolver información incorrecta.</span><span class="sxs-lookup"><span data-stu-id="9301c-117">If a file is loaded multiple times, the tool may return incorrect information.</span></span>  
  
 <span data-ttu-id="9301c-118">Después de crear la lista de archivos y directorios, especifique un comando y las opciones del mismo.</span><span class="sxs-lookup"><span data-stu-id="9301c-118">After the list of files and directories, you must specify a command, and any options for that command.</span></span>  
  
<a name="listing_available_parts"></a>

## <a name="listing-available-parts"></a><span data-ttu-id="9301c-119">Lista de los elementos disponibles</span><span class="sxs-lookup"><span data-stu-id="9301c-119">Listing Available Parts</span></span>  

 <span data-ttu-id="9301c-120">Use la acción `/parts` para enumerar todos los elementos declarados en los archivos cargados.</span><span class="sxs-lookup"><span data-stu-id="9301c-120">Use the `/parts` action to list all the parts declared in the files loaded.</span></span> <span data-ttu-id="9301c-121">El resultado es una lista de nombres de elementos.</span><span class="sxs-lookup"><span data-stu-id="9301c-121">The result is a simple list of part names.</span></span>  
  
```console
mefx /file:MyAddIn.dll /parts  
MyAddIn.AddIn  
MyAddIn.MemberPart  
```  
  
 <span data-ttu-id="9301c-122">Para obtener más información sobre los elementos, use la opción `/verbose` .</span><span class="sxs-lookup"><span data-stu-id="9301c-122">For more information about the parts, use the `/verbose` option.</span></span> <span data-ttu-id="9301c-123">Esto proporcionará más información sobre todos los elementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9301c-123">This will output more information for all available parts.</span></span> <span data-ttu-id="9301c-124">Para obtener más información sobre un único elemento, use la acción `/type` en lugar de `/parts`.</span><span class="sxs-lookup"><span data-stu-id="9301c-124">To get more information about a single part, use the `/type` action instead of `/parts`.</span></span>  
  
```console  
mefx /file:MyAddIn.dll /type:MyAddIn.AddIn /verbose  
[Part] MyAddIn.MemberPart from: AssemblyCatalog (Assembly=" MyAddIn, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] MyAddIn.MemberPart (ContractName=" MyAddIn.MemberPart")  
```  
  
<a name="listing_imports_and_exports"></a>

## <a name="listing-imports-and-exports"></a><span data-ttu-id="9301c-125">Lista de importaciones y exportaciones</span><span class="sxs-lookup"><span data-stu-id="9301c-125">Listing Imports and Exports</span></span>  

 <span data-ttu-id="9301c-126">Las acciones `/imports` y `/exports` enumerarán todos los elementos importados y exportados, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9301c-126">The `/imports` and `/exports` actions will list all the imported parts and all the exported parts, respectively.</span></span> <span data-ttu-id="9301c-127">También puede enumerar los elementos que importan o exportan un tipo determinado mediante las acciones `/importers` o `/exporters` .</span><span class="sxs-lookup"><span data-stu-id="9301c-127">You can also list the parts that import or export a particular type by using the `/importers` or `/exporters` actions.</span></span>  
  
```console  
mefx /file:MyAddIn.dll /importers:MyAddin.MemberPart  
MyAddin.AddIn  
```  
  
 <span data-ttu-id="9301c-128">Asimismo, puede aplicar la opción `/verbose` a estas acciones.</span><span class="sxs-lookup"><span data-stu-id="9301c-128">You can also apply the `/verbose` option to these actions.</span></span>  
  
<a name="finding_rejected_parts"></a>

## <a name="finding-rejected-parts"></a><span data-ttu-id="9301c-129">Búsqueda de elementos rechazados</span><span class="sxs-lookup"><span data-stu-id="9301c-129">Finding Rejected Parts</span></span>  

 <span data-ttu-id="9301c-130">Una vez cargados los elementos disponibles, Mefx usa el motor de composición de MEF para combinarlos.</span><span class="sxs-lookup"><span data-stu-id="9301c-130">Once it has loaded the available parts, Mefx uses the MEF composition engine to compose them.</span></span> <span data-ttu-id="9301c-131">Los elementos que no se pueden componer correctamente se denominan elementos *rechazados*.</span><span class="sxs-lookup"><span data-stu-id="9301c-131">Parts that cannot be successfully composed are referred to as *rejected*.</span></span> <span data-ttu-id="9301c-132">Para enumerar todos los elementos rechazados, use la acción `/rejected` .</span><span class="sxs-lookup"><span data-stu-id="9301c-132">To list all the rejected parts, use the `/rejected` action.</span></span>  
  
 <span data-ttu-id="9301c-133">Puede usar la opción `/verbose` con la acción `/rejected` para imprimir información detallada sobre los elementos rechazados.</span><span class="sxs-lookup"><span data-stu-id="9301c-133">You can use the `/verbose` option with the `/rejected` action to print detailed information about rejected parts.</span></span> <span data-ttu-id="9301c-134">En el ejemplo siguiente, la DLL `ClassLibrary1` contiene el elemento `AddIn` , que importa los elementos `MemberPart` y `ChainOne` .</span><span class="sxs-lookup"><span data-stu-id="9301c-134">In the following example, the `ClassLibrary1` DLL contains the `AddIn` part, which imports the `MemberPart` and `ChainOne` parts.</span></span> <span data-ttu-id="9301c-135">`ChainOne` importa `ChainTwo`, pero `ChainTwo` no existe.</span><span class="sxs-lookup"><span data-stu-id="9301c-135">`ChainOne` imports `ChainTwo`, but `ChainTwo` does not exist.</span></span> <span data-ttu-id="9301c-136">Esto significa que `ChainOne` se rechaza, lo que hace que `AddIn` también se rechace.</span><span class="sxs-lookup"><span data-stu-id="9301c-136">This means that `ChainOne` is rejected, which causes `AddIn` to be rejected.</span></span>  
  
```console  
mefx /file:ClassLibrary1.dll /rejected /verbose  
```  
  
 <span data-ttu-id="9301c-137">A continuación se muestra la salida completa del comando anterior:</span><span class="sxs-lookup"><span data-stu-id="9301c-137">The following shows the complete output of the previous command:</span></span>  
  
```output
[Part] ClassLibrary1.AddIn from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] ClassLibrary1.AddIn (ContractName="ClassLibrary1.AddIn")  
  [Import] ClassLibrary1.AddIn.memberPart (ContractName="ClassLibrary1.MemberPart")  
    [SatisfiedBy] ClassLibrary1.MemberPart (ContractName="ClassLibrary1.MemberPart") from: ClassLibrary1.MemberPart from: AssemblyCatalog (Assembly="ClassLibrar  
y1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Import] ClassLibrary1.AddIn.chain (ContractName="ClassLibrary1.ChainOne")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainOne") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainOne".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
    [Unsuitable] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
from: ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
      [Because] PartDefinitionIsRejected, The part providing the export is rejected because of other issues.  
  
[Part] ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Primary Rejection]  
  [Export] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
  [Import] ClassLibrary1.ChainOne.chain (ContractName="ClassLibrary1.ChainTwo")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainTwo") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainTwo".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
```  
  
 <span data-ttu-id="9301c-138">La información interesante se encuentra en los resultados de `[Exception]` y `[Unsuitable]` .</span><span class="sxs-lookup"><span data-stu-id="9301c-138">The interesting information is contained in the `[Exception]` and `[Unsuitable]` results.</span></span> <span data-ttu-id="9301c-139">El resultado de `[Exception]` proporciona información sobre el motivo de rechazo de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9301c-139">The `[Exception]` result provides information about why a part was rejected.</span></span> <span data-ttu-id="9301c-140">El resultado de `[Unsuitable]` indica por qué un elemento, que en otro caso se consideraría una coincidencia, no se pudo usar para rellenar una importación; en este caso, el motivo es que ese elemento también se rechazó para las importaciones que faltan.</span><span class="sxs-lookup"><span data-stu-id="9301c-140">The `[Unsuitable]` result indicates why an otherwise-matching part could not be used to fill an import; in this case, because that part was itself rejected for missing imports.</span></span>  
  
<a name="analyzing_primary_causes"></a>

## <a name="analyzing-primary-causes"></a><span data-ttu-id="9301c-141">Analizar las causas principales</span><span class="sxs-lookup"><span data-stu-id="9301c-141">Analyzing Primary Causes</span></span>  

 <span data-ttu-id="9301c-142">Si hay varios elementos vinculados en una cadena de dependencia larga, es posible que si se produce un problema en un elemento de la parte inferior, se rechace toda la cadena.</span><span class="sxs-lookup"><span data-stu-id="9301c-142">If several parts are linked in a long dependency chain, a problem involving a part near the bottom may cause the entire chain to be rejected.</span></span> <span data-ttu-id="9301c-143">Diagnosticar estos problemas puede ser difícil porque la causa principal del error no siempre está clara.</span><span class="sxs-lookup"><span data-stu-id="9301c-143">Diagnosing these problems can be difficult because the root cause of the failure is not always obvious.</span></span> <span data-ttu-id="9301c-144">Para ayudar a solucionar el problema, puede usar la acción `/causes` , que intenta encontrar la causa principal de cualquier rechazo en cascada.</span><span class="sxs-lookup"><span data-stu-id="9301c-144">To help with the problem, you can use the `/causes` action, which attempts to find the root cause of any cascading rejection.</span></span>  
  
 <span data-ttu-id="9301c-145">Mediante la acción `/causes` del ejemplo anterior se mostraría únicamente la información de `ChainOne`, cuya importación sin rellenar es la causa principal del rechazo de `AddIn`.</span><span class="sxs-lookup"><span data-stu-id="9301c-145">Using the `/causes` action on the previous example would list only information for `ChainOne`, whose unfilled import is the root cause of the rejection of `AddIn`.</span></span> <span data-ttu-id="9301c-146">La acción `/causes` se puede usar en las opciones normal y `/verbose` .</span><span class="sxs-lookup"><span data-stu-id="9301c-146">The `/causes` action can be used in both normal and `/verbose` options.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9301c-147">En la mayoría de los casos, Mefx podrá diagnosticar la causa principal de un error en cascada.</span><span class="sxs-lookup"><span data-stu-id="9301c-147">In most cases, Mefx will be able to diagnose the root cause of a cascading failure.</span></span> <span data-ttu-id="9301c-148">Sin embargo, Mefx no podrá diagnosticar la causa en aquellos casos en que los elementos se agregan mediante programación a un contenedor, ni tampoco en los casos relacionados con contenedores jerárquicos o en los que hay implementaciones de `ExportProvider` personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9301c-148">However, in cases where parts are added programmatically to a container, cases involving hierarchical containers, or cases involving custom `ExportProvider` implementations, Mefx will not be able to diagnose the cause.</span></span> <span data-ttu-id="9301c-149">En general, los casos descritos anteriormente deben evitarse siempre que sea posible, ya que los errores suelen ser difíciles de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="9301c-149">In general, the previously described cases should be avoided where possible, as failures are generally difficult to diagnose.</span></span>  
  
<a name="white_lists"></a>

## <a name="white-lists"></a><span data-ttu-id="9301c-150">Listas blancas</span><span class="sxs-lookup"><span data-stu-id="9301c-150">White Lists</span></span>  

 <span data-ttu-id="9301c-151">La opción `/whitelist` le permite especificar un archivo de texto que enumera los elementos que se esperan que se rechacen.</span><span class="sxs-lookup"><span data-stu-id="9301c-151">The `/whitelist` option enables you to specify a text file that lists parts that are expected to be rejected.</span></span> <span data-ttu-id="9301c-152">De este modo, se marcarán los rechazos inesperados.</span><span class="sxs-lookup"><span data-stu-id="9301c-152">Unexpected rejections will then be flagged.</span></span> <span data-ttu-id="9301c-153">Esto puede resultar útil al analizar una biblioteca incompleta o una biblioteca secundaria en la que falten algunas dependencias.</span><span class="sxs-lookup"><span data-stu-id="9301c-153">This can be useful when you analyze an incomplete library, or a sub-library that is missing some dependencies.</span></span> <span data-ttu-id="9301c-154">La opción `/whitelist` puede aplicarse a las acciones `/rejected` o `/causes` .</span><span class="sxs-lookup"><span data-stu-id="9301c-154">The `/whitelist` option can be applied to the `/rejected` or `/causes` actions.</span></span>  
  
 <span data-ttu-id="9301c-155">Piense en un archivo llamado test.txt que contenga el texto “ClassLibrary1.ChainOne”.</span><span class="sxs-lookup"><span data-stu-id="9301c-155">Consider a file named test.txt that contains the text "ClassLibrary1.ChainOne".</span></span> <span data-ttu-id="9301c-156">Si ejecuta la acción `/rejected` con la opción `/whitelist` en el ejemplo anterior, producirá la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="9301c-156">If you run the `/rejected` action with the `/whitelist` option on the previous example, it will produce the following output:</span></span>  
  
```console
mefx /file:ClassLibrary1.dll /rejected /whitelist:test.txt  
[Unexpected] ClassLibrary1.AddIn  
ClassLibrary1.ChainOne  
```
