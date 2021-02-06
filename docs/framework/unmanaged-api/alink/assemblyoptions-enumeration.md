---
description: 'Más información sobre: enumeración Assemblyoptions ('
title: AssemblyOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
ms.openlocfilehash: aba9ecb3176f533e2d53e2e45fef3d1dc4e55077
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638423"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="cdf7b-103">AssemblyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cdf7b-103">AssemblyOptions Enumeration</span></span>

<span data-ttu-id="cdf7b-104">Enumera las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-104">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdf7b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdf7b-105">Syntax</span></span>  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="cdf7b-106">Campos</span><span class="sxs-lookup"><span data-stu-id="cdf7b-106">Fields</span></span>  
  
|<span data-ttu-id="cdf7b-107">Campo</span><span class="sxs-lookup"><span data-stu-id="cdf7b-107">Field</span></span>|<span data-ttu-id="cdf7b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdf7b-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cdf7b-109">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="cdf7b-109">optAssemTitle</span></span>|<span data-ttu-id="cdf7b-110">Cadena: representa el título del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-110">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="cdf7b-111">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="cdf7b-111">optAssemDescription</span></span>|<span data-ttu-id="cdf7b-112">Cadena: contiene la descripción del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-112">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="cdf7b-113">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="cdf7b-113">optAssemConfig</span></span>|<span data-ttu-id="cdf7b-114">Cadena: contiene la configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-114">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="cdf7b-115">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="cdf7b-115">optAssemOS</span></span>|<span data-ttu-id="cdf7b-116">Codificada por cadena como: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="cdf7b-116">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="cdf7b-117">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="cdf7b-117">optAssemProcessor</span></span>|<span data-ttu-id="cdf7b-118">ULONG</span><span class="sxs-lookup"><span data-stu-id="cdf7b-118">ULONG</span></span>|  
|<span data-ttu-id="cdf7b-119">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="cdf7b-119">optAssemLocale</span></span>|<span data-ttu-id="cdf7b-120">Cadena: contiene la configuración regional del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-120">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="cdf7b-121">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="cdf7b-121">optAssemVersion</span></span>|<span data-ttu-id="cdf7b-122">Codificado por cadena como: "Major. minor. Build. revision".</span><span class="sxs-lookup"><span data-stu-id="cdf7b-122">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="cdf7b-123">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="cdf7b-123">optAssemCompany</span></span>|<span data-ttu-id="cdf7b-124">Cadena: contiene la compañía.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-124">String - Contains the company.</span></span>|  
|<span data-ttu-id="cdf7b-125">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="cdf7b-125">optAssemProduct</span></span>|<span data-ttu-id="cdf7b-126">Cadena: contiene el nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-126">String - Contains the product name.</span></span>|  
|<span data-ttu-id="cdf7b-127">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="cdf7b-127">optAssemProductVersion</span></span>|<span data-ttu-id="cdf7b-128">Cadena (también conocida como InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="cdf7b-128">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="cdf7b-129">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="cdf7b-129">optAssemCopyright</span></span>|<span data-ttu-id="cdf7b-130">Cadena: contiene la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-130">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="cdf7b-131">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="cdf7b-131">optAssemTrademark</span></span>|<span data-ttu-id="cdf7b-132">Cadena: contiene la información de marca comercial.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-132">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="cdf7b-133">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="cdf7b-133">optAssemKeyFile</span></span>|<span data-ttu-id="cdf7b-134">Cadena (nombre de archivo).</span><span class="sxs-lookup"><span data-stu-id="cdf7b-134">String (file name).</span></span>|  
|<span data-ttu-id="cdf7b-135">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="cdf7b-135">optAssemKeyName</span></span>|<span data-ttu-id="cdf7b-136">Cadena (el nombre de la clave).</span><span class="sxs-lookup"><span data-stu-id="cdf7b-136">String (The key name).</span></span>|  
|<span data-ttu-id="cdf7b-137">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="cdf7b-137">optAssemAlgID</span></span>|<span data-ttu-id="cdf7b-138">ULONG</span><span class="sxs-lookup"><span data-stu-id="cdf7b-138">ULONG</span></span>|  
|<span data-ttu-id="cdf7b-139">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="cdf7b-139">optAssemFlags</span></span>|<span data-ttu-id="cdf7b-140">ULONG</span><span class="sxs-lookup"><span data-stu-id="cdf7b-140">ULONG</span></span>|  
|<span data-ttu-id="cdf7b-141">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="cdf7b-141">optAssemHalfSign</span></span>|<span data-ttu-id="cdf7b-142">Bool (también conocido como DelaySign).</span><span class="sxs-lookup"><span data-stu-id="cdf7b-142">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="cdf7b-143">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="cdf7b-143">optAssemFileVersion</span></span>|<span data-ttu-id="cdf7b-144">Codificación de cadena como "Major. minor. Build. revision", igual que ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-144">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="cdf7b-145">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="cdf7b-145">optAssemSatelliteVer</span></span>|<span data-ttu-id="cdf7b-146">Codificación de cadena como "Major. minor. Build. revision".</span><span class="sxs-lookup"><span data-stu-id="cdf7b-146">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="cdf7b-147">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="cdf7b-147">optLastAssemOption</span></span>|<span data-ttu-id="cdf7b-148">Contador del número de elementos.</span><span class="sxs-lookup"><span data-stu-id="cdf7b-148">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cdf7b-149">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cdf7b-149">Requirements</span></span>  

 <span data-ttu-id="cdf7b-150">**Encabezado:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="cdf7b-150">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="cdf7b-151">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="cdf7b-151">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdf7b-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdf7b-152">See also</span></span>

- [<span data-ttu-id="cdf7b-153">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="cdf7b-153">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
