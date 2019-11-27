---
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
ms.openlocfilehash: 74807a678b5c0c2738f33fe552f6462af93ca1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436466"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="456b3-102">CorTokenType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="456b3-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="456b3-103">Indica el tipo de un token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="456b3-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="456b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="456b3-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="456b3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="456b3-105">Members</span></span>  
  
|<span data-ttu-id="456b3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="456b3-106">Member</span></span>|<span data-ttu-id="456b3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="456b3-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="456b3-108">Un token de `mdModule`.</span><span class="sxs-lookup"><span data-stu-id="456b3-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="456b3-109">Un token de `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="456b3-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="456b3-110">Un token de `mdTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="456b3-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="456b3-111">Un token de `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="456b3-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="456b3-112">Un token de `mdMethodDef`.</span><span class="sxs-lookup"><span data-stu-id="456b3-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="456b3-113">Un token de `mdParamDef`.</span><span class="sxs-lookup"><span data-stu-id="456b3-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="456b3-114">Un token de `mdInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="456b3-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="456b3-115">Un token de `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="456b3-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="456b3-116">Un token de `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="456b3-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="456b3-117">Un token de `mdPermission`.</span><span class="sxs-lookup"><span data-stu-id="456b3-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="456b3-118">Un token de `mdSignature`.</span><span class="sxs-lookup"><span data-stu-id="456b3-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="456b3-119">Un token de `mdEvent`.</span><span class="sxs-lookup"><span data-stu-id="456b3-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="456b3-120">Un token de `mdProperty`.</span><span class="sxs-lookup"><span data-stu-id="456b3-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="456b3-121">Un token de `mdModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="456b3-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="456b3-122">Un token de `mdTypeSpec`.</span><span class="sxs-lookup"><span data-stu-id="456b3-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="456b3-123">Un token de `mdAssembly`.</span><span class="sxs-lookup"><span data-stu-id="456b3-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="456b3-124">Un token de `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="456b3-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="456b3-125">Un token de `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="456b3-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="456b3-126">Un token de `mdExportedType`.</span><span class="sxs-lookup"><span data-stu-id="456b3-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="456b3-127">Un token de `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="456b3-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="456b3-128">Un token de `mdGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="456b3-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="456b3-129">Un token de `mdMethodSpec`.</span><span class="sxs-lookup"><span data-stu-id="456b3-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="456b3-130">Un token de `mdGenericParamConstraint`.</span><span class="sxs-lookup"><span data-stu-id="456b3-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="456b3-131">Un token de `mdString`.</span><span class="sxs-lookup"><span data-stu-id="456b3-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="456b3-132">Un token de `mdName`.</span><span class="sxs-lookup"><span data-stu-id="456b3-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="456b3-133">No usado.</span><span class="sxs-lookup"><span data-stu-id="456b3-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="456b3-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="456b3-134">Remarks</span></span>  
 <span data-ttu-id="456b3-135">Cada valor es igual al valor del byte superior en el token de metadatos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="456b3-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="456b3-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="456b3-136">Requirements</span></span>  
 <span data-ttu-id="456b3-137">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="456b3-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="456b3-138">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="456b3-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="456b3-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="456b3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456b3-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="456b3-140">See also</span></span>

- [<span data-ttu-id="456b3-141">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="456b3-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
