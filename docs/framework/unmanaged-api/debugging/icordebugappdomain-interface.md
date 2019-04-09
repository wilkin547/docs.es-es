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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141510"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="3e30a-102">Interfaz ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="3e30a-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="3e30a-103">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="3e30a-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="3e30a-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e30a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3e30a-105">Methods</span></span>  
  
|<span data-ttu-id="3e30a-106">Método</span><span class="sxs-lookup"><span data-stu-id="3e30a-106">Method</span></span>|<span data-ttu-id="3e30a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e30a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e30a-108">Método Attach</span><span class="sxs-lookup"><span data-stu-id="3e30a-108">Attach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|<span data-ttu-id="3e30a-109">Asocia al depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="3e30a-110">Método EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="3e30a-110">EnumerateAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="3e30a-111">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="3e30a-112">Método EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="3e30a-112">EnumerateBreakpoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="3e30a-113">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="3e30a-114">Método EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="3e30a-114">EnumerateSteppers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="3e30a-115">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="3e30a-116">Método GetId</span><span class="sxs-lookup"><span data-stu-id="3e30a-116">GetId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|<span data-ttu-id="3e30a-117">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="3e30a-118">Método GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="3e30a-118">GetModuleFromMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="3e30a-119">Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="3e30a-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="3e30a-120">Método GetName</span><span class="sxs-lookup"><span data-stu-id="3e30a-120">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|<span data-ttu-id="3e30a-121">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="3e30a-122">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="3e30a-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|<span data-ttu-id="3e30a-123">Obtiene un puntero de interfaz para el dominio de aplicación de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3e30a-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="3e30a-124">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="3e30a-124">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|<span data-ttu-id="3e30a-125">Obtiene el proceso que contiene el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="3e30a-126">Método IsAttached</span><span class="sxs-lookup"><span data-stu-id="3e30a-126">IsAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|<span data-ttu-id="3e30a-127">Determina si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3e30a-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e30a-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e30a-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e30a-129">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3e30a-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e30a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e30a-130">Requirements</span></span>  
 <span data-ttu-id="3e30a-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e30a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e30a-132">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e30a-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e30a-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e30a-133">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3e30a-134">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3e30a-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e30a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e30a-135">See also</span></span>

- [<span data-ttu-id="3e30a-136">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3e30a-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
