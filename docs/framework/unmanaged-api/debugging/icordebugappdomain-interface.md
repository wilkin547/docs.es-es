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
ms.openlocfilehash: da7c0fb472df89d94fa702a13eff968a4c7e68e3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785041"
---
# <a name="icordebugappdomain-interface"></a><span data-ttu-id="74dbe-102">Interfaz ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="74dbe-102">ICorDebugAppDomain Interface</span></span>

<span data-ttu-id="74dbe-103">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-103">Provides methods for debugging application domains.</span></span> <span data-ttu-id="74dbe-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="74dbe-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74dbe-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="74dbe-105">Methods</span></span>  
  
|<span data-ttu-id="74dbe-106">Método</span><span class="sxs-lookup"><span data-stu-id="74dbe-106">Method</span></span>|<span data-ttu-id="74dbe-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="74dbe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74dbe-108">Attach (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-108">Attach Method</span></span>](icordebugappdomain-attach-method.md)|<span data-ttu-id="74dbe-109">Asocia el depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-109">Attaches the debugger to the application domain.</span></span>|  
|[<span data-ttu-id="74dbe-110">EnumerateAssemblies (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-110">EnumerateAssemblies Method</span></span>](icordebugappdomain-enumerateassemblies-method.md)|<span data-ttu-id="74dbe-111">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-111">Gets an enumerator for the assemblies in the application domain.</span></span>|  
|[<span data-ttu-id="74dbe-112">EnumerateBreakpoints (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-112">EnumerateBreakpoints Method</span></span>](icordebugappdomain-enumeratebreakpoints-method.md)|<span data-ttu-id="74dbe-113">Obtiene un enumerador para todos los puntos de interrupción activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-113">Gets an enumerator for all active breakpoints in the application domain.</span></span>|  
|[<span data-ttu-id="74dbe-114">EnumerateSteppers (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-114">EnumerateSteppers Method</span></span>](icordebugappdomain-enumeratesteppers-method.md)|<span data-ttu-id="74dbe-115">Obtiene un enumerador para todos los steppers activos en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-115">Gets an enumerator for all active steppers in the application domain.</span></span>|  
|[<span data-ttu-id="74dbe-116">GetId (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-116">GetId Method</span></span>](icordebugappdomain-getid-method.md)|<span data-ttu-id="74dbe-117">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-117">Gets the unique ID of the application domain.</span></span>|  
|[<span data-ttu-id="74dbe-118">GetModuleFromMetaDataInterface (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-118">GetModuleFromMetaDataInterface Method</span></span>](icordebugappdomain-getmodulefrommetadatainterface-method.md)|<span data-ttu-id="74dbe-119">Obtiene el objeto ICorDebugModule con la interfaz de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="74dbe-119">Gets the ICorDebugModule object with the given metadata interface.</span></span>|  
|[<span data-ttu-id="74dbe-120">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-120">GetName Method</span></span>](icordebugappdomain-getname-method.md)|<span data-ttu-id="74dbe-121">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-121">Gets the name of the application domain.</span></span>|  
|[<span data-ttu-id="74dbe-122">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-122">GetObject Method</span></span>](icordebugappdomain-getobject-method.md)|<span data-ttu-id="74dbe-123">Obtiene un puntero de interfaz al dominio de aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="74dbe-123">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>|  
|[<span data-ttu-id="74dbe-124">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-124">GetProcess Method</span></span>](icordebugappdomain-getprocess-method.md)|<span data-ttu-id="74dbe-125">Obtiene el proceso que contiene el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-125">Gets the process containing the application domain.</span></span>|  
|[<span data-ttu-id="74dbe-126">IsAttached (método)</span><span class="sxs-lookup"><span data-stu-id="74dbe-126">IsAttached Method</span></span>](icordebugappdomain-isattached-method.md)|<span data-ttu-id="74dbe-127">Determina si el depurador está asociado al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74dbe-127">Determines whether the debugger is attached to the application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74dbe-128">Notas</span><span class="sxs-lookup"><span data-stu-id="74dbe-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74dbe-129">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="74dbe-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74dbe-130">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="74dbe-130">Requirements</span></span>  
 <span data-ttu-id="74dbe-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74dbe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74dbe-132">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74dbe-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74dbe-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74dbe-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74dbe-134">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74dbe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74dbe-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="74dbe-135">See also</span></span>

- [<span data-ttu-id="74dbe-136">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="74dbe-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
