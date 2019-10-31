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
ms.openlocfilehash: 270360a8950197eca14e02a60554659e5ac7b91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099076"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="35d45-102">COR_HEAPOBJECT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="35d45-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="35d45-103">Proporciona información sobre un objeto del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="35d45-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35d45-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="35d45-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="35d45-105">Members</span></span>  
  
|<span data-ttu-id="35d45-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="35d45-106">Member</span></span>|<span data-ttu-id="35d45-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="35d45-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="35d45-108">Dirección del objeto en memoria.</span><span class="sxs-lookup"><span data-stu-id="35d45-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="35d45-109">Tamaño total del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="35d45-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="35d45-110">Un token de [COR_TYPEID](cor-typeid-structure.md) que representa el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="35d45-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35d45-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35d45-111">Remarks</span></span>  
 <span data-ttu-id="35d45-112">`COR_HEAPOBJECT` instancias se pueden recuperar enumerando un objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) que se rellena llamando al método [ICorDebugProcess5:: enumerateheap (](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35d45-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="35d45-113">Una instancia de `COR_HEAPOBJECT` proporciona información sobre un objeto activo en el montón administrado o sobre un objeto que no está raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="35d45-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="35d45-114">Para mejorar el rendimiento, el campo `COR_HEAPOBJECT.address` es un valor `CORDB_ADDRESS` en lugar del valor de la interfaz ICorDebugValue usado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="35d45-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="35d45-115">Para obtener un objeto ICorDebugValue para una dirección de objeto determinada, puede pasar el valor `CORDB_ADDRESS` al método [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35d45-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="35d45-116">Para mejorar el rendimiento, el campo `COR_HEAPOBJECT.type` es un valor `COR_TYPEID` en lugar del valor de la interfaz ICorDebugType usado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="35d45-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="35d45-117">Para obtener un objeto ICorDebugType para un identificador de tipo determinado, puede pasar el valor de `COR_TYPEID` al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35d45-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="35d45-118">La estructura de `COR_HEAPOBJECT` incluye una interfaz COM con recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="35d45-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="35d45-119">Si recupera una instancia de `COR_HEAPOBJECT` del enumerador mediante una llamada al método [icordebugheapenum (:: Next](icordebugheapenum-next-method.md) , debe liberar la referencia posteriormente.</span><span class="sxs-lookup"><span data-stu-id="35d45-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35d45-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35d45-120">Requirements</span></span>  
 <span data-ttu-id="35d45-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35d45-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d45-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35d45-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35d45-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35d45-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35d45-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d45-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d45-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="35d45-125">See also</span></span>

- [<span data-ttu-id="35d45-126">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="35d45-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="35d45-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="35d45-127">Debugging</span></span>](index.md)
