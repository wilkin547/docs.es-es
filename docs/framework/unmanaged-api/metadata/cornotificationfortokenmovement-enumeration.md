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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15c5e8b34f2748868611bd7dc47ef73c491b1338
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189435"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="aa319-102">CorNotificationForTokenMovement (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="aa319-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="aa319-103">Especifica las notificaciones que se enviarán al cliente de API de metadatos cuando se produce una reasignación del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa319-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa319-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="aa319-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="aa319-105">Members</span></span>  
  
|<span data-ttu-id="aa319-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="aa319-106">Member</span></span>|<span data-ttu-id="aa319-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa319-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="aa319-108">Notificar cuando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, o `mdFieldDef` movimiento de tokens.</span><span class="sxs-lookup"><span data-stu-id="aa319-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="aa319-109">Notificar cuando se mueve ningún token.</span><span class="sxs-lookup"><span data-stu-id="aa319-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="aa319-110">No informan de los tokens de mover.</span><span class="sxs-lookup"><span data-stu-id="aa319-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="aa319-111">Notificar cuando una `mdMethodDef` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="aa319-112">Notificar cuando una `mdMemberRef` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="aa319-113">Notificar cuando una `mdFieldDef` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="aa319-114">Notificar cuando una `mdTypeRef` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="aa319-115">Notificar cuando una `mdTypeDef` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="aa319-116">Notificar cuando una `mdParamDef` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="aa319-117">Notificar cuando una `mdInterfaceImpl` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="aa319-118">Notificar cuando una `mdProperty` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="aa319-119">Notificar cuando una `mdEvent` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="aa319-120">Notificar cuando una `mdSignature` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="aa319-121">Notificar cuando una `mdTypeSpec` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="aa319-122">Notificar cuando una `mdCustomAttribute` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="aa319-123">Notificar cuando una `mdSecurityValue` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="aa319-124">Notificar cuando una `mdPermission` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="aa319-125">Notificar cuando una `mdModuleRef` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="aa319-126">Notificar cuando una `mdNameSpace` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="aa319-127">Notificar cuando una `mdAssemblyRef` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="aa319-128">Notificar cuando una `mdFile` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="aa319-129">Notificar cuando una `mdExportedType` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="aa319-130">Notificar cuando una `mdManifestResource` movimientos del token.</span><span class="sxs-lookup"><span data-stu-id="aa319-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa319-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa319-131">Remarks</span></span>  
 <span data-ttu-id="aa319-132">Un token se puede volver a asignar (es decir, mover) durante una combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="aa319-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa319-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa319-133">Requirements</span></span>  
 <span data-ttu-id="aa319-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa319-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa319-135">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="aa319-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="aa319-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa319-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa319-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa319-137">See also</span></span>

- [<span data-ttu-id="aa319-138">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="aa319-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
