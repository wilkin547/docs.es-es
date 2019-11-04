---
title: CorFlags.exe (Herramienta de conversión de CorFlags)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: e1251b6660db45f3af4f6e57114b1b10da18bd0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129862"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="17d83-102">CorFlags.exe (Herramienta de conversión de CorFlags)</span><span class="sxs-lookup"><span data-stu-id="17d83-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="17d83-103">La herramienta de conversión CorFlags permite configurar la sección de CorFlags del encabezado de una imagen ejecutable portátil.</span><span class="sxs-lookup"><span data-stu-id="17d83-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="17d83-104">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="17d83-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="17d83-105">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="17d83-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="17d83-106">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="17d83-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="17d83-107">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="17d83-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d83-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17d83-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="17d83-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17d83-109">Parameters</span></span>  
  
|<span data-ttu-id="17d83-110">Parámetro requerido</span><span class="sxs-lookup"><span data-stu-id="17d83-110">Required parameter</span></span>|<span data-ttu-id="17d83-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="17d83-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="17d83-112">El nombre del ensamblado para el que se va a configurar CorFlags.</span><span class="sxs-lookup"><span data-stu-id="17d83-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="17d83-113">Opción</span><span class="sxs-lookup"><span data-stu-id="17d83-113">Option</span></span>|<span data-ttu-id="17d83-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="17d83-114">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="17d83-115">Establece la marca 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="17d83-115">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="17d83-116">Borra la marca 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="17d83-116">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="17d83-117">Establece la marca 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="17d83-117">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="17d83-118">La aplicación se ejecuta como un proceso de 32 bits incluso en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="17d83-118">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="17d83-119">Establezca esta marca únicamente en archivos EXE.</span><span class="sxs-lookup"><span data-stu-id="17d83-119">Set this flag only on EXE files.</span></span> <span data-ttu-id="17d83-120">Si la marca se establece en un archivo DLL, este genera un error al cargarse en procesos de 64 bits y se produce una excepción <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="17d83-120">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="17d83-121">Los archivos EXE que tienen esta marca se pueden cargar en procesos de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="17d83-121">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="17d83-122">Novedades de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="17d83-122">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="17d83-123">Borra la marca 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="17d83-123">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="17d83-124">Novedades de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="17d83-124">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="17d83-125">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="17d83-125">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="17d83-126">Fuerza una actualización aunque se trate de un ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="17d83-126">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="17d83-127">**Importante:**  Si actualiza un ensamblado con nombre seguro, deberá volverlo a firmar antes de ejecutar su código.</span><span class="sxs-lookup"><span data-stu-id="17d83-127">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="17d83-128">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="17d83-128">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="17d83-129">Establece la marca ILONLY.</span><span class="sxs-lookup"><span data-stu-id="17d83-129">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="17d83-130">Borra la marca ILONLY.</span><span class="sxs-lookup"><span data-stu-id="17d83-130">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="17d83-131">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17d83-131">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="17d83-132">Vuelve a establecer la versión del encabezado CLR en 2.0.</span><span class="sxs-lookup"><span data-stu-id="17d83-132">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="17d83-133">Actualiza la versión del encabezado CLR a la 2.5.</span><span class="sxs-lookup"><span data-stu-id="17d83-133">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="17d83-134">**Nota:**  Para que los ensamblados se ejecuten de forma nativa, la versión del encabezado CLR debe ser la 2.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="17d83-134">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17d83-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17d83-135">Remarks</span></span>  
 <span data-ttu-id="17d83-136">Si no se especifica ninguna opción, la herramienta de conversión CorFlags muestra las marcas para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="17d83-136">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d83-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="17d83-137">See also</span></span>

- [<span data-ttu-id="17d83-138">Herramientas</span><span class="sxs-lookup"><span data-stu-id="17d83-138">Tools</span></span>](index.md)
- [<span data-ttu-id="17d83-139">Aplicaciones de 64 bits</span><span class="sxs-lookup"><span data-stu-id="17d83-139">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="17d83-140">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="17d83-140">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
