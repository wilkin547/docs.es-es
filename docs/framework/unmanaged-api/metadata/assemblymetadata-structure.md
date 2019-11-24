---
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
ms.openlocfilehash: 24ec1f7d553a59425f7eb02af8e91010d940eb07
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444258"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="92e22-102">ASSEMBLYMETADATA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="92e22-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="92e22-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span><span class="sxs-lookup"><span data-stu-id="92e22-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e22-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92e22-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="92e22-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="92e22-105">Members</span></span>  
  
|<span data-ttu-id="92e22-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="92e22-106">Member</span></span>|<span data-ttu-id="92e22-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="92e22-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="92e22-108">The major version number of the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="92e22-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="92e22-109">This value cannot be zero.</span><span class="sxs-lookup"><span data-stu-id="92e22-109">This value cannot be zero.</span></span> <span data-ttu-id="92e22-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span><span class="sxs-lookup"><span data-stu-id="92e22-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="92e22-111">The minor version number of the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="92e22-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="92e22-112">This value cannot be zero.</span><span class="sxs-lookup"><span data-stu-id="92e22-112">This value cannot be zero.</span></span> <span data-ttu-id="92e22-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span><span class="sxs-lookup"><span data-stu-id="92e22-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="92e22-114">The build number of the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="92e22-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="92e22-115">This value cannot be zero.</span><span class="sxs-lookup"><span data-stu-id="92e22-115">This value cannot be zero.</span></span> <span data-ttu-id="92e22-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span><span class="sxs-lookup"><span data-stu-id="92e22-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="92e22-117">The revision number of the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="92e22-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="92e22-118">This value cannot be zero.</span><span class="sxs-lookup"><span data-stu-id="92e22-118">This value cannot be zero.</span></span> <span data-ttu-id="92e22-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span><span class="sxs-lookup"><span data-stu-id="92e22-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="92e22-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="92e22-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="92e22-121">A null value indicates locale independence.</span><span class="sxs-lookup"><span data-stu-id="92e22-121">A null value indicates locale independence.</span></span> <span data-ttu-id="92e22-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span><span class="sxs-lookup"><span data-stu-id="92e22-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="92e22-123">The size in wide characters of `szLocale`.</span><span class="sxs-lookup"><span data-stu-id="92e22-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="92e22-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="92e22-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="92e22-125">A NULL value indicates processor independence.</span><span class="sxs-lookup"><span data-stu-id="92e22-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="92e22-126">The length of the `rdwProcessor` array.</span><span class="sxs-lookup"><span data-stu-id="92e22-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="92e22-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="92e22-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="92e22-128">A NULL value indicates operating-system independence.</span><span class="sxs-lookup"><span data-stu-id="92e22-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="92e22-129">The length of the `rOS` array.</span><span class="sxs-lookup"><span data-stu-id="92e22-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92e22-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92e22-130">Requirements</span></span>  
 <span data-ttu-id="92e22-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92e22-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92e22-132">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92e22-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92e22-133">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92e22-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92e22-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92e22-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e22-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="92e22-135">See also</span></span>

- [<span data-ttu-id="92e22-136">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="92e22-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="92e22-137">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="92e22-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="92e22-138">OSINFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="92e22-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
