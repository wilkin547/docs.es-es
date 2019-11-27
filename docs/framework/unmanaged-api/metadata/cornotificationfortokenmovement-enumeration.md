---
title: CorNotificationForTokenMovement (Enumeración)
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450149"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="5e7cd-102">CorNotificationForTokenMovement (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5e7cd-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="5e7cd-103">Especifica las notificaciones que se enviarán al cliente de la API de metadatos cuando se produzca una reasignación de token.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e7cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e7cd-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="5e7cd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5e7cd-105">Members</span></span>  
  
|<span data-ttu-id="5e7cd-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5e7cd-106">Member</span></span>|<span data-ttu-id="5e7cd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e7cd-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="5e7cd-108">Notificar cuando se muevan los tokens `mdTypeRef`, `mdMethodDef`, `mdMemberRef`o `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="5e7cd-109">Notificar cuando se mueva cualquier token.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="5e7cd-110">No notifique cuando se muevan los tokens.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="5e7cd-111">Notificar cuando se mueve un token de `mdMethodDef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="5e7cd-112">Notificar cuando se mueve un token de `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="5e7cd-113">Notificar cuando se mueve un token de `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="5e7cd-114">Notificar cuando se mueve un token de `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="5e7cd-115">Notificar cuando se mueve un token de `mdTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="5e7cd-116">Notificar cuando se mueve un token de `mdParamDef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="5e7cd-117">Notificar cuando se mueve un token de `mdInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="5e7cd-118">Notificar cuando se mueve un token de `mdProperty`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="5e7cd-119">Notificar cuando se mueve un token de `mdEvent`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="5e7cd-120">Notificar cuando se mueve un token de `mdSignature`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="5e7cd-121">Notificar cuando se mueve un token de `mdTypeSpec`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="5e7cd-122">Notificar cuando se mueve un token de `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="5e7cd-123">Notificar cuando se mueve un token de `mdSecurityValue`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="5e7cd-124">Notificar cuando se mueve un token de `mdPermission`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="5e7cd-125">Notificar cuando se mueve un token de `mdModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="5e7cd-126">Notificar cuando se mueve un token de `mdNameSpace`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="5e7cd-127">Notificar cuando se mueve un token de `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="5e7cd-128">Notificar cuando se mueve un token de `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="5e7cd-129">Notificar cuando se mueve un token de `mdExportedType`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="5e7cd-130">Notificar cuando se mueve un token de `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e7cd-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e7cd-131">Remarks</span></span>  
 <span data-ttu-id="5e7cd-132">Un token puede volver a asignarse (es decir, moverse) durante una fusión mediante combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5e7cd-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e7cd-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e7cd-133">Requirements</span></span>  
 <span data-ttu-id="5e7cd-134">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e7cd-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e7cd-135">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="5e7cd-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5e7cd-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e7cd-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7cd-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e7cd-137">See also</span></span>

- [<span data-ttu-id="5e7cd-138">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="5e7cd-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
