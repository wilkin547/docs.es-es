---
title: CorCheckDuplicatesFor (Enumeración)
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176193"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="f49de-102">CorCheckDuplicatesFor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f49de-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="f49de-103">Especifica los tokens de metadatos que se comprobarán en busca de duplicados.</span><span class="sxs-lookup"><span data-stu-id="f49de-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f49de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f49de-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="f49de-105">Members</span><span class="sxs-lookup"><span data-stu-id="f49de-105">Members</span></span>  
  
|<span data-ttu-id="f49de-106">Member</span><span class="sxs-lookup"><span data-stu-id="f49de-106">Member</span></span>|<span data-ttu-id="f49de-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f49de-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="f49de-108">Compruebe todos los tokens de metadatos en busca de duplicados.</span><span class="sxs-lookup"><span data-stu-id="f49de-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="f49de-109">No se usa.</span><span class="sxs-lookup"><span data-stu-id="f49de-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="f49de-110">No compruebe los tokens de metadatos en busca de duplicados.</span><span class="sxs-lookup"><span data-stu-id="f49de-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="f49de-111">Compruebe si hay `mdTypeDef` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="f49de-112">Compruebe si hay `mdInterfaceImpl` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="f49de-113">Compruebe si hay `mdMethodDef` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="f49de-114">Compruebe si hay `mdTypeRef` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="f49de-115">Compruebe si hay `mdMemberRef` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="f49de-116">Compruebe si hay `mdCustomAttribute` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="f49de-117">Compruebe si hay `mdParamDef` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="f49de-118">Compruebe si hay `mdPermission` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="f49de-119">Compruebe si hay `mdProperty` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="f49de-120">Compruebe si hay `mdEvent` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="f49de-121">Compruebe si hay `mdFieldDef` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="f49de-122">Compruebe si hay `mdSignature` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="f49de-123">Compruebe si hay `mdModuleRef` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="f49de-124">Compruebe si hay `mdTypeSpec` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="f49de-125">Compruebe si hay `mdImplMap` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="f49de-126">Compruebe si hay `mdAssemblyRef` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="f49de-127">Compruebe si hay `mdFile` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="f49de-128">Compruebe si hay `mdExportedType` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="f49de-129">Compruebe si hay `mdManifestResource` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="f49de-130">Compruebe si hay `mdGenericParam` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="f49de-131">Compruebe si hay `mdMethodSpec` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="f49de-132">Compruebe si hay `mdGenericParamConstraint` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="f49de-133">Compruebe si hay `mdAssembly` duplicados de tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="f49de-134">Compruebe si hay `mdMemberRef` `mdTypeRef`duplicados `mdTypeSpec`de `mdMethodSpec` , , `mdSignature`, y tokens.</span><span class="sxs-lookup"><span data-stu-id="f49de-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f49de-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f49de-135">Requirements</span></span>  
 <span data-ttu-id="f49de-136">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f49de-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f49de-137">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f49de-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f49de-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f49de-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f49de-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f49de-139">See also</span></span>

- [<span data-ttu-id="f49de-140">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f49de-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
