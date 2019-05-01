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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d04f5589ecffbcde59a6ffbe4f3d6c5f0b1040cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046051"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="a9e85-102">CorCheckDuplicatesFor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a9e85-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="a9e85-103">Especifica los tokens de metadatos que se comprobará si existen duplicados.</span><span class="sxs-lookup"><span data-stu-id="a9e85-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9e85-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9e85-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="a9e85-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a9e85-105">Members</span></span>  
  
|<span data-ttu-id="a9e85-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a9e85-106">Member</span></span>|<span data-ttu-id="a9e85-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9e85-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="a9e85-108">Compruebe todos los tokens de metadatos para los duplicados.</span><span class="sxs-lookup"><span data-stu-id="a9e85-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="a9e85-109">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a9e85-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="a9e85-110">No comprobar los tokens de metadatos para los duplicados.</span><span class="sxs-lookup"><span data-stu-id="a9e85-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="a9e85-111">Comprobar duplicados de `mdTypeDef` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="a9e85-112">Comprobar duplicados de `mdInterfaceImpl` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="a9e85-113">Comprobar duplicados de `mdMethodDef` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="a9e85-114">Comprobar duplicados de `mdTypeRef` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="a9e85-115">Comprobar duplicados de `mdMemberRef` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="a9e85-116">Comprobar duplicados de `mdCustomAttribute` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="a9e85-117">Comprobar duplicados de `mdParamDef` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="a9e85-118">Comprobar duplicados de `mdPermission` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="a9e85-119">Comprobar duplicados de `mdProperty` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="a9e85-120">Comprobar duplicados de `mdEvent` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="a9e85-121">Comprobar duplicados de `mdFieldDef` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="a9e85-122">Comprobar duplicados de `mdSignature` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="a9e85-123">Comprobar duplicados de `mdModuleRef` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="a9e85-124">Comprobar duplicados de `mdTypeSpec` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="a9e85-125">Comprobar duplicados de `mdImplMap` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="a9e85-126">Comprobar duplicados de `mdAssemblyRef` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="a9e85-127">Comprobar duplicados de `mdFile` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="a9e85-128">Comprobar duplicados de `mdExportedType` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="a9e85-129">Comprobar duplicados de `mdManifestResource` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="a9e85-130">Comprobar duplicados de `mdGenericParam` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="a9e85-131">Comprobar duplicados de `mdMethodSpec` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="a9e85-132">Comprobar duplicados de `mdGenericParamConstraint` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="a9e85-133">Comprobar duplicados de `mdAssembly` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="a9e85-134">Comprobar duplicados de `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, y `mdMethodSpec` tokens.</span><span class="sxs-lookup"><span data-stu-id="a9e85-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9e85-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9e85-135">Requirements</span></span>  
 <span data-ttu-id="a9e85-136">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9e85-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9e85-137">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a9e85-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a9e85-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9e85-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e85-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9e85-139">See also</span></span>

- [<span data-ttu-id="a9e85-140">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="a9e85-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
