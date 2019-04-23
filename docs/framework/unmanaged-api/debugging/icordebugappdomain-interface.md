---
title: Interfaz ICorDebugAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40619aa40f9924d94c82541eb8d30790e774a675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141510"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="23bbd-102">Interfaz ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="23bbd-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="23bbd-103">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="23bbd-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="23bbd-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23bbd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="23bbd-105">Methods</span></span>  
  
|<span data-ttu-id="23bbd-106">Método</span><span class="sxs-lookup"><span data-stu-id="23bbd-106">Method</span></span>|<span data-ttu-id="23bbd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="23bbd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23bbd-108">Attach (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="23bbd-109">Asocia al depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="23bbd-110">EnumerateAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="23bbd-111">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="23bbd-112">EnumerateBreakpoints (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="23bbd-113">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="23bbd-114">EnumerateSteppers (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="23bbd-115">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="23bbd-116">GetId (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="23bbd-117">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="23bbd-118">GetModuleFromMetaDataInterface (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="23bbd-119">Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="23bbd-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="23bbd-120">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="23bbd-121">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="23bbd-122">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="23bbd-123">Obtiene un puntero de interfaz para el dominio de aplicación de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="23bbd-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="23bbd-124">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="23bbd-125">Obtiene el proceso que contiene el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="23bbd-126">IsAttached (método)</span><span class="sxs-lookup"><span data-stu-id="23bbd-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="23bbd-127">Determina si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="23bbd-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23bbd-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23bbd-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23bbd-129">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="23bbd-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23bbd-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23bbd-130">Requirements</span></span>  
 <span data-ttu-id="23bbd-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23bbd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23bbd-132">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23bbd-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23bbd-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23bbd-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23bbd-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23bbd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23bbd-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="23bbd-135">See also</span></span>

- [<span data-ttu-id="23bbd-136">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="23bbd-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
