---
description: 'Más información sobre: enumeración CorCheckDuplicatesFor ('
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
ms.openlocfilehash: 5649fc6bc66dd282b64fb5064e302a9f77420cd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678441"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="44f50-103">CorCheckDuplicatesFor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="44f50-103">CorCheckDuplicatesFor Enumeration</span></span>

<span data-ttu-id="44f50-104">Especifica los tokens de metadatos en los que se comprobarán los duplicados.</span><span class="sxs-lookup"><span data-stu-id="44f50-104">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f50-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44f50-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="44f50-106">Members</span><span class="sxs-lookup"><span data-stu-id="44f50-106">Members</span></span>  
  
|<span data-ttu-id="44f50-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="44f50-107">Member</span></span>|<span data-ttu-id="44f50-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="44f50-108">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="44f50-109">Compruebe todos los tokens de metadatos en busca de duplicados.</span><span class="sxs-lookup"><span data-stu-id="44f50-109">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="44f50-110">No se usa.</span><span class="sxs-lookup"><span data-stu-id="44f50-110">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="44f50-111">No Compruebe los tokens de metadatos en busca de duplicados.</span><span class="sxs-lookup"><span data-stu-id="44f50-111">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="44f50-112">Compruebe si hay duplicados de `mdTypeDef` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-112">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="44f50-113">Compruebe si hay duplicados de `mdInterfaceImpl` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-113">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="44f50-114">Compruebe si hay duplicados de `mdMethodDef` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-114">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="44f50-115">Compruebe si hay duplicados de `mdTypeRef` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-115">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="44f50-116">Compruebe si hay duplicados de `mdMemberRef` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-116">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="44f50-117">Compruebe si hay duplicados de `mdCustomAttribute` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-117">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="44f50-118">Compruebe si hay duplicados de `mdParamDef` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-118">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="44f50-119">Compruebe si hay duplicados de `mdPermission` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-119">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="44f50-120">Compruebe si hay duplicados de `mdProperty` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-120">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="44f50-121">Compruebe si hay duplicados de `mdEvent` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-121">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="44f50-122">Compruebe si hay duplicados de `mdFieldDef` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-122">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="44f50-123">Compruebe si hay duplicados de `mdSignature` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-123">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="44f50-124">Compruebe si hay duplicados de `mdModuleRef` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-124">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="44f50-125">Compruebe si hay duplicados de `mdTypeSpec` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-125">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="44f50-126">Compruebe si hay duplicados de `mdImplMap` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-126">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="44f50-127">Compruebe si hay duplicados de `mdAssemblyRef` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-127">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="44f50-128">Compruebe si hay duplicados de `mdFile` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-128">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="44f50-129">Compruebe si hay duplicados de `mdExportedType` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-129">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="44f50-130">Compruebe si hay duplicados de `mdManifestResource` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-130">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="44f50-131">Compruebe si hay duplicados de `mdGenericParam` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-131">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="44f50-132">Compruebe si hay duplicados de `mdMethodSpec` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-132">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="44f50-133">Compruebe si hay duplicados de `mdGenericParamConstraint` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-133">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="44f50-134">Compruebe si hay duplicados de `mdAssembly` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-134">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="44f50-135">Compruebe si hay duplicados de,,, `mdMemberRef` `mdTypeRef` `mdSignature` `mdTypeSpec` y `mdMethodSpec` tokens.</span><span class="sxs-lookup"><span data-stu-id="44f50-135">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44f50-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44f50-136">Requirements</span></span>  

 <span data-ttu-id="44f50-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44f50-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f50-138">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="44f50-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="44f50-139">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f50-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f50-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="44f50-140">See also</span></span>

- [<span data-ttu-id="44f50-141">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="44f50-141">Metadata Enumerations</span></span>](metadata-enumerations.md)
