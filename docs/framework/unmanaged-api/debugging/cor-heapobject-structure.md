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
ms.openlocfilehash: 91e64bb2e1c8a7b11fe70024eb4a4fa1717c06e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407354"
---
# <a name="corheapobject-structure"></a><span data-ttu-id="ceca0-102">COR_HEAPOBJECT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ceca0-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="ceca0-103">Proporciona información sobre un objeto del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="ceca0-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceca0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ceca0-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="ceca0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ceca0-105">Members</span></span>  
  
|<span data-ttu-id="ceca0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ceca0-106">Member</span></span>|<span data-ttu-id="ceca0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ceca0-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="ceca0-108">La dirección del objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="ceca0-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="ceca0-109">El tamaño total del objeto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ceca0-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="ceca0-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) símbolo (token) que representa el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="ceca0-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceca0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ceca0-111">Remarks</span></span>  
 <span data-ttu-id="ceca0-112">`COR_HEAPOBJECT` instancias se pueden recuperar mediante la enumeración de un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto de interfaz que se rellena mediante una llamada a la [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ceca0-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="ceca0-113">Un `COR_HEAPOBJECT` instancia proporciona información acerca de un objeto activo en el montón administrado, o sobre un objeto que no se ha modificado cualquier objeto, pero aún no se ha recolectado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ceca0-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="ceca0-114">Para mejorar el rendimiento, la `COR_HEAPOBJECT.address` campo es un `CORDB_ADDRESS` valor en lugar de ICorDebugValue interfaz valor usado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="ceca0-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="ceca0-115">Para obtener un objeto ICorDebugValue para una dirección de objeto determinado, puede pasar el `CORDB_ADDRESS` valor para el [icordebugprocess5:: GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ceca0-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="ceca0-116">Para mejorar el rendimiento, la `COR_HEAPOBJECT.type` campo es un `COR_TYPEID` valor en lugar de la ICorDebugType interfaz valor usado en gran parte de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="ceca0-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="ceca0-117">Para obtener un objeto ICorDebugType para un identificador de tipo determinado, puede pasar el `COR_TYPEID` valor para el [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ceca0-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="ceca0-118">El `COR_HEAPOBJECT` estructura incluye una interfaz de COM con recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="ceca0-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="ceca0-119">Si recupera un `COR_HEAPOBJECT` instancia desde el enumerador mediante una llamada a la [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) método posteriormente debe liberar la referencia.</span><span class="sxs-lookup"><span data-stu-id="ceca0-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceca0-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ceca0-120">Requirements</span></span>  
 <span data-ttu-id="ceca0-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceca0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceca0-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ceca0-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ceca0-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceca0-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceca0-124">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceca0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceca0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ceca0-125">See Also</span></span>  
 [<span data-ttu-id="ceca0-126">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="ceca0-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="ceca0-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="ceca0-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
