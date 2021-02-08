---
description: 'Más información acerca de: estructura de COR_HEAPOBJECT'
title: COR_HEAPOBJECT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
ms.openlocfilehash: f41e02e7c528063f4b7ed485cbadbabb4d3e5ca7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801805"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="8c4ab-103">COR_HEAPOBJECT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8c4ab-103">COR_HEAPOBJECT Structure</span></span>

<span data-ttu-id="8c4ab-104">Proporciona información sobre un objeto del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-104">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c4ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c4ab-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="8c4ab-106">Members</span><span class="sxs-lookup"><span data-stu-id="8c4ab-106">Members</span></span>  
  
|<span data-ttu-id="8c4ab-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="8c4ab-107">Member</span></span>|<span data-ttu-id="8c4ab-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c4ab-108">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="8c4ab-109">Dirección del objeto en memoria.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-109">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="8c4ab-110">Tamaño total del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-110">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="8c4ab-111">[COR_TYPEID](cor-typeid-structure.md) token que representa el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-111">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c4ab-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8c4ab-112">Remarks</span></span>  

 <span data-ttu-id="8c4ab-113">`COR_HEAPOBJECT` las instancias pueden recuperarse mediante la enumeración de un objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) que se rellena llamando al método [ICorDebugProcess5:: enumerateheap (](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c4ab-113">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="8c4ab-114">Una `COR_HEAPOBJECT` instancia de proporciona información sobre un objeto activo en el montón administrado o sobre un objeto que no está raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-114">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="8c4ab-115">Para mejorar el rendimiento, el `COR_HEAPOBJECT.address` campo es un `CORDB_ADDRESS` valor en lugar del valor de la interfaz ICorDebugValue usado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-115">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="8c4ab-116">Para obtener un objeto ICorDebugValue para una dirección de objeto determinada, puede pasar el `CORDB_ADDRESS` valor al método [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c4ab-116">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="8c4ab-117">Para mejorar el rendimiento, el `COR_HEAPOBJECT.type` campo es un `COR_TYPEID` valor en lugar del valor de la interfaz ICorDebugType usado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-117">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="8c4ab-118">Para obtener un objeto ICorDebugType para un identificador de tipo determinado, puede pasar el `COR_TYPEID` valor al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c4ab-118">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="8c4ab-119">La `COR_HEAPOBJECT` estructura incluye una interfaz com con recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-119">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="8c4ab-120">Si recupera una `COR_HEAPOBJECT` instancia del enumerador mediante una llamada al método [icordebugheapenum (:: Next](icordebugheapenum-next-method.md) , debe liberar posteriormente la referencia.</span><span class="sxs-lookup"><span data-stu-id="8c4ab-120">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c4ab-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c4ab-121">Requirements</span></span>  

 <span data-ttu-id="8c4ab-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c4ab-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c4ab-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c4ab-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c4ab-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c4ab-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c4ab-125">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c4ab-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c4ab-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c4ab-126">See also</span></span>

- [<span data-ttu-id="8c4ab-127">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="8c4ab-127">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="8c4ab-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="8c4ab-128">Debugging</span></span>](index.md)
