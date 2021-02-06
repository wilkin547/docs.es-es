---
description: 'Más información acerca de: interfaz ICorDebugProcess5'
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
ms.openlocfilehash: 880c305c1d9786f87d9727836a973696aa686ecf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649772"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="7e228-103">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e228-103">ICorDebugProcess5 Interface</span></span>

<span data-ttu-id="7e228-104">Extiende la interfaz ICorDebugProcess para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la memoria caché de imágenes nativas local de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e228-104">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e228-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7e228-105">Methods</span></span>  
  
|<span data-ttu-id="7e228-106">Método</span><span class="sxs-lookup"><span data-stu-id="7e228-106">Method</span></span>|<span data-ttu-id="7e228-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e228-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e228-108">Método EnableNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="7e228-108">EnableNGenPolicy Method</span></span>](icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="7e228-109">Establece un valor que determina cómo una aplicación carga imágenes nativas mientras se ejecuta en un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="7e228-109">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="7e228-110">Método EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="7e228-110">EnumerateGCReferences Method</span></span>](icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="7e228-111">Obtiene un enumerador para todos los objetos que se van a recopilar de elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="7e228-111">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="7e228-112">Método EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="7e228-112">EnumerateHandles Method</span></span>](icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="7e228-113">Obtiene un enumerador para los identificadores de objetos de un proceso.</span><span class="sxs-lookup"><span data-stu-id="7e228-113">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="7e228-114">Método EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="7e228-114">EnumerateHeap Method</span></span>](icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="7e228-115">Obtiene un enumerador para los objetos en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="7e228-115">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="7e228-116">Método EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="7e228-116">EnumerateHeapRegions Method</span></span>](icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="7e228-117">Obtiene un enumerador para las regiones del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="7e228-117">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="7e228-118">Método GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="7e228-118">GetArrayLayout Method</span></span>](icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="7e228-119">Obtiene información sobre el diseño de una matriz en la memoria.</span><span class="sxs-lookup"><span data-stu-id="7e228-119">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="7e228-120">Método GetGCHeapInformation</span><span class="sxs-lookup"><span data-stu-id="7e228-120">GetGCHeapInformation Method</span></span>](icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="7e228-121">Obtiene un puntero a una estructura de [COR_HEAPINFO](cor-heapinfo-structure.md) que contiene información sobre los objetos que se van a recopilar en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="7e228-121">Gets a pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="7e228-122">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="7e228-122">GetObject Method</span></span>](icordebugprocess5-getobject-method.md)|<span data-ttu-id="7e228-123">Obtiene un puntero a un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="7e228-123">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="7e228-124">Método GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="7e228-124">GetTypeFields Method</span></span>](icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="7e228-125">Obtiene un puntero a una matriz que contiene información de campo para un tipo basado en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="7e228-125">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="7e228-126">Método GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="7e228-126">GetTypeForTypeID Method</span></span>](icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="7e228-127">Obtiene un objeto de tipo que proporciona información sobre un objeto basándose en sus identificadores de tipo.</span><span class="sxs-lookup"><span data-stu-id="7e228-127">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="7e228-128">Método GetTypeID</span><span class="sxs-lookup"><span data-stu-id="7e228-128">GetTypeID Method</span></span>](icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="7e228-129">Obtiene el identificador de tipo para el objeto en una dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="7e228-129">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="7e228-130">Método GetTypeLayout</span><span class="sxs-lookup"><span data-stu-id="7e228-130">GetTypeLayout Method</span></span>](icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="7e228-131">Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="7e228-131">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e228-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7e228-132">Remarks</span></span>  

 <span data-ttu-id="7e228-133">Esta interfaz extiende lógicamente las interfaces ICorDebugProcess, ICorDebugProcess2 y [ICorDebugProcess3 (](icordebugprocess3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7e228-133">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e228-134">Esta interfaz no admite la llamada remota, ya sea desde otro equipo o desde otro proceso.</span><span class="sxs-lookup"><span data-stu-id="7e228-134">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e228-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e228-135">Requirements</span></span>  

 <span data-ttu-id="7e228-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e228-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e228-137">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e228-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e228-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e228-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e228-139">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e228-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e228-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e228-140">See also</span></span>

- [<span data-ttu-id="7e228-141">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7e228-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7e228-142">Depuración</span><span class="sxs-lookup"><span data-stu-id="7e228-142">Debugging</span></span>](index.md)
