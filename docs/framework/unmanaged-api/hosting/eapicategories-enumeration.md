---
title: "EApiCategories (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EApiCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: EApiCategories
helpviewer_keywords: EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 630a3048072ed7b19b3250e75aca3b31e4dd7df7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="578e1-102">EApiCategories (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="578e1-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="578e1-103">Describe las categorías de funciones cuya ejecución en código de confianza parcial puede bloquear el host.</span><span class="sxs-lookup"><span data-stu-id="578e1-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="578e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="578e1-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="578e1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="578e1-105">Members</span></span>  
  
|<span data-ttu-id="578e1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="578e1-106">Member</span></span>|<span data-ttu-id="578e1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="578e1-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="578e1-108">Especifica que todas las clases administran y los miembros que están cubiertos por otro `EApiCategories` campos podrá ejecutarse en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="578e1-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="578e1-109">Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y miembros que permiten la creación, manipulación y destrucción de procesos externos.</span><span class="sxs-lookup"><span data-stu-id="578e1-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="578e1-110">Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros que permiten la creación, manipulación y destrucción de subprocesos externos.</span><span class="sxs-lookup"><span data-stu-id="578e1-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="578e1-111">Especifica que debe bloquearse la ejecución en el código de confianza parcial de tipos administrados y miembros que pueden provocar pérdidas de memoria en la anulación.</span><span class="sxs-lookup"><span data-stu-id="578e1-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="578e1-112">Especifica que no hay categorías de código administrado se bloqueó su ejecución en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="578e1-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="578e1-113">Especifica que la infraestructura de seguridad de common language runtime (CLR) se bloquee sean usadas por código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="578e1-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="578e1-114">Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros cuyas funciones pueden afectar al proceso hospedado.</span><span class="sxs-lookup"><span data-stu-id="578e1-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="578e1-115">Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros cuyas funciones pueden afectar a subprocesos del proceso hospedado.</span><span class="sxs-lookup"><span data-stu-id="578e1-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="578e1-116">Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros que exponen el estado compartido.</span><span class="sxs-lookup"><span data-stu-id="578e1-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="578e1-117">Especifica que las clases en tiempo de ejecución de idioma y miembros que permitir que el código de usuario se mantienen bloqueos comunes podrá ejecutarse en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="578e1-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="578e1-118">Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros que permiten o requieren interacción humana.</span><span class="sxs-lookup"><span data-stu-id="578e1-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="578e1-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="578e1-119">Remarks</span></span>  
 <span data-ttu-id="578e1-120">El [ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) método toma un parámetro de tipo `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="578e1-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="578e1-121">El `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados a los recursos administrados <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="578e1-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="578e1-122">Se utiliza la clase administrada con el <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeración, cuyos valores se corresponden directamente a la `EApiCategories` valores, para marcar tipos administrados y miembros que exponen funciones correspondientes a las categorías descritas por `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="578e1-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="578e1-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="578e1-123">Requirements</span></span>  
 <span data-ttu-id="578e1-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="578e1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="578e1-125">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="578e1-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="578e1-126">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="578e1-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="578e1-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="578e1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="578e1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="578e1-128">See Also</span></span>  
 [<span data-ttu-id="578e1-129">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="578e1-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="578e1-130">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="578e1-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
