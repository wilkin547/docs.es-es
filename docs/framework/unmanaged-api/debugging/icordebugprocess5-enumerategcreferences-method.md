---
description: 'Más información sobre: ICorDebugProcess5:: Enumerategcreferences ((método)'
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
ms.openlocfilehash: 5145fd072b083ed107b874fe99403984915233ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746417"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="c5997-103">ICorDebugProcess5::EnumerateGCReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="c5997-103">ICorDebugProcess5::EnumerateGCReferences Method</span></span>

<span data-ttu-id="c5997-104">Obtiene un enumerador para todos los objetos que se van a recopilar de elementos no utilizados en un proceso.</span><span class="sxs-lookup"><span data-stu-id="c5997-104">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5997-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5997-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5997-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5997-106">Parameters</span></span>  

 `enumerateWeakReferences`  
 <span data-ttu-id="c5997-107">de Valor booleano que indica si también se deben enumerar las referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="c5997-107">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="c5997-108">Si `enumerateWeakReferences` es `true` , el `ppEnum` enumerador incluye las referencias fuertes y las referencias débiles.</span><span class="sxs-lookup"><span data-stu-id="c5997-108">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="c5997-109">Si `enumerateWeakReferences` es `false` , el enumerador incluye solo referencias seguras.</span><span class="sxs-lookup"><span data-stu-id="c5997-109">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="c5997-110">enuncia Puntero a la dirección de un [icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md) que es un enumerador para los objetos que se van a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="c5997-110">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5997-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c5997-111">Remarks</span></span>  

 <span data-ttu-id="c5997-112">Este método proporciona una manera de determinar la cadena de raíz completa de cualquier objeto administrado en un proceso y se puede usar para determinar por qué un objeto sigue estando activo.</span><span class="sxs-lookup"><span data-stu-id="c5997-112">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5997-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5997-113">Requirements</span></span>  

 <span data-ttu-id="c5997-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5997-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5997-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5997-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5997-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5997-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5997-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5997-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5997-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5997-118">See also</span></span>

- [<span data-ttu-id="c5997-119">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5997-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="c5997-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c5997-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
