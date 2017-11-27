---
title: COR_TYPEID (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPEID
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPEID
helpviewer_keywords: COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 795dea77ac8dac1e1d22574c23f1e1c13344a71a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cortypeid-structure"></a><span data-ttu-id="35d5a-102">COR_TYPEID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="35d5a-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="35d5a-103">Contiene un identificador de tipos.</span><span class="sxs-lookup"><span data-stu-id="35d5a-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35d5a-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="35d5a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="35d5a-105">Members</span></span>  
  
|<span data-ttu-id="35d5a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="35d5a-106">Member</span></span>|<span data-ttu-id="35d5a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="35d5a-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="35d5a-108">El primer token.</span><span class="sxs-lookup"><span data-stu-id="35d5a-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="35d5a-109">El segundo token.</span><span class="sxs-lookup"><span data-stu-id="35d5a-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35d5a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35d5a-110">Remarks</span></span>  
 <span data-ttu-id="35d5a-111">El `COR_TYPEID` estructura se devuelve un número de métodos de depuración que proporcionan información acerca de los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="35d5a-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="35d5a-112">A continuación, puede pasarse como argumento a otros métodos de depuración que proporcionan información adicional sobre dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="35d5a-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="35d5a-113">Por ejemplo, al enumerar un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto, puede recuperar individuales [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objetos que representan los objetos individuales en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="35d5a-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="35d5a-114">A continuación, puede pasar el `COR_TYPEID` valor de la `COR_HEAPOBJECT.type` campo el [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) método para recuperar un objeto ICorDebugType que proporciona información de tipo sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="35d5a-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="35d5a-115">Un `COR_TYPEID` objeto está pensado para ser opaco.</span><span class="sxs-lookup"><span data-stu-id="35d5a-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="35d5a-116">No se deben obtener acceso a o manipulan sus campos individuales.</span><span class="sxs-lookup"><span data-stu-id="35d5a-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="35d5a-117">Su uso único es como un identificador que se proporciona como un `out` parámetro en una llamada al método y que puede, a su vez, se pasa a otros métodos para proporcionar información adicional.</span><span class="sxs-lookup"><span data-stu-id="35d5a-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35d5a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35d5a-118">Requirements</span></span>  
 <span data-ttu-id="35d5a-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35d5a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d5a-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35d5a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35d5a-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35d5a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35d5a-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d5a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d5a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="35d5a-123">See Also</span></span>  
 [<span data-ttu-id="35d5a-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="35d5a-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="35d5a-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="35d5a-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
