---
title: ICorDebugProcess5 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5
helpviewer_keywords: ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0f0a46e18121a222ee62fec207dde938d1e967b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="69516-102">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="69516-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="69516-103">Extiende la interfaz ICorDebugProcess que admitan el acceso al montón administrado, para proporcionar información sobre la recolección de los objetos administrados, y determinar si un depurador carga imágenes desde la caché de imágenes nativas local de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69516-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69516-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="69516-104">Methods</span></span>  
  
|<span data-ttu-id="69516-105">Método</span><span class="sxs-lookup"><span data-stu-id="69516-105">Method</span></span>|<span data-ttu-id="69516-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="69516-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69516-107">EnableNGenPolicy (método)</span><span class="sxs-lookup"><span data-stu-id="69516-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="69516-108">Establece un valor que determina la forma en que una aplicación carga imágenes nativas mientras se ejecuta bajo un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="69516-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="69516-109">EnumerateGCReferences (método)</span><span class="sxs-lookup"><span data-stu-id="69516-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="69516-110">Obtiene un enumerador para todos los objetos que se recolectarán como elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="69516-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="69516-111">EnumerateHandles (método)</span><span class="sxs-lookup"><span data-stu-id="69516-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="69516-112">Obtiene un enumerador para los identificadores de objeto en un proceso.</span><span class="sxs-lookup"><span data-stu-id="69516-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="69516-113">EnumerateHeap (método)</span><span class="sxs-lookup"><span data-stu-id="69516-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="69516-114">Obtiene un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="69516-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="69516-115">EnumerateHeapRegions (método)</span><span class="sxs-lookup"><span data-stu-id="69516-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="69516-116">Obtiene un enumerador para las regiones del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="69516-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="69516-117">Getarraylayout (método)</span><span class="sxs-lookup"><span data-stu-id="69516-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="69516-118">Obtiene información sobre el diseño de una matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="69516-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="69516-119">Getgcheapinformation (método)</span><span class="sxs-lookup"><span data-stu-id="69516-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="69516-120">Obtiene un puntero a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) estructura que contiene información acerca de los objetos que se recolectarán como elementos no utilizados en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="69516-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="69516-121">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="69516-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="69516-122">Obtiene un puntero a un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="69516-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="69516-123">Gettypefields (método)</span><span class="sxs-lookup"><span data-stu-id="69516-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="69516-124">Obtiene un puntero a una matriz que contiene información de campo para un tipo basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="69516-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="69516-125">Gettypefortypeid (método)</span><span class="sxs-lookup"><span data-stu-id="69516-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="69516-126">Obtiene un objeto de tipo que proporciona información sobre un objeto basándose en sus identificadores de tipo.</span><span class="sxs-lookup"><span data-stu-id="69516-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="69516-127">GetTypeId (método)</span><span class="sxs-lookup"><span data-stu-id="69516-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="69516-128">Obtiene el identificador de tipo para el objeto en una dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="69516-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="69516-129">Gettypelayout (método)</span><span class="sxs-lookup"><span data-stu-id="69516-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="69516-130">Obtiene información sobre el diseño de un objeto en la memoria basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="69516-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69516-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69516-131">Remarks</span></span>  
 <span data-ttu-id="69516-132">Esta interfaz extiende lógicamente la ICorDebugProcess, ICorDebugProcess2, y [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span><span class="sxs-lookup"><span data-stu-id="69516-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69516-133">Esta interfaz no admite que se llame de forma remota, desde otro equipo o desde otro proceso.</span><span class="sxs-lookup"><span data-stu-id="69516-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69516-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69516-134">Requirements</span></span>  
 <span data-ttu-id="69516-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69516-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69516-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69516-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69516-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69516-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69516-138">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69516-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69516-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="69516-139">See Also</span></span>  
 [<span data-ttu-id="69516-140">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="69516-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="69516-141">Depuración</span><span class="sxs-lookup"><span data-stu-id="69516-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
