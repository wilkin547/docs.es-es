---
description: 'Más información sobre: enumeración EApiCategories'
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
ms.openlocfilehash: 58a7d4fa4d0c965bf9158ad6713185782d4ae94a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785632"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="dd8d5-103">EApiCategories (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="dd8d5-103">EApiCategories Enumeration</span></span>

<span data-ttu-id="dd8d5-104">Describe las categorías de funciones de las que el host puede bloquear la ejecución en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-104">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd8d5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd8d5-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="dd8d5-106">Members</span><span class="sxs-lookup"><span data-stu-id="dd8d5-106">Members</span></span>  
  
|<span data-ttu-id="dd8d5-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="dd8d5-107">Member</span></span>|<span data-ttu-id="dd8d5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd8d5-108">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="dd8d5-109">Especifica que se bloquee la ejecución de todas las clases y miembros administrados que están incluidos `EApiCategories` en otros campos en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-109">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="dd8d5-110">Especifica que se bloquee la ejecución de las clases y los miembros administrados que permiten la creación, manipulación y destrucción de procesos externos en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="dd8d5-111">Especifica que las clases administradas y los miembros que permiten la creación, manipulación y destrucción de subprocesos externos no se pueden ejecutar en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-111">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="dd8d5-112">Especifica que los tipos y miembros administrados que podrían perder memoria al anularse no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-112">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="dd8d5-113">Especifica que no se bloquee ninguna categoría de código administrado en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-113">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="dd8d5-114">Especifica que no se puede usar la infraestructura de seguridad de Common Language Runtime (CLR) en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-114">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="dd8d5-115">Especifica que las clases administradas y los miembros cuyas funciones pueden afectar al proceso hospedado no pueden ejecutarse en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-115">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="dd8d5-116">Especifica que las clases administradas y los miembros cuyas funciones pueden afectar a los subprocesos del proceso hospedado no pueden ejecutarse en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-116">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="dd8d5-117">Especifica que se bloquee la ejecución de las clases administradas y los miembros que exponen el estado compartido en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-117">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="dd8d5-118">Especifica que Common Language Runtime clases y miembros que permiten que el código de usuario mantenga bloqueos no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-118">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="dd8d5-119">Especifica que las clases administradas y los miembros que permiten o requieren la interacción humana no se pueden ejecutar en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-119">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd8d5-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dd8d5-120">Remarks</span></span>  

 <span data-ttu-id="dd8d5-121">El método [ICLRHostProtectionManager:: setprotectedcategories (](iclrhostprotectionmanager-setprotectedcategories-method.md) toma un parámetro de tipo `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="dd8d5-121">The [ICLRHostProtectionManager::SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="dd8d5-122">La `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados con la <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> clase administrada.</span><span class="sxs-lookup"><span data-stu-id="dd8d5-122">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="dd8d5-123">La clase administrada se usa con la <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeración, cuyos valores se corresponden directamente con los `EApiCategories` valores, para marcar los tipos administrados y los miembros que exponen las funciones correspondientes a las categorías descritas por `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="dd8d5-123">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd8d5-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd8d5-124">Requirements</span></span>  

 <span data-ttu-id="dd8d5-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd8d5-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd8d5-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dd8d5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd8d5-127">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd8d5-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd8d5-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd8d5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd8d5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd8d5-129">See also</span></span>

- [<span data-ttu-id="dd8d5-130">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd8d5-130">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="dd8d5-131">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="dd8d5-131">Hosting Enumerations</span></span>](hosting-enumerations.md)
