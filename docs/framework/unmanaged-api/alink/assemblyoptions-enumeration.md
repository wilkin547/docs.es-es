---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49e7b73559e8def890f8df8f596fbe8ad5bb5d3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777486"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="42505-102">AssemblyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="42505-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="42505-103">Enumera las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42505-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42505-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42505-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="42505-105">Fields</span><span class="sxs-lookup"><span data-stu-id="42505-105">Fields</span></span>  
  
|<span data-ttu-id="42505-106">Campo</span><span class="sxs-lookup"><span data-stu-id="42505-106">Field</span></span>|<span data-ttu-id="42505-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="42505-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42505-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="42505-108">optAssemTitle</span></span>|<span data-ttu-id="42505-109">Cadena: representa el título del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42505-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="42505-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="42505-110">optAssemDescription</span></span>|<span data-ttu-id="42505-111">Cadena: contiene la descripción del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42505-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="42505-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="42505-112">optAssemConfig</span></span>|<span data-ttu-id="42505-113">Cadena: contiene la configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42505-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="42505-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="42505-114">optAssemOS</span></span>|<span data-ttu-id="42505-115">Codificada por cadena como: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="42505-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="42505-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="42505-116">optAssemProcessor</span></span>|<span data-ttu-id="42505-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="42505-117">ULONG</span></span>|  
|<span data-ttu-id="42505-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="42505-118">optAssemLocale</span></span>|<span data-ttu-id="42505-119">Cadena: contiene la configuración regional del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42505-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="42505-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="42505-120">optAssemVersion</span></span>|<span data-ttu-id="42505-121">Codificado por cadena como: "Major. minor. Build. revision".</span><span class="sxs-lookup"><span data-stu-id="42505-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="42505-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="42505-122">optAssemCompany</span></span>|<span data-ttu-id="42505-123">Cadena: contiene la compañía.</span><span class="sxs-lookup"><span data-stu-id="42505-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="42505-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="42505-124">optAssemProduct</span></span>|<span data-ttu-id="42505-125">Cadena: contiene el nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="42505-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="42505-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="42505-126">optAssemProductVersion</span></span>|<span data-ttu-id="42505-127">Cadena (también conocida como InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="42505-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="42505-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="42505-128">optAssemCopyright</span></span>|<span data-ttu-id="42505-129">Cadena: contiene la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="42505-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="42505-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="42505-130">optAssemTrademark</span></span>|<span data-ttu-id="42505-131">Cadena: contiene la información de marca comercial.</span><span class="sxs-lookup"><span data-stu-id="42505-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="42505-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="42505-132">optAssemKeyFile</span></span>|<span data-ttu-id="42505-133">Cadena (nombre de archivo).</span><span class="sxs-lookup"><span data-stu-id="42505-133">String (file name).</span></span>|  
|<span data-ttu-id="42505-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="42505-134">optAssemKeyName</span></span>|<span data-ttu-id="42505-135">Cadena (el nombre de la clave).</span><span class="sxs-lookup"><span data-stu-id="42505-135">String (The key name).</span></span>|  
|<span data-ttu-id="42505-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="42505-136">optAssemAlgID</span></span>|<span data-ttu-id="42505-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="42505-137">ULONG</span></span>|  
|<span data-ttu-id="42505-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="42505-138">optAssemFlags</span></span>|<span data-ttu-id="42505-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="42505-139">ULONG</span></span>|  
|<span data-ttu-id="42505-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="42505-140">optAssemHalfSign</span></span>|<span data-ttu-id="42505-141">Bool (también conocido como DelaySign).</span><span class="sxs-lookup"><span data-stu-id="42505-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="42505-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="42505-142">optAssemFileVersion</span></span>|<span data-ttu-id="42505-143">Codificación de cadena como "Major. minor. Build. revision", igual que ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="42505-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="42505-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="42505-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="42505-145">Codificación de cadena como "Major. minor. Build. revision".</span><span class="sxs-lookup"><span data-stu-id="42505-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="42505-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="42505-146">optLastAssemOption</span></span>|<span data-ttu-id="42505-147">Contador del número de elementos.</span><span class="sxs-lookup"><span data-stu-id="42505-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42505-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42505-148">Requirements</span></span>  
 <span data-ttu-id="42505-149">**Encabezado:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="42505-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="42505-150">**Biblioteca**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="42505-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42505-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="42505-151">See also</span></span>

- [<span data-ttu-id="42505-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="42505-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
