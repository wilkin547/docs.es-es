---
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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179335"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="45a46-102">COR_HEAPOBJECT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="45a46-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="45a46-103">Proporciona información sobre un objeto del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="45a46-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a46-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45a46-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="45a46-105">Members</span><span class="sxs-lookup"><span data-stu-id="45a46-105">Members</span></span>  
  
|<span data-ttu-id="45a46-106">Member</span><span class="sxs-lookup"><span data-stu-id="45a46-106">Member</span></span>|<span data-ttu-id="45a46-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="45a46-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="45a46-108">La dirección del objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="45a46-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="45a46-109">El tamaño total del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="45a46-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="45a46-110">Un [token de COR_TYPEID](cor-typeid-structure.md) que representa el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="45a46-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45a46-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="45a46-111">Remarks</span></span>  
 <span data-ttu-id="45a46-112">`COR_HEAPOBJECT`Instancias se pueden recuperar mediante la enumeración de un [ICorDebugHeapEnum](icordebugheapenum-interface.md) objeto de interfaz que se rellena mediante una llamada a la [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="45a46-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="45a46-113">Una `COR_HEAPOBJECT` instancia proporciona información sobre un objeto activo en el montón administrado o sobre un objeto que no está rooteado por ningún objeto pero que aún no ha sido recopilado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="45a46-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="45a46-114">Para un mejor `COR_HEAPOBJECT.address` rendimiento, `CORDB_ADDRESS` el campo es un valor en lugar del valor de la interfaz ICorDebugValue utilizado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="45a46-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="45a46-115">Para obtener un ICorDebugValue objeto para una dirección `CORDB_ADDRESS` de objeto determinada, puede pasar el valor a la [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="45a46-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="45a46-116">Para un mejor `COR_HEAPOBJECT.type` rendimiento, `COR_TYPEID` el campo es un valor en lugar del valor de la interfaz ICorDebugType utilizado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="45a46-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="45a46-117">Para obtener un ICorDebugType objeto para un identificador `COR_TYPEID` de tipo determinado, puede pasar el valor a la [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="45a46-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="45a46-118">La `COR_HEAPOBJECT` estructura incluye una interfaz COM con recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="45a46-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="45a46-119">Si recupera `COR_HEAPOBJECT` una instancia del enumerador mediante una llamada a la [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) método, debe liberar posteriormente la referencia.</span><span class="sxs-lookup"><span data-stu-id="45a46-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a46-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45a46-120">Requirements</span></span>  
 <span data-ttu-id="45a46-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45a46-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a46-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45a46-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45a46-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45a46-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45a46-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45a46-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a46-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45a46-125">See also</span></span>

- [<span data-ttu-id="45a46-126">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="45a46-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="45a46-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="45a46-127">Debugging</span></span>](index.md)
