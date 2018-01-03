---
title: ICorDebugAppDomain Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain
helpviewer_keywords: ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aab18cb1d29931a58e64561f23d91ee4eb3a4278
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain-interface1"></a><span data-ttu-id="4f382-102">ICorDebugAppDomain Interfaz1</span><span class="sxs-lookup"><span data-stu-id="4f382-102">ICorDebugAppDomain Interface1</span></span>
<span data-ttu-id="4f382-103">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="4f382-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="4f382-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f382-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4f382-105">Methods</span></span>  
  
|<span data-ttu-id="4f382-106">Método</span><span class="sxs-lookup"><span data-stu-id="4f382-106">Method</span></span>|<span data-ttu-id="4f382-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f382-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f382-108">Attach (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="4f382-109">Asocia al depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="4f382-110">EnumerateAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="4f382-111">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="4f382-112">EnumerateBreakpoints (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="4f382-113">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="4f382-114">EnumerateSteppers (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="4f382-115">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="4f382-116">GetId (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="4f382-117">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="4f382-118">GetModuleFromMetaDataInterface (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="4f382-119">Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="4f382-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="4f382-120">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="4f382-121">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="4f382-122">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="4f382-123">Obtiene un puntero de interfaz al dominio de aplicación de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4f382-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="4f382-124">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="4f382-125">Obtiene el proceso que contiene el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="4f382-126">IsAttached (método)</span><span class="sxs-lookup"><span data-stu-id="4f382-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="4f382-127">Determina si el depurador se adjunta al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f382-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f382-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f382-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f382-129">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4f382-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f382-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f382-130">Requirements</span></span>  
 <span data-ttu-id="4f382-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f382-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f382-132">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f382-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f382-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f382-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f382-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f382-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f382-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f382-135">See Also</span></span>  
 [<span data-ttu-id="4f382-136">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4f382-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
