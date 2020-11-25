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
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717036"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="cae08-102">AssemblyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cae08-102">AssemblyOptions Enumeration</span></span>

<span data-ttu-id="cae08-103">Enumera las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cae08-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae08-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cae08-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="cae08-105">Campos</span><span class="sxs-lookup"><span data-stu-id="cae08-105">Fields</span></span>  
  
|<span data-ttu-id="cae08-106">Campo</span><span class="sxs-lookup"><span data-stu-id="cae08-106">Field</span></span>|<span data-ttu-id="cae08-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cae08-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cae08-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="cae08-108">optAssemTitle</span></span>|<span data-ttu-id="cae08-109">Cadena: representa el título del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cae08-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="cae08-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="cae08-110">optAssemDescription</span></span>|<span data-ttu-id="cae08-111">Cadena: contiene la descripción del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cae08-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="cae08-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="cae08-112">optAssemConfig</span></span>|<span data-ttu-id="cae08-113">Cadena: contiene la configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cae08-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="cae08-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="cae08-114">optAssemOS</span></span>|<span data-ttu-id="cae08-115">Codificada por cadena como: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="cae08-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="cae08-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="cae08-116">optAssemProcessor</span></span>|<span data-ttu-id="cae08-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="cae08-117">ULONG</span></span>|  
|<span data-ttu-id="cae08-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="cae08-118">optAssemLocale</span></span>|<span data-ttu-id="cae08-119">Cadena: contiene la configuración regional del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cae08-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="cae08-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="cae08-120">optAssemVersion</span></span>|<span data-ttu-id="cae08-121">Codificado por cadena como: "Major. minor. Build. revision".</span><span class="sxs-lookup"><span data-stu-id="cae08-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="cae08-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="cae08-122">optAssemCompany</span></span>|<span data-ttu-id="cae08-123">Cadena: contiene la compañía.</span><span class="sxs-lookup"><span data-stu-id="cae08-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="cae08-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="cae08-124">optAssemProduct</span></span>|<span data-ttu-id="cae08-125">Cadena: contiene el nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="cae08-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="cae08-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="cae08-126">optAssemProductVersion</span></span>|<span data-ttu-id="cae08-127">Cadena (también conocida como InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="cae08-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="cae08-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="cae08-128">optAssemCopyright</span></span>|<span data-ttu-id="cae08-129">Cadena: contiene la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="cae08-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="cae08-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="cae08-130">optAssemTrademark</span></span>|<span data-ttu-id="cae08-131">Cadena: contiene la información de marca comercial.</span><span class="sxs-lookup"><span data-stu-id="cae08-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="cae08-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="cae08-132">optAssemKeyFile</span></span>|<span data-ttu-id="cae08-133">Cadena (nombre de archivo).</span><span class="sxs-lookup"><span data-stu-id="cae08-133">String (file name).</span></span>|  
|<span data-ttu-id="cae08-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="cae08-134">optAssemKeyName</span></span>|<span data-ttu-id="cae08-135">Cadena (el nombre de la clave).</span><span class="sxs-lookup"><span data-stu-id="cae08-135">String (The key name).</span></span>|  
|<span data-ttu-id="cae08-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="cae08-136">optAssemAlgID</span></span>|<span data-ttu-id="cae08-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="cae08-137">ULONG</span></span>|  
|<span data-ttu-id="cae08-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="cae08-138">optAssemFlags</span></span>|<span data-ttu-id="cae08-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="cae08-139">ULONG</span></span>|  
|<span data-ttu-id="cae08-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="cae08-140">optAssemHalfSign</span></span>|<span data-ttu-id="cae08-141">Bool (también conocido como DelaySign).</span><span class="sxs-lookup"><span data-stu-id="cae08-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="cae08-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="cae08-142">optAssemFileVersion</span></span>|<span data-ttu-id="cae08-143">Codificación de cadena como "Major. minor. Build. revision", igual que ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="cae08-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="cae08-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="cae08-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="cae08-145">Codificación de cadena como "Major. minor. Build. revision".</span><span class="sxs-lookup"><span data-stu-id="cae08-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="cae08-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="cae08-146">optLastAssemOption</span></span>|<span data-ttu-id="cae08-147">Contador del número de elementos.</span><span class="sxs-lookup"><span data-stu-id="cae08-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cae08-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cae08-148">Requirements</span></span>  

 <span data-ttu-id="cae08-149">**Encabezado:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="cae08-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="cae08-150">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="cae08-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae08-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cae08-151">See also</span></span>

- [<span data-ttu-id="cae08-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="cae08-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
