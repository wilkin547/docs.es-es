---
title: ICorDebugProcess5::EnumerateGCReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 0f2f5acfc6a23398b15af3a63345050eb0dfd5b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687195"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="714c9-102">ICorDebugProcess5::EnumerateGCReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="714c9-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>

<span data-ttu-id="714c9-103">Obtiene un enumerador para todos los objetos que se van a recopilar de elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="714c9-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="714c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="714c9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="714c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="714c9-105">Parameters</span></span>  

 `enumerateWeakReferences`  
 <span data-ttu-id="714c9-106">de Valor booleano que indica si también se deben enumerar las referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="714c9-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="714c9-107">Si `enumerateWeakReferences` es `true` , el `ppEnum` enumerador incluye las referencias fuertes y las referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="714c9-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="714c9-108">Si `enumerateWeakReferences` es `false` , el enumerador incluye solo referencias seguras.</span><span class="sxs-lookup"><span data-stu-id="714c9-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="714c9-109">enuncia Puntero a la dirección de un [icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="714c9-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="714c9-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="714c9-110">Remarks</span></span>  

 <span data-ttu-id="714c9-111">Este método proporciona una manera de determinar la cadena de raíz completa de cualquier objeto administrado en un proceso y se puede usar para determinar por qué un objeto sigue estando activo.</span><span class="sxs-lookup"><span data-stu-id="714c9-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="714c9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="714c9-112">Requirements</span></span>  

 <span data-ttu-id="714c9-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="714c9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="714c9-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="714c9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="714c9-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="714c9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="714c9-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="714c9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714c9-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="714c9-117">See also</span></span>

- [<span data-ttu-id="714c9-118">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="714c9-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="714c9-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="714c9-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
