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
ms.openlocfilehash: 140e67417f4fad552f972a93bc8c620b440b2370
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895174"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="75650-102">Interfaz ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="75650-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="75650-103">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="75650-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="75650-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75650-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="75650-105">Methods</span></span>  
  
|<span data-ttu-id="75650-106">Método</span><span class="sxs-lookup"><span data-stu-id="75650-106">Method</span></span>|<span data-ttu-id="75650-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="75650-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75650-108">Método Attach</span><span class="sxs-lookup"><span data-stu-id="75650-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="75650-109">Asocia el depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="75650-110">Método EnumerateAssemblies</span><span class="sxs-lookup"><span data-stu-id="75650-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="75650-111">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="75650-112">Método EnumerateBreakpoints</span><span class="sxs-lookup"><span data-stu-id="75650-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="75650-113">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="75650-114">Método EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="75650-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="75650-115">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="75650-116">GetId (método)</span><span class="sxs-lookup"><span data-stu-id="75650-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="75650-117">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="75650-118">Método GetModuleFromMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="75650-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="75650-119">Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="75650-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="75650-120">Método GetName</span><span class="sxs-lookup"><span data-stu-id="75650-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="75650-121">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="75650-122">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="75650-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="75650-123">Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="75650-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="75650-124">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="75650-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="75650-125">Obtiene el proceso que contiene el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="75650-126">Método IsAttached</span><span class="sxs-lookup"><span data-stu-id="75650-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="75650-127">Determina si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="75650-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75650-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="75650-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75650-129">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="75650-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75650-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75650-130">Requirements</span></span>  
 <span data-ttu-id="75650-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75650-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75650-132">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75650-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75650-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75650-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75650-134">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75650-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75650-135">Consulta también</span><span class="sxs-lookup"><span data-stu-id="75650-135">See also</span></span>

- [<span data-ttu-id="75650-136">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="75650-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
