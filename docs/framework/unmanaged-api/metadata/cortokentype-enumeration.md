---
description: 'Más información sobre: enumeración Cortokentype ('
title: CorTokenType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
ms.openlocfilehash: 954bddccd8fe20be46080f8843bcf754e0cf1bbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678411"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="097ad-103">CorTokenType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="097ad-103">CorTokenType Enumeration</span></span>

<span data-ttu-id="097ad-104">Indica el tipo de un token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="097ad-104">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097ad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="097ad-105">Syntax</span></span>  
  
```cpp  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="097ad-106">Members</span><span class="sxs-lookup"><span data-stu-id="097ad-106">Members</span></span>  
  
|<span data-ttu-id="097ad-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="097ad-107">Member</span></span>|<span data-ttu-id="097ad-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="097ad-108">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="097ad-109">Un `mdModule` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-109">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="097ad-110">Un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-110">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="097ad-111">Un `mdTypeDef` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-111">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="097ad-112">Un `mdFieldDef` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-112">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="097ad-113">Un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-113">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="097ad-114">Un `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-114">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="097ad-115">Un `mdInterfaceImpl` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-115">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="097ad-116">Un `mdMemberRef` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-116">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="097ad-117">Un `mdCustomAttribute` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-117">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="097ad-118">Un `mdPermission` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-118">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="097ad-119">Un `mdSignature` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-119">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="097ad-120">Un `mdEvent` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-120">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="097ad-121">Un `mdProperty` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-121">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="097ad-122">Un `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-122">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="097ad-123">Un `mdTypeSpec` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-123">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="097ad-124">Un `mdAssembly` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-124">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="097ad-125">Un `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-125">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="097ad-126">Un `mdFile` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-126">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="097ad-127">Un `mdExportedType` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-127">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="097ad-128">Un `mdManifestResource` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-128">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="097ad-129">Un `mdGenericParam` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-129">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="097ad-130">Un `mdMethodSpec` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-130">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="097ad-131">Un `mdGenericParamConstraint` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-131">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="097ad-132">Un `mdString` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-132">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="097ad-133">Un `mdName` token.</span><span class="sxs-lookup"><span data-stu-id="097ad-133">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="097ad-134">No se usa.</span><span class="sxs-lookup"><span data-stu-id="097ad-134">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="097ad-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="097ad-135">Remarks</span></span>  

 <span data-ttu-id="097ad-136">Cada valor es igual al valor del byte superior en el token de metadatos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="097ad-136">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="097ad-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="097ad-137">Requirements</span></span>  

 <span data-ttu-id="097ad-138">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="097ad-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="097ad-139">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="097ad-139">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="097ad-140">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="097ad-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097ad-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="097ad-141">See also</span></span>

- [<span data-ttu-id="097ad-142">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="097ad-142">Metadata Enumerations</span></span>](metadata-enumerations.md)
