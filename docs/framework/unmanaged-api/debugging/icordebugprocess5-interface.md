---
title: ICorDebugProcess5 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
ms.openlocfilehash: 263124db75abdc058d26ffb606a13fc711aed8bf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792299"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="b094b-102">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b094b-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="b094b-103">Extiende la interfaz ICorDebugProcess para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la memoria caché de imágenes nativas local de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b094b-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b094b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b094b-104">Methods</span></span>  
  
|<span data-ttu-id="b094b-105">Método</span><span class="sxs-lookup"><span data-stu-id="b094b-105">Method</span></span>|<span data-ttu-id="b094b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b094b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b094b-107">EnableNGenPolicy (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-107">EnableNGenPolicy Method</span></span>](icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="b094b-108">Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="b094b-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="b094b-109">EnumerateGCReferences (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-109">EnumerateGCReferences Method</span></span>](icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="b094b-110">Obtiene un enumerador para todos los objetos que se van a recopilar de elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="b094b-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="b094b-111">EnumerateHandles (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-111">EnumerateHandles Method</span></span>](icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="b094b-112">Obtiene un enumerador para los identificadores de objetos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="b094b-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="b094b-113">EnumerateHeap (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-113">EnumerateHeap Method</span></span>](icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="b094b-114">Obtiene un enumerador para los objetos en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b094b-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="b094b-115">EnumerateHeapRegions (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-115">EnumerateHeapRegions Method</span></span>](icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="b094b-116">Obtiene un enumerador para las regiones del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b094b-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="b094b-117">GetArrayLayout (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-117">GetArrayLayout Method</span></span>](icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="b094b-118">Obtiene información sobre el diseño de una matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b094b-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="b094b-119">GetGCHeapInformation (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-119">GetGCHeapInformation Method</span></span>](icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="b094b-120">Obtiene un puntero a una estructura de [COR_HEAPINFO](cor-heapinfo-structure.md) que contiene información sobre los objetos que se van a recopilar en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b094b-120">Gets a pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="b094b-121">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-121">GetObject Method</span></span>](icordebugprocess5-getobject-method.md)|<span data-ttu-id="b094b-122">Obtiene un puntero a un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b094b-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="b094b-123">GetTypeFields (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-123">GetTypeFields Method</span></span>](icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="b094b-124">Obtiene un puntero a una matriz que contiene información de campo para un tipo basado en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="b094b-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="b094b-125">GetTypeForTypeID (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-125">GetTypeForTypeID Method</span></span>](icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="b094b-126">Obtiene un objeto de tipo que proporciona información sobre un objeto basándose en sus identificadores de tipo.</span><span class="sxs-lookup"><span data-stu-id="b094b-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="b094b-127">GetTypeID (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-127">GetTypeID Method</span></span>](icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="b094b-128">Obtiene el identificador de tipo para el objeto en una dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="b094b-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="b094b-129">GetTypeLayout (método)</span><span class="sxs-lookup"><span data-stu-id="b094b-129">GetTypeLayout Method</span></span>](icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="b094b-130">Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="b094b-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b094b-131">Notas</span><span class="sxs-lookup"><span data-stu-id="b094b-131">Remarks</span></span>  
 <span data-ttu-id="b094b-132">Esta interfaz extiende lógicamente las interfaces ICorDebugProcess, ICorDebugProcess2 y [ICorDebugProcess3 (](icordebugprocess3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b094b-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b094b-133">Esta interfaz no admite la llamada remota, ya sea desde otro equipo o desde otro proceso.</span><span class="sxs-lookup"><span data-stu-id="b094b-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b094b-134">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b094b-134">Requirements</span></span>  
 <span data-ttu-id="b094b-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b094b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b094b-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b094b-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b094b-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b094b-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b094b-138">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b094b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b094b-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b094b-139">See also</span></span>

- [<span data-ttu-id="b094b-140">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b094b-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b094b-141">Depuración</span><span class="sxs-lookup"><span data-stu-id="b094b-141">Debugging</span></span>](index.md)
