---
title: "CorCheckDuplicatesFor (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCheckDuplicatesFor
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCheckDuplicatesFor
helpviewer_keywords: CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c5a9376f6d56e2a21ee474e2724ce5eff8f6f63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="6be27-102">CorCheckDuplicatesFor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6be27-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="6be27-103">Especifica los tokens de metadatos que se va a comprobar si existen duplicados.</span><span class="sxs-lookup"><span data-stu-id="6be27-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6be27-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6be27-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6be27-105">Members</span></span>  
  
|<span data-ttu-id="6be27-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6be27-106">Member</span></span>|<span data-ttu-id="6be27-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6be27-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="6be27-108">Compruebe todos los tokens de metadatos para los duplicados.</span><span class="sxs-lookup"><span data-stu-id="6be27-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="6be27-109">No usado.</span><span class="sxs-lookup"><span data-stu-id="6be27-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="6be27-110">No proteja los tokens de metadatos para los duplicados.</span><span class="sxs-lookup"><span data-stu-id="6be27-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="6be27-111">Compruebe si existen duplicados de `mdTypeDef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="6be27-112">Compruebe si existen duplicados de `mdInterfaceImpl` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="6be27-113">Compruebe si existen duplicados de `mdMethodDef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="6be27-114">Compruebe si existen duplicados de `mdTypeRef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="6be27-115">Compruebe si existen duplicados de `mdMemberRef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="6be27-116">Compruebe si existen duplicados de `mdCustomAttribute` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="6be27-117">Compruebe si existen duplicados de `mdParamDef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="6be27-118">Compruebe si existen duplicados de `mdPermission` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="6be27-119">Compruebe si existen duplicados de `mdProperty` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="6be27-120">Compruebe si existen duplicados de `mdEvent` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="6be27-121">Compruebe si existen duplicados de `mdFieldDef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="6be27-122">Compruebe si existen duplicados de `mdSignature` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="6be27-123">Compruebe si existen duplicados de `mdModuleRef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="6be27-124">Compruebe si existen duplicados de `mdTypeSpec` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="6be27-125">Compruebe si existen duplicados de `mdImplMap` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="6be27-126">Compruebe si existen duplicados de `mdAssemblyRef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="6be27-127">Compruebe si existen duplicados de `mdFile` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="6be27-128">Compruebe si existen duplicados de `mdExportedType` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="6be27-129">Compruebe si existen duplicados de `mdManifestResource` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="6be27-130">Compruebe si existen duplicados de `mdGenericParam` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="6be27-131">Compruebe si existen duplicados de `mdMethodSpec` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="6be27-132">Compruebe si existen duplicados de `mdGenericParamConstraint` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="6be27-133">Compruebe si existen duplicados de `mdAssembly` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="6be27-134">Compruebe si existen duplicados de `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, y `mdMethodSpec` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6be27-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6be27-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6be27-135">Requirements</span></span>  
 <span data-ttu-id="6be27-136">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6be27-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6be27-137">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6be27-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6be27-138">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6be27-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be27-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="6be27-139">See Also</span></span>  
 [<span data-ttu-id="6be27-140">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="6be27-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
