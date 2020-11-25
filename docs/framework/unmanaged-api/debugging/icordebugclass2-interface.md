---
title: Interfaz ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: ce3f289ae914817071fad5274c45d1e5fae71a06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717986"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="2904e-102">Interfaz ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="2904e-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="2904e-103">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="2904e-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="2904e-104">Esta interfaz extiende [ICorDebugClass](icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2904e-104">This interface extends [ICorDebugClass](icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2904e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2904e-105">Methods</span></span>  
  
|<span data-ttu-id="2904e-106">Método</span><span class="sxs-lookup"><span data-stu-id="2904e-106">Method</span></span>|<span data-ttu-id="2904e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2904e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2904e-108">Método GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="2904e-108">GetParameterizedType Method</span></span>](icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="2904e-109">Obtiene la declaración de tipos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="2904e-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="2904e-110">SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="2904e-110">SetJMCStatus Method</span></span>](icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="2904e-111">Para cada método de esta clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="2904e-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2904e-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2904e-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2904e-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2904e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2904e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2904e-114">Requirements</span></span>  

 <span data-ttu-id="2904e-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2904e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2904e-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2904e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2904e-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2904e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2904e-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2904e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2904e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2904e-119">See also</span></span>

- [<span data-ttu-id="2904e-120">Interfaz ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="2904e-120">ICorDebugClass Interface</span></span>](icordebugclass-interface.md)
- [<span data-ttu-id="2904e-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2904e-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
