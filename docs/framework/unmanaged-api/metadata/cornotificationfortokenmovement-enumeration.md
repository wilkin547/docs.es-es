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
ms.openlocfilehash: 96ab659e6ab6cc9601c0e9a1ab511da92905c242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448261"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="4a123-102">CorNotificationForTokenMovement (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4a123-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="4a123-103">Especifica las notificaciones que se enviará al cliente de API de metadatos cuando se produce una reasignación de símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="4a123-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a123-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a123-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="4a123-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4a123-105">Members</span></span>  
  
|<span data-ttu-id="4a123-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4a123-106">Member</span></span>|<span data-ttu-id="4a123-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a123-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="4a123-108">Notificar cuando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, o `mdFieldDef` movimiento de símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="4a123-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="4a123-109">Notificar cuando se mueve ningún símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="4a123-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="4a123-110">No notificar cuando se mueva de símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="4a123-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="4a123-111">Notificar cuando un `mdMethodDef` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="4a123-112">Notificar cuando un `mdMemberRef` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="4a123-113">Notificar cuando un `mdFieldDef` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="4a123-114">Notificar cuando un `mdTypeRef` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="4a123-115">Notificar cuando un `mdTypeDef` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="4a123-116">Notificar cuando un `mdParamDef` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="4a123-117">Notificar cuando un `mdInterfaceImpl` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="4a123-118">Notificar cuando un `mdProperty` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="4a123-119">Notificar cuando un `mdEvent` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="4a123-120">Notificar cuando un `mdSignature` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="4a123-121">Notificar cuando un `mdTypeSpec` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="4a123-122">Notificar cuando un `mdCustomAttribute` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="4a123-123">Notificar cuando un `mdSecurityValue` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="4a123-124">Notificar cuando un `mdPermission` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="4a123-125">Notificar cuando un `mdModuleRef` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="4a123-126">Notificar cuando un `mdNameSpace` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="4a123-127">Notificar cuando un `mdAssemblyRef` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="4a123-128">Notificar cuando un `mdFile` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="4a123-129">Notificar cuando un `mdExportedType` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="4a123-130">Notificar cuando un `mdManifestResource` símbolo (token) se mueve.</span><span class="sxs-lookup"><span data-stu-id="4a123-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a123-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a123-131">Remarks</span></span>  
 <span data-ttu-id="4a123-132">Un símbolo (token) se puede volver a asignar (es decir, mover) durante una combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4a123-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a123-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a123-133">Requirements</span></span>  
 <span data-ttu-id="4a123-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a123-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a123-135">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4a123-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4a123-136">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a123-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a123-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a123-137">See Also</span></span>  
 [<span data-ttu-id="4a123-138">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4a123-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
