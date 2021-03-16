---
title: CorFlags.exe (Herramienta de conversión de CorFlags)
description: Obtenga información sobre CorFlags.exe, la herramienta de conversión de CorFlags. Esta herramienta permite configurar la sección CorFlags del encabezado de una imagen ejecutable portable.
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: 4481e6718372fe7b58dbc05ab7cfe35e6d3047ce
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258057"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="52c84-104">CorFlags.exe (Herramienta de conversión de CorFlags)</span><span class="sxs-lookup"><span data-stu-id="52c84-104">CorFlags.exe (CorFlags Conversion Tool)</span></span>

<span data-ttu-id="52c84-105">La herramienta de conversión CorFlags permite configurar la sección de CorFlags del encabezado de una imagen ejecutable portátil.</span><span class="sxs-lookup"><span data-stu-id="52c84-105">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="52c84-106">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52c84-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="52c84-107">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="52c84-107">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="52c84-108">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52c84-108">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c84-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52c84-109">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="52c84-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52c84-110">Parameters</span></span>  
  
|<span data-ttu-id="52c84-111">Parámetro requerido</span><span class="sxs-lookup"><span data-stu-id="52c84-111">Required parameter</span></span>|<span data-ttu-id="52c84-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="52c84-112">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="52c84-113">El nombre del ensamblado para el que se va a configurar CorFlags.</span><span class="sxs-lookup"><span data-stu-id="52c84-113">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="52c84-114">Opción</span><span class="sxs-lookup"><span data-stu-id="52c84-114">Option</span></span>|<span data-ttu-id="52c84-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="52c84-115">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="52c84-116">Establece la marca 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="52c84-116">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="52c84-117">Borra la marca 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="52c84-117">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="52c84-118">Establece la marca 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="52c84-118">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="52c84-119">La aplicación se ejecuta como un proceso de 32 bits incluso en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="52c84-119">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="52c84-120">Establezca esta marca únicamente en archivos EXE.</span><span class="sxs-lookup"><span data-stu-id="52c84-120">Set this flag only on EXE files.</span></span> <span data-ttu-id="52c84-121">Si la marca se establece en un archivo DLL, este genera un error al cargarse en procesos de 64 bits y se produce una excepción <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="52c84-121">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="52c84-122">Los archivos EXE que tienen esta marca se pueden cargar en procesos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="52c84-122">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="52c84-123">Novedades de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="52c84-123">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="52c84-124">Borra la marca 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="52c84-124">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="52c84-125">Novedades de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="52c84-125">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="52c84-126">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="52c84-126">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="52c84-127">Fuerza una actualización aunque se trate de un ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="52c84-127">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="52c84-128">**Importante:**  Si actualiza un ensamblado con nombre seguro, deberá volverlo a firmar antes de ejecutar su código.</span><span class="sxs-lookup"><span data-stu-id="52c84-128">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="52c84-129">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="52c84-129">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="52c84-130">Establece la marca ILONLY.</span><span class="sxs-lookup"><span data-stu-id="52c84-130">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="52c84-131">Borra la marca ILONLY.</span><span class="sxs-lookup"><span data-stu-id="52c84-131">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="52c84-132">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52c84-132">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="52c84-133">Vuelve a establecer la versión del encabezado CLR en 2.0.</span><span class="sxs-lookup"><span data-stu-id="52c84-133">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="52c84-134">Actualiza la versión del encabezado CLR a la 2.5.</span><span class="sxs-lookup"><span data-stu-id="52c84-134">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="52c84-135">**Nota:**  Para que los ensamblados se ejecuten de forma nativa, la versión del encabezado CLR debe ser la 2.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="52c84-135">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52c84-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52c84-136">Remarks</span></span>  

 <span data-ttu-id="52c84-137">Si no se especifica ninguna opción, la herramienta de conversión CorFlags muestra las marcas para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="52c84-137">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c84-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="52c84-138">See also</span></span>

- [<span data-ttu-id="52c84-139">Herramientas</span><span class="sxs-lookup"><span data-stu-id="52c84-139">Tools</span></span>](index.md)
- [<span data-ttu-id="52c84-140">Aplicaciones de 64 bits</span><span class="sxs-lookup"><span data-stu-id="52c84-140">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="52c84-141">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="52c84-141">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
