---
description: 'Más información acerca de: ICorDebugAppDomain (interfaz)'
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
ms.openlocfilehash: 5f1ac20a7376a741da2e34de74c810c0f45e8293
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754205"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="d5db8-103">Interfaz ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="d5db8-103">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="d5db8-104">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-104">Provides methods for debugging application domains.</span></span> <span data-ttu-id="d5db8-105">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="d5db8-105">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5db8-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="d5db8-106">Methods</span></span>  
  
|<span data-ttu-id="d5db8-107">Método</span><span class="sxs-lookup"><span data-stu-id="d5db8-107">Method</span></span>|<span data-ttu-id="d5db8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5db8-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5db8-109">Método Attach</span><span class="sxs-lookup"><span data-stu-id="d5db8-109">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="d5db8-110">Asocia el depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-110">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="d5db8-111">Método EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="d5db8-111">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="d5db8-112">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-112">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="d5db8-113">Método EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="d5db8-113">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="d5db8-114">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-114">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="d5db8-115">Método EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="d5db8-115">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="d5db8-116">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-116">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="d5db8-117">GetId (método)</span><span class="sxs-lookup"><span data-stu-id="d5db8-117">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="d5db8-118">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-118">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="d5db8-119">Método GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="d5db8-119">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="d5db8-120">Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="d5db8-120">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="d5db8-121">Método GetName</span><span class="sxs-lookup"><span data-stu-id="d5db8-121">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="d5db8-122">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-122">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="d5db8-123">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="d5db8-123">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="d5db8-124">Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d5db8-124">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="d5db8-125">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="d5db8-125">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="d5db8-126">Obtiene el proceso que contiene el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-126">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="d5db8-127">Método IsAttached</span><span class="sxs-lookup"><span data-stu-id="d5db8-127">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="d5db8-128">Determina si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5db8-128">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5db8-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d5db8-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5db8-130">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d5db8-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5db8-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5db8-131">Requirements</span></span>  

 <span data-ttu-id="d5db8-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5db8-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5db8-133">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5db8-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5db8-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5db8-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5db8-135">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5db8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5db8-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5db8-136">See also</span></span>

- [<span data-ttu-id="d5db8-137">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d5db8-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
