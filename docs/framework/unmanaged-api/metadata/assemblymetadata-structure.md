---
title: ASSEMBLYMETADATA (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 819510c14bd67e7fcc739a19ea945f16b2a66c9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="e610d-102">ASSEMBLYMETADATA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e610d-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="e610d-103">Contiene información sobre el ensamblado que se hace referencia, incluyendo su versión y su nivel de compatibilidad con configuraciones regionales, procesadores y sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="e610d-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e610d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e610d-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="e610d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e610d-105">Members</span></span>  
  
|<span data-ttu-id="e610d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e610d-106">Member</span></span>|<span data-ttu-id="e610d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e610d-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="e610d-108">El número de versión principal del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e610d-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="e610d-109">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="e610d-109">This value cannot be zero.</span></span> <span data-ttu-id="e610d-110">Si todos los bits de `usMajorVersion` están configurados, no se especifica la versión principal.</span><span class="sxs-lookup"><span data-stu-id="e610d-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="e610d-111">El número de versión secundaria del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e610d-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="e610d-112">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="e610d-112">This value cannot be zero.</span></span> <span data-ttu-id="e610d-113">Si todos los bits de `usMinorVersion` están configurados, no se especifica la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="e610d-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="e610d-114">El número de compilación del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e610d-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="e610d-115">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="e610d-115">This value cannot be zero.</span></span> <span data-ttu-id="e610d-116">Si todos los bits de `usBuildNumber` están configurados, no se especifica el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="e610d-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="e610d-117">El número de revisión del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e610d-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="e610d-118">Este valor no puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="e610d-118">This value cannot be zero.</span></span> <span data-ttu-id="e610d-119">Si todos los bits de `usRevisionNumber` están configurados, no se especifica el número de revisión.</span><span class="sxs-lookup"><span data-stu-id="e610d-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="e610d-120">Una lista de nombres de configuración regional que cumplen la especificación RFC1766, separada por punto y coma, especificar las configuraciones regionales admitidas por el ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e610d-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="e610d-121">Un valor null indica la independencia de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="e610d-121">A null value indicates locale independence.</span></span> <span data-ttu-id="e610d-122">**Nota:** en .NET Framework versión 1.0 no se puede especificar más de una configuración regional.</span><span class="sxs-lookup"><span data-stu-id="e610d-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="e610d-123">El tamaño en caracteres anchos de `szLocale`.</span><span class="sxs-lookup"><span data-stu-id="e610d-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="e610d-124">Una matriz de identificadores, tal como se define en Winnt.h, para los tipos de procesador que son compatibles con el ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e610d-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="e610d-125">Un valor NULL indica la dependencia del procesador.</span><span class="sxs-lookup"><span data-stu-id="e610d-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="e610d-126">La longitud de la `rdwProcessor` matriz.</span><span class="sxs-lookup"><span data-stu-id="e610d-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="e610d-127">Una matriz de [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instancias especificando los sistemas operativos que son compatibles con el ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e610d-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="e610d-128">Un valor NULL indica la dependencia del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e610d-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="e610d-129">La longitud de la `rOS` matriz.</span><span class="sxs-lookup"><span data-stu-id="e610d-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e610d-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e610d-130">Requirements</span></span>  
 <span data-ttu-id="e610d-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e610d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e610d-132">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e610d-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e610d-133">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e610d-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e610d-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e610d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e610d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e610d-135">See Also</span></span>  
 [<span data-ttu-id="e610d-136">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="e610d-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="e610d-137">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e610d-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="e610d-138">OSINFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="e610d-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
