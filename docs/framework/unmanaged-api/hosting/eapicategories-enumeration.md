---
title: EApiCategories (Enumeración)
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50aa116fc1f5377254a8a6a128d0240c57cb52b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597572"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="2aad7-102">EApiCategories (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2aad7-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="2aad7-103">Describe las categorías de funciones que puede bloquear el host que se ejecutan en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aad7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2aad7-104">Syntax</span></span>  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a><span data-ttu-id="2aad7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2aad7-105">Members</span></span>  
  
|<span data-ttu-id="2aad7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2aad7-106">Member</span></span>|<span data-ttu-id="2aad7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2aad7-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="2aad7-108">Especifica que todos los administrados de las clases y miembros que están cubiertos por otro `EApiCategories` campos podrá ejecutarse en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="2aad7-109">Especifica que las clases administradas y los miembros que permiten la creación, manipulación y destrucción de procesos externos podrá ejecutarse en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="2aad7-110">Especifica que las clases administradas y los miembros que permiten la creación, manipulación y destrucción de subprocesos externos podrá ejecutarse en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="2aad7-111">Especifica que se bloquean los tipos administrados y miembros que pueden provocar pérdidas de memoria en la anulación se ejecuten en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="2aad7-112">Especifica que no hay categorías de código administrado se bloqueó su ejecución en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="2aad7-113">Especifica que debe bloquearse la infraestructura de seguridad de common language runtime (CLR) usando código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="2aad7-114">Especifica que las clases administradas y miembros cuyas características pueden afectar al proceso hospedado podrá ejecutarse en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="2aad7-115">Especifica que las clases administradas y miembros cuyas características pueden afectar a los subprocesos del proceso hospedado podrá ejecutarse en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="2aad7-116">Especifica que las clases administradas y los miembros que exponen el estado compartido podrá ejecutarse en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="2aad7-117">Especifica que los miembros que permitir que el código de usuario mantener los bloqueos y las clases en tiempo de ejecución de lenguaje comunes podrá ejecutarse en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="2aad7-118">Especifica que las clases administradas y los miembros que permiten o requieren la interacción humana podrá ejecutarse en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2aad7-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aad7-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2aad7-119">Remarks</span></span>  
 <span data-ttu-id="2aad7-120">El [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) método toma un parámetro de tipo `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="2aad7-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="2aad7-121">El `EApiCategories` enumeración y el `SetProtectedCategories` método están relacionados directamente a los recursos administrados <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="2aad7-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="2aad7-122">Se usa la clase administrada con el <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeración, cuyos valores se corresponden directamente con el `EApiCategories` valores para marcar los tipos administrados y miembros que exponen funciones correspondientes a las categorías descritas por `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="2aad7-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aad7-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2aad7-123">Requirements</span></span>  
 <span data-ttu-id="2aad7-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aad7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aad7-125">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2aad7-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2aad7-126">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2aad7-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2aad7-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aad7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aad7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aad7-128">See also</span></span>
- [<span data-ttu-id="2aad7-129">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2aad7-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="2aad7-130">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="2aad7-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
