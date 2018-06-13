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
ms.openlocfilehash: 9cdb1570b682088e92ff7c7a78d84259d02d8512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444508"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="b4e6c-102">CorCheckDuplicatesFor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b4e6c-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="b4e6c-103">Especifica los tokens de metadatos que se va a comprobar si existen duplicados.</span><span class="sxs-lookup"><span data-stu-id="b4e6c-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4e6c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4e6c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b4e6c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b4e6c-105">Members</span></span>  
  
|<span data-ttu-id="b4e6c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b4e6c-106">Member</span></span>|<span data-ttu-id="b4e6c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4e6c-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="b4e6c-108">Compruebe todos los tokens de metadatos para los duplicados.</span><span class="sxs-lookup"><span data-stu-id="b4e6c-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="b4e6c-109">No usado.</span><span class="sxs-lookup"><span data-stu-id="b4e6c-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="b4e6c-110">No proteja los tokens de metadatos para los duplicados.</span><span class="sxs-lookup"><span data-stu-id="b4e6c-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="b4e6c-111">Compruebe si existen duplicados de `mdTypeDef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="b4e6c-112">Compruebe si existen duplicados de `mdInterfaceImpl` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="b4e6c-113">Compruebe si existen duplicados de `mdMethodDef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="b4e6c-114">Compruebe si existen duplicados de `mdTypeRef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="b4e6c-115">Compruebe si existen duplicados de `mdMemberRef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="b4e6c-116">Compruebe si existen duplicados de `mdCustomAttribute` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="b4e6c-117">Compruebe si existen duplicados de `mdParamDef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="b4e6c-118">Compruebe si existen duplicados de `mdPermission` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="b4e6c-119">Compruebe si existen duplicados de `mdProperty` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="b4e6c-120">Compruebe si existen duplicados de `mdEvent` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="b4e6c-121">Compruebe si existen duplicados de `mdFieldDef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="b4e6c-122">Compruebe si existen duplicados de `mdSignature` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="b4e6c-123">Compruebe si existen duplicados de `mdModuleRef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="b4e6c-124">Compruebe si existen duplicados de `mdTypeSpec` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="b4e6c-125">Compruebe si existen duplicados de `mdImplMap` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="b4e6c-126">Compruebe si existen duplicados de `mdAssemblyRef` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="b4e6c-127">Compruebe si existen duplicados de `mdFile` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="b4e6c-128">Compruebe si existen duplicados de `mdExportedType` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="b4e6c-129">Compruebe si existen duplicados de `mdManifestResource` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="b4e6c-130">Compruebe si existen duplicados de `mdGenericParam` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="b4e6c-131">Compruebe si existen duplicados de `mdMethodSpec` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="b4e6c-132">Compruebe si existen duplicados de `mdGenericParamConstraint` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="b4e6c-133">Compruebe si existen duplicados de `mdAssembly` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="b4e6c-134">Compruebe si existen duplicados de `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, y `mdMethodSpec` símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4e6c-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4e6c-135">Requirements</span></span>  
 <span data-ttu-id="b4e6c-136">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4e6c-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4e6c-137">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b4e6c-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b4e6c-138">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4e6c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e6c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4e6c-139">See Also</span></span>  
 [<span data-ttu-id="b4e6c-140">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b4e6c-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
