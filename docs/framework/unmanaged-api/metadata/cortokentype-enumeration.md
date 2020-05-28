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
ms.openlocfilehash: 629e18b6cd2fd7910804ecc608a45d2406dddea1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007499"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="b391c-102">CorTokenType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b391c-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="b391c-103">Indica el tipo de un token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b391c-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b391c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b391c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b391c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b391c-105">Members</span></span>  
  
|<span data-ttu-id="b391c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b391c-106">Member</span></span>|<span data-ttu-id="b391c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b391c-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="b391c-108">Un `mdModule` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="b391c-109">Un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="b391c-110">Un `mdTypeDef` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="b391c-111">Un `mdFieldDef` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="b391c-112">Un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="b391c-113">Un `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="b391c-114">Un `mdInterfaceImpl` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="b391c-115">Un `mdMemberRef` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="b391c-116">Un `mdCustomAttribute` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="b391c-117">Un `mdPermission` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="b391c-118">Un `mdSignature` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="b391c-119">Un `mdEvent` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="b391c-120">Un `mdProperty` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="b391c-121">Un `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="b391c-122">Un `mdTypeSpec` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="b391c-123">Un `mdAssembly` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="b391c-124">Un `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="b391c-125">Un `mdFile` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="b391c-126">Un `mdExportedType` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="b391c-127">Un `mdManifestResource` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="b391c-128">Un `mdGenericParam` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="b391c-129">Un `mdMethodSpec` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="b391c-130">Un `mdGenericParamConstraint` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="b391c-131">Un `mdString` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="b391c-132">Un `mdName` token.</span><span class="sxs-lookup"><span data-stu-id="b391c-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="b391c-133">No se usa.</span><span class="sxs-lookup"><span data-stu-id="b391c-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b391c-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b391c-134">Remarks</span></span>  
 <span data-ttu-id="b391c-135">Cada valor es igual al valor del byte superior en el token de metadatos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b391c-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b391c-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b391c-136">Requirements</span></span>  
 <span data-ttu-id="b391c-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b391c-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b391c-138">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="b391c-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b391c-139">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b391c-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b391c-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b391c-140">See also</span></span>

- [<span data-ttu-id="b391c-141">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b391c-141">Metadata Enumerations</span></span>](metadata-enumerations.md)
