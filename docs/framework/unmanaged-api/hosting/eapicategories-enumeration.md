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
ms.openlocfilehash: 0fd9409a5157e1013365c94f01631f130a76f54b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131213"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="a9e0f-102">EApiCategories (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a9e0f-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="a9e0f-103">Describe las categorías de funciones de las que el host puede bloquear la ejecución en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9e0f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9e0f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="a9e0f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a9e0f-105">Members</span></span>  
  
|<span data-ttu-id="a9e0f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a9e0f-106">Member</span></span>|<span data-ttu-id="a9e0f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9e0f-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="a9e0f-108">Especifica que se bloquee la ejecución de todas las clases y miembros administrados que están incluidos en otros campos de `EApiCategories` en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="a9e0f-109">Especifica que se bloquee la ejecución de las clases y los miembros administrados que permiten la creación, manipulación y destrucción de procesos externos en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="a9e0f-110">Especifica que las clases administradas y los miembros que permiten la creación, manipulación y destrucción de subprocesos externos no se pueden ejecutar en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="a9e0f-111">Especifica que los tipos y miembros administrados que podrían perder memoria al anularse no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="a9e0f-112">Especifica que no se bloquee ninguna categoría de código administrado en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="a9e0f-113">Especifica que no se puede usar la infraestructura de seguridad de Common Language Runtime (CLR) en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="a9e0f-114">Especifica que las clases administradas y los miembros cuyas funciones pueden afectar al proceso hospedado no pueden ejecutarse en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="a9e0f-115">Especifica que las clases administradas y los miembros cuyas funciones pueden afectar a los subprocesos del proceso hospedado no pueden ejecutarse en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="a9e0f-116">Especifica que se bloquee la ejecución de las clases administradas y los miembros que exponen el estado compartido en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="a9e0f-117">Especifica que Common Language Runtime clases y miembros que permiten que el código de usuario mantenga bloqueos no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="a9e0f-118">Especifica que las clases administradas y los miembros que permiten o requieren la interacción humana no se pueden ejecutar en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9e0f-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9e0f-119">Remarks</span></span>  
 <span data-ttu-id="a9e0f-120">El método [ICLRHostProtectionManager:: setprotectedcategories (](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) toma un parámetro de tipo `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="a9e0f-121">La enumeración `EApiCategories` y el método `SetProtectedCategories` se relacionan directamente con la clase <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> administrada.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a9e0f-122">La clase administrada se usa con la enumeración <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>, cuyos valores se corresponden directamente con los valores `EApiCategories`, para marcar los tipos administrados y los miembros que exponen las funciones correspondientes a las categorías descritas por `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="a9e0f-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9e0f-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9e0f-123">Requirements</span></span>  
 <span data-ttu-id="a9e0f-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9e0f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9e0f-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a9e0f-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9e0f-126">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a9e0f-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9e0f-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9e0f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e0f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9e0f-128">See also</span></span>

- [<span data-ttu-id="a9e0f-129">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9e0f-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="a9e0f-130">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="a9e0f-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
