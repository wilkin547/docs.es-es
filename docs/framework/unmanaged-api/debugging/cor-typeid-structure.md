---
description: 'Más información acerca de: estructura de COR_TYPEID'
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
ms.openlocfilehash: fe246d544697275ffc4ea3ab6ed21c0f33863881
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712219"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="eafd8-103">COR_TYPEID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="eafd8-103">COR_TYPEID Structure</span></span>

<span data-ttu-id="eafd8-104">Contiene un identificador de tipos.</span><span class="sxs-lookup"><span data-stu-id="eafd8-104">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eafd8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eafd8-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="eafd8-106">Members</span><span class="sxs-lookup"><span data-stu-id="eafd8-106">Members</span></span>  
  
|<span data-ttu-id="eafd8-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="eafd8-107">Member</span></span>|<span data-ttu-id="eafd8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="eafd8-108">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="eafd8-109">El primer token.</span><span class="sxs-lookup"><span data-stu-id="eafd8-109">The first token.</span></span>|  
|`token2`|<span data-ttu-id="eafd8-110">Segundo token.</span><span class="sxs-lookup"><span data-stu-id="eafd8-110">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eafd8-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eafd8-111">Remarks</span></span>  

 <span data-ttu-id="eafd8-112">La `COR_TYPEID` estructura es devuelta por una serie de métodos de depuración que proporcionan información sobre los objetos que se van a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="eafd8-112">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="eafd8-113">A continuación, se puede pasar como argumento a otros métodos de depuración que proporcionan información adicional sobre ese elemento.</span><span class="sxs-lookup"><span data-stu-id="eafd8-113">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="eafd8-114">Por ejemplo, al enumerar un objeto [icordebugheapenum (](icordebugheapenum-interface.md) , puede recuperar objetos individuales [COR_HEAPOBJECT](cor-heapobject-structure.md) que representan objetos individuales en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="eafd8-114">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="eafd8-115">Después, puede pasar el `COR_TYPEID` valor del `COR_HEAPOBJECT.type` campo al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) para recuperar un objeto ICorDebugType que proporcione información de tipo sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="eafd8-115">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="eafd8-116">Un `COR_TYPEID` objeto está diseñado para ser opaco.</span><span class="sxs-lookup"><span data-stu-id="eafd8-116">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="eafd8-117">No se debe tener acceso a sus campos individuales ni manipularlos.</span><span class="sxs-lookup"><span data-stu-id="eafd8-117">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="eafd8-118">Su único uso es como un identificador que se proporciona como un `out` parámetro en una llamada al método y que, a su vez, se puede pasar a otros métodos para proporcionar información adicional.</span><span class="sxs-lookup"><span data-stu-id="eafd8-118">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eafd8-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eafd8-119">Requirements</span></span>  

 <span data-ttu-id="eafd8-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eafd8-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eafd8-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eafd8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eafd8-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eafd8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eafd8-123">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eafd8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafd8-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="eafd8-124">See also</span></span>

- [<span data-ttu-id="eafd8-125">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="eafd8-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="eafd8-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="eafd8-126">Debugging</span></span>](index.md)
