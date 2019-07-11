---
title: COR_TYPEID (Estructura)
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 426420175a7d05f39859b9e217a888a8c01b6d63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740505"
---
# <a name="cortypeid-structure"></a><span data-ttu-id="50a61-102">COR_TYPEID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="50a61-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="50a61-103">Contiene un identificador de tipos.</span><span class="sxs-lookup"><span data-stu-id="50a61-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50a61-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="50a61-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="50a61-105">Members</span></span>  
  
|<span data-ttu-id="50a61-106">Member</span><span class="sxs-lookup"><span data-stu-id="50a61-106">Member</span></span>|<span data-ttu-id="50a61-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="50a61-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="50a61-108">El primer token.</span><span class="sxs-lookup"><span data-stu-id="50a61-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="50a61-109">El segundo token.</span><span class="sxs-lookup"><span data-stu-id="50a61-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50a61-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50a61-110">Remarks</span></span>  
 <span data-ttu-id="50a61-111">El `COR_TYPEID` estructura devuelto por una serie de métodos de depuración que proporcionan información acerca de los objetos para recopilar los elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="50a61-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="50a61-112">A continuación, puede pasarse como argumento a otros métodos de depuración que proporcionen información adicional sobre dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="50a61-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="50a61-113">Por ejemplo, al enumerar un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto, puede recuperar individuales [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objetos que representan objetos individuales en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="50a61-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="50a61-114">A continuación, puede pasar el `COR_TYPEID` valor desde el `COR_HEAPOBJECT.type` campo el [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) método para recuperar un objeto ICorDebugType que proporciona información sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="50a61-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="50a61-115">Un `COR_TYPEID` objeto está pensado para ser opaca.</span><span class="sxs-lookup"><span data-stu-id="50a61-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="50a61-116">No se deben tener acceso a sus campos individuales ni manipular.</span><span class="sxs-lookup"><span data-stu-id="50a61-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="50a61-117">Es su uso exclusivo como un identificador que se proporciona como un `out` parámetro en una llamada al método y que puede, a su vez, se pasa a otros métodos para proporcionar información adicional.</span><span class="sxs-lookup"><span data-stu-id="50a61-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a61-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50a61-118">Requirements</span></span>  
 <span data-ttu-id="50a61-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50a61-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50a61-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50a61-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50a61-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50a61-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50a61-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50a61-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a61-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="50a61-123">See also</span></span>

- [<span data-ttu-id="50a61-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="50a61-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="50a61-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="50a61-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
