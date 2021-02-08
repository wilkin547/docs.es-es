---
description: 'Más información sobre: enumeración Cornotificationfortokenmovement ('
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
ms.openlocfilehash: 1975598b756499c9c0b017bf7eba9a134af5185f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784319"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="37476-103">CorNotificationForTokenMovement (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="37476-103">CorNotificationForTokenMovement Enumeration</span></span>

<span data-ttu-id="37476-104">Especifica las notificaciones que se enviarán al cliente de la API de metadatos cuando se produzca una reasignación de token.</span><span class="sxs-lookup"><span data-stu-id="37476-104">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37476-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37476-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="37476-106">Members</span><span class="sxs-lookup"><span data-stu-id="37476-106">Members</span></span>  
  
|<span data-ttu-id="37476-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="37476-107">Member</span></span>|<span data-ttu-id="37476-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="37476-108">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="37476-109">Notificar cuándo se `mdTypeRef` `mdMethodDef` `mdMemberRef` `mdFieldDef` mueven los tokens,, o.</span><span class="sxs-lookup"><span data-stu-id="37476-109">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="37476-110">Notificar cuando se mueva cualquier token.</span><span class="sxs-lookup"><span data-stu-id="37476-110">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="37476-111">No notifique cuando se muevan los tokens.</span><span class="sxs-lookup"><span data-stu-id="37476-111">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="37476-112">Notificar cuando `mdMethodDef` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-112">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="37476-113">Notificar cuando `mdMemberRef` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-113">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="37476-114">Notificar cuando `mdFieldDef` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-114">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="37476-115">Notificar cuando `mdTypeRef` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-115">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="37476-116">Notificar cuando `mdTypeDef` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-116">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="37476-117">Notificar cuando `mdParamDef` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-117">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="37476-118">Notificar cuando `mdInterfaceImpl` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-118">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="37476-119">Notificar cuando `mdProperty` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-119">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="37476-120">Notificar cuando `mdEvent` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-120">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="37476-121">Notificar cuando `mdSignature` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-121">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="37476-122">Notificar cuando `mdTypeSpec` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-122">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="37476-123">Notificar cuando `mdCustomAttribute` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-123">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="37476-124">Notificar cuando `mdSecurityValue` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-124">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="37476-125">Notificar cuando `mdPermission` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-125">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="37476-126">Notificar cuando `mdModuleRef` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-126">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="37476-127">Notificar cuando `mdNameSpace` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-127">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="37476-128">Notificar cuando `mdAssemblyRef` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-128">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="37476-129">Notificar cuando `mdFile` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-129">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="37476-130">Notificar cuando `mdExportedType` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-130">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="37476-131">Notificar cuando `mdManifestResource` se mueva un token.</span><span class="sxs-lookup"><span data-stu-id="37476-131">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37476-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37476-132">Remarks</span></span>  

 <span data-ttu-id="37476-133">Un token puede volver a asignarse (es decir, moverse) durante una fusión mediante combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="37476-133">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37476-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37476-134">Requirements</span></span>  

 <span data-ttu-id="37476-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37476-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37476-136">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="37476-136">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="37476-137">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37476-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37476-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="37476-138">See also</span></span>

- [<span data-ttu-id="37476-139">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="37476-139">Metadata Enumerations</span></span>](metadata-enumerations.md)
