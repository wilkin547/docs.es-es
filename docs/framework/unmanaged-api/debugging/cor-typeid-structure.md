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
ms.openlocfilehash: 5eeb5aef7edaa23385190a309144e1477da741e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697446"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="a9034-102">COR_TYPEID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a9034-102">COR_TYPEID Structure</span></span>

<span data-ttu-id="a9034-103">Contiene un identificador de tipos.</span><span class="sxs-lookup"><span data-stu-id="a9034-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9034-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9034-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="a9034-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a9034-105">Members</span></span>  
  
|<span data-ttu-id="a9034-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a9034-106">Member</span></span>|<span data-ttu-id="a9034-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9034-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="a9034-108">El primer token.</span><span class="sxs-lookup"><span data-stu-id="a9034-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="a9034-109">Segundo token.</span><span class="sxs-lookup"><span data-stu-id="a9034-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9034-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9034-110">Remarks</span></span>  

 <span data-ttu-id="a9034-111">La `COR_TYPEID` estructura es devuelta por una serie de métodos de depuración que proporcionan información sobre los objetos que se van a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="a9034-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="a9034-112">A continuación, se puede pasar como argumento a otros métodos de depuración que proporcionan información adicional sobre ese elemento.</span><span class="sxs-lookup"><span data-stu-id="a9034-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="a9034-113">Por ejemplo, al enumerar un objeto [icordebugheapenum (](icordebugheapenum-interface.md) , puede recuperar objetos individuales [COR_HEAPOBJECT](cor-heapobject-structure.md) que representan objetos individuales en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="a9034-113">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="a9034-114">Después, puede pasar el `COR_TYPEID` valor del `COR_HEAPOBJECT.type` campo al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) para recuperar un objeto ICorDebugType que proporcione información de tipo sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="a9034-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="a9034-115">Un `COR_TYPEID` objeto está diseñado para ser opaco.</span><span class="sxs-lookup"><span data-stu-id="a9034-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="a9034-116">No se debe tener acceso a sus campos individuales ni manipularlos.</span><span class="sxs-lookup"><span data-stu-id="a9034-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="a9034-117">Su único uso es como un identificador que se proporciona como un `out` parámetro en una llamada al método y que, a su vez, se puede pasar a otros métodos para proporcionar información adicional.</span><span class="sxs-lookup"><span data-stu-id="a9034-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9034-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9034-118">Requirements</span></span>  

 <span data-ttu-id="a9034-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9034-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9034-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9034-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9034-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9034-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9034-122">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9034-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9034-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9034-123">See also</span></span>

- [<span data-ttu-id="a9034-124">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="a9034-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="a9034-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="a9034-125">Debugging</span></span>](index.md)
