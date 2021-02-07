---
description: 'Más información acerca de: estructura ASSEMBLYMETADATA ('
title: ASSEMBLYMETADATA (Estructura)
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 6fc9c03bea3b1413cd3a8421746137e37d43bd90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678944"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="7ac4d-103">ASSEMBLYMETADATA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="7ac4d-103">ASSEMBLYMETADATA Structure</span></span>

<span data-ttu-id="7ac4d-104">Contiene información acerca del ensamblado al que se hace referencia, incluida su versión y su nivel de compatibilidad con configuraciones regionales, procesadores y sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-104">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ac4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ac4d-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="7ac4d-106">Members</span><span class="sxs-lookup"><span data-stu-id="7ac4d-106">Members</span></span>  
  
|<span data-ttu-id="7ac4d-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="7ac4d-107">Member</span></span>|<span data-ttu-id="7ac4d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ac4d-108">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="7ac4d-109">Número de versión principal del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-109">The major version number of the referenced assembly.</span></span> <span data-ttu-id="7ac4d-110">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-110">This value cannot be zero.</span></span> <span data-ttu-id="7ac4d-111">Si se establecen todos los bits de `usMajorVersion` , no se especifica la versión principal.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-111">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="7ac4d-112">Número de versión secundaria del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-112">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="7ac4d-113">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-113">This value cannot be zero.</span></span> <span data-ttu-id="7ac4d-114">Si se establecen todos los bits de `usMinorVersion` , no se especifica la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-114">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="7ac4d-115">Número de compilación del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-115">The build number of the referenced assembly.</span></span> <span data-ttu-id="7ac4d-116">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-116">This value cannot be zero.</span></span> <span data-ttu-id="7ac4d-117">Si se establecen todos los bits de `usBuildNumber` , no se especifica el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-117">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="7ac4d-118">El número de revisión del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-118">The revision number of the referenced assembly.</span></span> <span data-ttu-id="7ac4d-119">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-119">This value cannot be zero.</span></span> <span data-ttu-id="7ac4d-120">Si se establecen todos los bits de `usRevisionNumber` , no se especifica el número de revisión.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-120">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="7ac4d-121">Una lista de nombres de configuración regional que se ajustan a la especificación de RFC1766, separadas por punto y coma, que especifican las configuraciones regionales que admite el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-121">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="7ac4d-122">Un valor null indica la independencia de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-122">A null value indicates locale independence.</span></span> <span data-ttu-id="7ac4d-123">**Nota:**  En la versión .NET Framework 1,0 no puede especificar más de una configuración regional.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-123">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="7ac4d-124">Tamaño en caracteres anchos de `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="7ac4d-124">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="7ac4d-125">Matriz de identificadores, tal y como se define en Winnt. h, para los tipos de procesador admitidos por el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-125">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="7ac4d-126">Un valor NULL indica la independencia del procesador.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-126">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="7ac4d-127">Longitud de la matriz `rdwProcessor`.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-127">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="7ac4d-128">Una matriz de instancias de [OSINFO](osinfo-structure.md) que especifican los sistemas operativos admitidos por el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-128">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="7ac4d-129">Un valor NULL indica la independencia del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-129">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="7ac4d-130">Longitud de la matriz `rOS`.</span><span class="sxs-lookup"><span data-stu-id="7ac4d-130">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ac4d-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ac4d-131">Requirements</span></span>  

 <span data-ttu-id="7ac4d-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ac4d-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ac4d-133">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7ac4d-133">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ac4d-134">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ac4d-134">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ac4d-135">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac4d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac4d-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ac4d-136">See also</span></span>

- [<span data-ttu-id="7ac4d-137">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="7ac4d-137">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="7ac4d-138">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ac4d-138">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="7ac4d-139">OSINFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="7ac4d-139">OSINFO Structure</span></span>](osinfo-structure.md)
