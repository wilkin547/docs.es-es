---
title: "CorFlags.exe (Herramienta de conversión de CorFlags)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 111c697d4d62cd52cd7913039e3c17e8a25ab50d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="922e0-102">CorFlags.exe (Herramienta de conversión de CorFlags)</span><span class="sxs-lookup"><span data-stu-id="922e0-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="922e0-103">La herramienta de conversión CorFlags permite configurar la sección de CorFlags del encabezado de una imagen ejecutable portátil.</span><span class="sxs-lookup"><span data-stu-id="922e0-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="922e0-104">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="922e0-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="922e0-105">Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores (o el Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="922e0-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="922e0-106">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="922e0-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="922e0-107">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="922e0-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="922e0-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="922e0-108">Syntax</span></span>  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="922e0-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="922e0-109">Parameters</span></span>  
  
|<span data-ttu-id="922e0-110">Parámetro requerido</span><span class="sxs-lookup"><span data-stu-id="922e0-110">Required parameter</span></span>|<span data-ttu-id="922e0-111">Description</span><span class="sxs-lookup"><span data-stu-id="922e0-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="922e0-112">El nombre del ensamblado para el que se va a configurar CorFlags.</span><span class="sxs-lookup"><span data-stu-id="922e0-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="922e0-113">Opción</span><span class="sxs-lookup"><span data-stu-id="922e0-113">Option</span></span>|<span data-ttu-id="922e0-114">Description</span><span class="sxs-lookup"><span data-stu-id="922e0-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="922e0-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="922e0-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="922e0-116">Establece la marca 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="922e0-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="922e0-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="922e0-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="922e0-118">Borra la marca 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="922e0-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="922e0-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="922e0-119">**/32BITPREF+**</span></span>|<span data-ttu-id="922e0-120">Establece la marca 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="922e0-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="922e0-121">La aplicación se ejecuta como un proceso de 32 bits incluso en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="922e0-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="922e0-122">Establezca esta marca únicamente en archivos EXE.</span><span class="sxs-lookup"><span data-stu-id="922e0-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="922e0-123">Si la marca se establece en un archivo DLL, este genera un error al cargarse en procesos de 64 bits y se produce una excepción <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="922e0-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="922e0-124">Los archivos EXE que tienen esta marca se pueden cargar en procesos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="922e0-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="922e0-125">Nueva en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="922e0-125">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="922e0-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="922e0-126">**/32BITPREF-**</span></span>|<span data-ttu-id="922e0-127">Borra la marca 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="922e0-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="922e0-128">Nueva en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="922e0-128">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="922e0-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="922e0-129">**/?**</span></span>|<span data-ttu-id="922e0-130">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="922e0-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="922e0-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="922e0-131">**/Force**</span></span>|<span data-ttu-id="922e0-132">Fuerza una actualización aunque se trate de un ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="922e0-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="922e0-133">**Importante:** Si actualiza un ensamblado con nombre seguro, deberá volver a firmarlo antes de ejecutar su código.</span><span class="sxs-lookup"><span data-stu-id="922e0-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="922e0-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="922e0-134">**/help**</span></span>|<span data-ttu-id="922e0-135">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="922e0-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="922e0-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="922e0-136">**/ILONLY+**</span></span>|<span data-ttu-id="922e0-137">Establece la marca ILONLY.</span><span class="sxs-lookup"><span data-stu-id="922e0-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="922e0-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="922e0-138">**/ILONLY-**</span></span>|<span data-ttu-id="922e0-139">Borra la marca ILONLY.</span><span class="sxs-lookup"><span data-stu-id="922e0-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="922e0-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="922e0-140">**/nologo**</span></span>|<span data-ttu-id="922e0-141">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="922e0-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="922e0-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="922e0-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="922e0-143">Vuelve a establecer la versión del encabezado CLR en 2.0.</span><span class="sxs-lookup"><span data-stu-id="922e0-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="922e0-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="922e0-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="922e0-145">Actualiza la versión del encabezado CLR a la 2.5.</span><span class="sxs-lookup"><span data-stu-id="922e0-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="922e0-146">**Nota:** Para que los ensamblados se ejecuten de forma nativa, la versión del encabezado CLR debe ser la 2.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="922e0-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="922e0-147">Comentarios</span><span class="sxs-lookup"><span data-stu-id="922e0-147">Remarks</span></span>  
 <span data-ttu-id="922e0-148">Si no se especifica ninguna opción, la herramienta de conversión CorFlags muestra las marcas para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="922e0-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="922e0-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="922e0-149">See Also</span></span>  
 [<span data-ttu-id="922e0-150">Herramientas</span><span class="sxs-lookup"><span data-stu-id="922e0-150">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="922e0-151">Aplicaciones de 64 bits</span><span class="sxs-lookup"><span data-stu-id="922e0-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)  
 [<span data-ttu-id="922e0-152">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="922e0-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
