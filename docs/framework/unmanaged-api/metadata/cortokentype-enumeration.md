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
ms.openlocfilehash: 70b28ab0ca73988093eadb9628142fecd9442948
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705480"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="e30d2-102">CorTokenType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e30d2-102">CorTokenType Enumeration</span></span>

<span data-ttu-id="e30d2-103">Indica el tipo de un token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e30d2-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e30d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e30d2-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e30d2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e30d2-105">Members</span></span>  
  
|<span data-ttu-id="e30d2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e30d2-106">Member</span></span>|<span data-ttu-id="e30d2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e30d2-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="e30d2-108">Un `mdModule` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="e30d2-109">Un `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="e30d2-110">Un `mdTypeDef` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="e30d2-111">Un `mdFieldDef` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="e30d2-112">Un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="e30d2-113">Un `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="e30d2-114">Un `mdInterfaceImpl` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="e30d2-115">Un `mdMemberRef` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="e30d2-116">Un `mdCustomAttribute` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="e30d2-117">Un `mdPermission` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="e30d2-118">Un `mdSignature` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="e30d2-119">Un `mdEvent` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="e30d2-120">Un `mdProperty` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="e30d2-121">Un `mdModuleRef` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="e30d2-122">Un `mdTypeSpec` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="e30d2-123">Un `mdAssembly` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="e30d2-124">Un `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="e30d2-125">Un `mdFile` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="e30d2-126">Un `mdExportedType` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="e30d2-127">Un `mdManifestResource` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="e30d2-128">Un `mdGenericParam` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="e30d2-129">Un `mdMethodSpec` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="e30d2-130">Un `mdGenericParamConstraint` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="e30d2-131">Un `mdString` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="e30d2-132">Un `mdName` token.</span><span class="sxs-lookup"><span data-stu-id="e30d2-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="e30d2-133">No se usa.</span><span class="sxs-lookup"><span data-stu-id="e30d2-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e30d2-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e30d2-134">Remarks</span></span>  

 <span data-ttu-id="e30d2-135">Cada valor es igual al valor del byte superior en el token de metadatos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e30d2-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e30d2-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e30d2-136">Requirements</span></span>  

 <span data-ttu-id="e30d2-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e30d2-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e30d2-138">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="e30d2-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e30d2-139">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e30d2-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e30d2-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e30d2-140">See also</span></span>

- [<span data-ttu-id="e30d2-141">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="e30d2-141">Metadata Enumerations</span></span>](metadata-enumerations.md)
