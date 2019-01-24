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
ms.openlocfilehash: 939e815f4d3adc5f6e1c8b8fc85c9f4b89372501
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571488"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="721dd-102">AssemblyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="721dd-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="721dd-103">Enumera las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="721dd-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="721dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="721dd-104">Syntax</span></span>  
  
```  
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
  
## <a name="fields"></a><span data-ttu-id="721dd-105">Campos</span><span class="sxs-lookup"><span data-stu-id="721dd-105">Fields</span></span>  
  
|<span data-ttu-id="721dd-106">Campo</span><span class="sxs-lookup"><span data-stu-id="721dd-106">Field</span></span>|<span data-ttu-id="721dd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="721dd-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="721dd-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="721dd-108">optAssemTitle</span></span>|<span data-ttu-id="721dd-109">Cadena: representa el título del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="721dd-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="721dd-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="721dd-110">optAssemDescription</span></span>|<span data-ttu-id="721dd-111">Cadena: contiene la descripción del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="721dd-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="721dd-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="721dd-112">optAssemConfig</span></span>|<span data-ttu-id="721dd-113">Cadena: contiene la configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="721dd-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="721dd-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="721dd-114">optAssemOS</span></span>|<span data-ttu-id="721dd-115">Cadena: codificada como: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="721dd-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="721dd-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="721dd-116">optAssemProcessor</span></span>|<span data-ttu-id="721dd-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="721dd-117">ULONG</span></span>|  
|<span data-ttu-id="721dd-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="721dd-118">optAssemLocale</span></span>|<span data-ttu-id="721dd-119">Cadena: contiene la configuración regional del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="721dd-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="721dd-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="721dd-120">optAssemVersion</span></span>|<span data-ttu-id="721dd-121">Cadena: codificada como: "Principal.secundaria.compilación.revisión".</span><span class="sxs-lookup"><span data-stu-id="721dd-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="721dd-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="721dd-122">optAssemCompany</span></span>|<span data-ttu-id="721dd-123">Cadena: contiene la empresa.</span><span class="sxs-lookup"><span data-stu-id="721dd-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="721dd-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="721dd-124">optAssemProduct</span></span>|<span data-ttu-id="721dd-125">Cadena: contiene el nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="721dd-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="721dd-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="721dd-126">optAssemProductVersion</span></span>|<span data-ttu-id="721dd-127">Cadena (también conocido como InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="721dd-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="721dd-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="721dd-128">optAssemCopyright</span></span>|<span data-ttu-id="721dd-129">Cadena: contiene la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="721dd-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="721dd-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="721dd-130">optAssemTrademark</span></span>|<span data-ttu-id="721dd-131">Cadena: contiene la información de marca comercial.</span><span class="sxs-lookup"><span data-stu-id="721dd-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="721dd-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="721dd-132">optAssemKeyFile</span></span>|<span data-ttu-id="721dd-133">String (nombre de archivo).</span><span class="sxs-lookup"><span data-stu-id="721dd-133">String (file name).</span></span>|  
|<span data-ttu-id="721dd-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="721dd-134">optAssemKeyName</span></span>|<span data-ttu-id="721dd-135">Cadena (el nombre de clave).</span><span class="sxs-lookup"><span data-stu-id="721dd-135">String (The key name).</span></span>|  
|<span data-ttu-id="721dd-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="721dd-136">optAssemAlgID</span></span>|<span data-ttu-id="721dd-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="721dd-137">ULONG</span></span>|  
|<span data-ttu-id="721dd-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="721dd-138">optAssemFlags</span></span>|<span data-ttu-id="721dd-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="721dd-139">ULONG</span></span>|  
|<span data-ttu-id="721dd-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="721dd-140">optAssemHalfSign</span></span>|<span data-ttu-id="721dd-141">BOOL (también conocida como DelaySign).</span><span class="sxs-lookup"><span data-stu-id="721dd-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="721dd-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="721dd-142">optAssemFileVersion</span></span>|<span data-ttu-id="721dd-143">Cadena: codificada como "Major.Minor.Build.Revision" como ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="721dd-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="721dd-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="721dd-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="721dd-145">Cadena - codificada como "Principal.secundaria.compilación.revisión".</span><span class="sxs-lookup"><span data-stu-id="721dd-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="721dd-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="721dd-146">optLastAssemOption</span></span>|<span data-ttu-id="721dd-147">Un contador del número de elementos.</span><span class="sxs-lookup"><span data-stu-id="721dd-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="721dd-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="721dd-148">Requirements</span></span>  
 <span data-ttu-id="721dd-149">**Encabezado:** alink.h</span><span class="sxs-lookup"><span data-stu-id="721dd-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="721dd-150">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="721dd-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="721dd-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="721dd-151">See also</span></span>
- [<span data-ttu-id="721dd-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="721dd-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
