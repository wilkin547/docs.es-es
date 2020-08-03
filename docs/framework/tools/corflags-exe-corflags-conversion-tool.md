---
title: CorFlags.exe (Herramienta de conversión de CorFlags)
description: Obtenga información sobre CorFlags.exe, la herramienta de conversión de CorFlags. Esta herramienta permite configurar la sección CorFlags del encabezado de una imagen ejecutable portable.
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: da5efadd63cc03f6f6e4eecf3115865ca3643b39
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167229"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="67e15-104">CorFlags.exe (Herramienta de conversión de CorFlags)</span><span class="sxs-lookup"><span data-stu-id="67e15-104">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="67e15-105">La herramienta de conversión CorFlags permite configurar la sección de CorFlags del encabezado de una imagen ejecutable portátil.</span><span class="sxs-lookup"><span data-stu-id="67e15-105">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="67e15-106">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="67e15-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="67e15-107">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="67e15-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="67e15-108">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="67e15-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="67e15-109">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="67e15-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e15-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67e15-110">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="67e15-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67e15-111">Parameters</span></span>  
  
|<span data-ttu-id="67e15-112">Parámetro requerido</span><span class="sxs-lookup"><span data-stu-id="67e15-112">Required parameter</span></span>|<span data-ttu-id="67e15-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="67e15-113">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="67e15-114">El nombre del ensamblado para el que se va a configurar CorFlags.</span><span class="sxs-lookup"><span data-stu-id="67e15-114">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="67e15-115">Opción</span><span class="sxs-lookup"><span data-stu-id="67e15-115">Option</span></span>|<span data-ttu-id="67e15-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="67e15-116">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="67e15-117">Establece la marca 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="67e15-117">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="67e15-118">Borra la marca 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="67e15-118">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="67e15-119">Establece la marca 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="67e15-119">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="67e15-120">La aplicación se ejecuta como un proceso de 32 bits incluso en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="67e15-120">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="67e15-121">Establezca esta marca únicamente en archivos EXE.</span><span class="sxs-lookup"><span data-stu-id="67e15-121">Set this flag only on EXE files.</span></span> <span data-ttu-id="67e15-122">Si la marca se establece en un archivo DLL, este genera un error al cargarse en procesos de 64 bits y se produce una excepción <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="67e15-122">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="67e15-123">Los archivos EXE que tienen esta marca se pueden cargar en procesos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="67e15-123">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="67e15-124">Novedades de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="67e15-124">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="67e15-125">Borra la marca 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="67e15-125">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="67e15-126">Novedades de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="67e15-126">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="67e15-127">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="67e15-127">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="67e15-128">Fuerza una actualización aunque se trate de un ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="67e15-128">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="67e15-129">**Importante:**  Si actualiza un ensamblado con nombre seguro, deberá volverlo a firmar antes de ejecutar su código.</span><span class="sxs-lookup"><span data-stu-id="67e15-129">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="67e15-130">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="67e15-130">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="67e15-131">Establece la marca ILONLY.</span><span class="sxs-lookup"><span data-stu-id="67e15-131">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="67e15-132">Borra la marca ILONLY.</span><span class="sxs-lookup"><span data-stu-id="67e15-132">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="67e15-133">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67e15-133">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="67e15-134">Vuelve a establecer la versión del encabezado CLR en 2.0.</span><span class="sxs-lookup"><span data-stu-id="67e15-134">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="67e15-135">Actualiza la versión del encabezado CLR a la 2.5.</span><span class="sxs-lookup"><span data-stu-id="67e15-135">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="67e15-136">**Nota:**  Para que los ensamblados se ejecuten de forma nativa, la versión del encabezado CLR debe ser la 2.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="67e15-136">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67e15-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67e15-137">Remarks</span></span>  
 <span data-ttu-id="67e15-138">Si no se especifica ninguna opción, la herramienta de conversión CorFlags muestra las marcas para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="67e15-138">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e15-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="67e15-139">See also</span></span>

- [<span data-ttu-id="67e15-140">Herramientas</span><span class="sxs-lookup"><span data-stu-id="67e15-140">Tools</span></span>](index.md)
- [<span data-ttu-id="67e15-141">Aplicaciones de 64 bits</span><span class="sxs-lookup"><span data-stu-id="67e15-141">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="67e15-142">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="67e15-142">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
