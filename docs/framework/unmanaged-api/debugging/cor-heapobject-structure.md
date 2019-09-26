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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c59ddec655f3127e8dab8d8c41543f03a896cf63
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274036"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="1f588-102">COR_HEAPOBJECT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="1f588-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="1f588-103">Proporciona información sobre un objeto del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="1f588-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f588-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f588-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="1f588-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1f588-105">Members</span></span>  
  
|<span data-ttu-id="1f588-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1f588-106">Member</span></span>|<span data-ttu-id="1f588-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f588-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="1f588-108">Dirección del objeto en memoria.</span><span class="sxs-lookup"><span data-stu-id="1f588-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="1f588-109">Tamaño total del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="1f588-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="1f588-110">Un token de [COR_TYPEID](cor-typeid-structure.md) que representa el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="1f588-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f588-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f588-111">Remarks</span></span>  
 <span data-ttu-id="1f588-112">`COR_HEAPOBJECT`las instancias pueden recuperarse mediante la enumeración de un objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) que se rellena llamando al método [ICorDebugProcess5:: enumerateheap (](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1f588-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="1f588-113">Una `COR_HEAPOBJECT` instancia de proporciona información sobre un objeto activo en el montón administrado o sobre un objeto que no está raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="1f588-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="1f588-114">Para mejorar el rendimiento, `COR_HEAPOBJECT.address` el campo es `CORDB_ADDRESS` un valor en lugar del valor de la interfaz ICorDebugValue usado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="1f588-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="1f588-115">Para obtener un objeto ICorDebugValue para una dirección de objeto determinada, puede pasar el `CORDB_ADDRESS` valor al método [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1f588-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="1f588-116">Para mejorar el rendimiento, `COR_HEAPOBJECT.type` el campo es `COR_TYPEID` un valor en lugar del valor de la interfaz ICorDebugType usado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="1f588-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="1f588-117">Para obtener un objeto ICorDebugType para un identificador de tipo determinado, puede pasar el `COR_TYPEID` valor al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1f588-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="1f588-118">La `COR_HEAPOBJECT` estructura incluye una interfaz com con recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="1f588-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="1f588-119">Si recupera una `COR_HEAPOBJECT` instancia del enumerador mediante una llamada al método [icordebugheapenum (:: Next](icordebugheapenum-next-method.md) , debe liberar posteriormente la referencia.</span><span class="sxs-lookup"><span data-stu-id="1f588-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f588-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f588-120">Requirements</span></span>  
 <span data-ttu-id="1f588-121">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f588-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f588-122">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="1f588-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f588-123">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f588-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f588-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f588-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f588-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f588-125">See also</span></span>

- [<span data-ttu-id="1f588-126">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="1f588-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="1f588-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="1f588-127">Debugging</span></span>](index.md)
