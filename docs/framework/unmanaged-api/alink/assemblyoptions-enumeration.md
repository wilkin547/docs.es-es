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
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085420"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="4dd88-102">AssemblyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4dd88-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="4dd88-103">Enumera las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4dd88-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dd88-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dd88-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="4dd88-105">Campos</span><span class="sxs-lookup"><span data-stu-id="4dd88-105">Fields</span></span>  
  
|<span data-ttu-id="4dd88-106">Campo</span><span class="sxs-lookup"><span data-stu-id="4dd88-106">Field</span></span>|<span data-ttu-id="4dd88-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4dd88-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4dd88-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="4dd88-108">optAssemTitle</span></span>|<span data-ttu-id="4dd88-109">Cadena: representa el título del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4dd88-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="4dd88-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="4dd88-110">optAssemDescription</span></span>|<span data-ttu-id="4dd88-111">Cadena: contiene la descripción del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4dd88-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="4dd88-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="4dd88-112">optAssemConfig</span></span>|<span data-ttu-id="4dd88-113">Cadena: contiene la configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4dd88-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="4dd88-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="4dd88-114">optAssemOS</span></span>|<span data-ttu-id="4dd88-115">Cadena: codificada como: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="4dd88-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="4dd88-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="4dd88-116">optAssemProcessor</span></span>|<span data-ttu-id="4dd88-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="4dd88-117">ULONG</span></span>|  
|<span data-ttu-id="4dd88-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="4dd88-118">optAssemLocale</span></span>|<span data-ttu-id="4dd88-119">Cadena: contiene la configuración regional del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4dd88-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="4dd88-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="4dd88-120">optAssemVersion</span></span>|<span data-ttu-id="4dd88-121">Cadena: codificada como: "Principal.secundaria.compilación.revisión".</span><span class="sxs-lookup"><span data-stu-id="4dd88-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="4dd88-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="4dd88-122">optAssemCompany</span></span>|<span data-ttu-id="4dd88-123">Cadena: contiene la empresa.</span><span class="sxs-lookup"><span data-stu-id="4dd88-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="4dd88-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="4dd88-124">optAssemProduct</span></span>|<span data-ttu-id="4dd88-125">Cadena: contiene el nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="4dd88-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="4dd88-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="4dd88-126">optAssemProductVersion</span></span>|<span data-ttu-id="4dd88-127">Cadena (también conocido como InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="4dd88-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="4dd88-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="4dd88-128">optAssemCopyright</span></span>|<span data-ttu-id="4dd88-129">Cadena: contiene la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="4dd88-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="4dd88-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="4dd88-130">optAssemTrademark</span></span>|<span data-ttu-id="4dd88-131">Cadena: contiene la información de marca comercial.</span><span class="sxs-lookup"><span data-stu-id="4dd88-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="4dd88-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="4dd88-132">optAssemKeyFile</span></span>|<span data-ttu-id="4dd88-133">String (nombre de archivo).</span><span class="sxs-lookup"><span data-stu-id="4dd88-133">String (file name).</span></span>|  
|<span data-ttu-id="4dd88-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="4dd88-134">optAssemKeyName</span></span>|<span data-ttu-id="4dd88-135">Cadena (el nombre de clave).</span><span class="sxs-lookup"><span data-stu-id="4dd88-135">String (The key name).</span></span>|  
|<span data-ttu-id="4dd88-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="4dd88-136">optAssemAlgID</span></span>|<span data-ttu-id="4dd88-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="4dd88-137">ULONG</span></span>|  
|<span data-ttu-id="4dd88-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="4dd88-138">optAssemFlags</span></span>|<span data-ttu-id="4dd88-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="4dd88-139">ULONG</span></span>|  
|<span data-ttu-id="4dd88-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="4dd88-140">optAssemHalfSign</span></span>|<span data-ttu-id="4dd88-141">BOOL (también conocida como DelaySign).</span><span class="sxs-lookup"><span data-stu-id="4dd88-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="4dd88-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="4dd88-142">optAssemFileVersion</span></span>|<span data-ttu-id="4dd88-143">Cadena: codificada como "Major.Minor.Build.Revision" como ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="4dd88-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="4dd88-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="4dd88-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="4dd88-145">Cadena - codificada como "Principal.secundaria.compilación.revisión".</span><span class="sxs-lookup"><span data-stu-id="4dd88-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="4dd88-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="4dd88-146">optLastAssemOption</span></span>|<span data-ttu-id="4dd88-147">Un contador del número de elementos.</span><span class="sxs-lookup"><span data-stu-id="4dd88-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4dd88-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dd88-148">Requirements</span></span>  
 <span data-ttu-id="4dd88-149">**Encabezado:** alink.h</span><span class="sxs-lookup"><span data-stu-id="4dd88-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="4dd88-150">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="4dd88-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd88-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dd88-151">See also</span></span>

- [<span data-ttu-id="4dd88-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="4dd88-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
