---
description: 'Más información acerca de: ICorDebugFunction2 (interfaz)'
title: Interfaz ICorDebugFunction2
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: e5297d46acb9b174537363fc185fa2d540d55a75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692204"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="5448b-103">Interfaz ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="5448b-103">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="5448b-104">Extiende lógicamente la interfaz ICorDebugFunction para proporcionar compatibilidad con Solo mi código depuración paso a paso, que omite el código que no es de usuario.</span><span class="sxs-lookup"><span data-stu-id="5448b-104">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5448b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5448b-105">Methods</span></span>  
  
|<span data-ttu-id="5448b-106">Método</span><span class="sxs-lookup"><span data-stu-id="5448b-106">Method</span></span>|<span data-ttu-id="5448b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5448b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5448b-108">Método EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="5448b-108">EnumerateNativeCode Method</span></span>](icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="5448b-109">(Aún no implementado). Obtiene un puntero de interfaz a un ICorDebugCodeEnum (que contiene las instrucciones de código nativo en la función a la que hace referencia este objeto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="5448b-109">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="5448b-110">Método GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="5448b-110">GetJMCStatus Method</span></span>](icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="5448b-111">Obtiene un valor que indica si esta función está marcada como código de usuario.</span><span class="sxs-lookup"><span data-stu-id="5448b-111">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="5448b-112">GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="5448b-112">GetVersionNumber Method</span></span>](icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="5448b-113">Obtiene la versión de edición y continuación de esta función.</span><span class="sxs-lookup"><span data-stu-id="5448b-113">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="5448b-114">SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="5448b-114">SetJMCStatus Method</span></span>](icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="5448b-115">Marca esta función para Solo mi código la ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="5448b-115">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5448b-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5448b-116">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5448b-117">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5448b-117">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5448b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5448b-118">Requirements</span></span>  

 <span data-ttu-id="5448b-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5448b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5448b-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5448b-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5448b-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5448b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5448b-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5448b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5448b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5448b-123">See also</span></span>

- [<span data-ttu-id="5448b-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5448b-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
