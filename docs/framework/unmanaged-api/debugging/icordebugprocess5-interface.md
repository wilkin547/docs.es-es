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
ms.openlocfilehash: cef69ac7e3572b67dd676ce8408e4210d93accf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717583"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="530f4-102">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="530f4-102">ICorDebugProcess5 Interface</span></span>

<span data-ttu-id="530f4-103">Extiende la interfaz ICorDebugProcess para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la memoria caché de imágenes nativas local de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="530f4-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="530f4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="530f4-104">Methods</span></span>  
  
|<span data-ttu-id="530f4-105">Método</span><span class="sxs-lookup"><span data-stu-id="530f4-105">Method</span></span>|<span data-ttu-id="530f4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="530f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="530f4-107">Método EnableNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="530f4-107">EnableNGenPolicy Method</span></span>](icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="530f4-108">Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="530f4-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="530f4-109">Método EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="530f4-109">EnumerateGCReferences Method</span></span>](icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="530f4-110">Obtiene un enumerador para todos los objetos que se van a recopilar de elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="530f4-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="530f4-111">Método EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="530f4-111">EnumerateHandles Method</span></span>](icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="530f4-112">Obtiene un enumerador para los identificadores de objetos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="530f4-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="530f4-113">Método EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="530f4-113">EnumerateHeap Method</span></span>](icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="530f4-114">Obtiene un enumerador para los objetos en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="530f4-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="530f4-115">Método EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="530f4-115">EnumerateHeapRegions Method</span></span>](icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="530f4-116">Obtiene un enumerador para las regiones del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="530f4-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="530f4-117">Método GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="530f4-117">GetArrayLayout Method</span></span>](icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="530f4-118">Obtiene información sobre el diseño de una matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="530f4-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="530f4-119">Método GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="530f4-119">GetGCHeapInformation Method</span></span>](icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="530f4-120">Obtiene un puntero a una estructura de [COR_HEAPINFO](cor-heapinfo-structure.md) que contiene información sobre los objetos que se van a recopilar en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="530f4-120">Gets a pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="530f4-121">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="530f4-121">GetObject Method</span></span>](icordebugprocess5-getobject-method.md)|<span data-ttu-id="530f4-122">Obtiene un puntero a un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="530f4-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="530f4-123">Método GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="530f4-123">GetTypeFields Method</span></span>](icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="530f4-124">Obtiene un puntero a una matriz que contiene información de campo para un tipo basado en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="530f4-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="530f4-125">Método GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="530f4-125">GetTypeForTypeID Method</span></span>](icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="530f4-126">Obtiene un objeto de tipo que proporciona información sobre un objeto basándose en sus identificadores de tipo.</span><span class="sxs-lookup"><span data-stu-id="530f4-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="530f4-127">Método GetTypeID</span><span class="sxs-lookup"><span data-stu-id="530f4-127">GetTypeID Method</span></span>](icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="530f4-128">Obtiene el identificador de tipo para el objeto en una dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="530f4-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="530f4-129">Método GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="530f4-129">GetTypeLayout Method</span></span>](icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="530f4-130">Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="530f4-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="530f4-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="530f4-131">Remarks</span></span>  

 <span data-ttu-id="530f4-132">Esta interfaz extiende lógicamente las interfaces ICorDebugProcess, ICorDebugProcess2 y [ICorDebugProcess3 (](icordebugprocess3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="530f4-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="530f4-133">Esta interfaz no admite la llamada remota, ya sea desde otro equipo o desde otro proceso.</span><span class="sxs-lookup"><span data-stu-id="530f4-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="530f4-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="530f4-134">Requirements</span></span>  

 <span data-ttu-id="530f4-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="530f4-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="530f4-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="530f4-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="530f4-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="530f4-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="530f4-138">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="530f4-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="530f4-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="530f4-139">See also</span></span>

- [<span data-ttu-id="530f4-140">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="530f4-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="530f4-141">Depuración</span><span class="sxs-lookup"><span data-stu-id="530f4-141">Debugging</span></span>](index.md)
