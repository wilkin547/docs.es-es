---
title: ICorDebugFunction2 (Interfaz1)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 190e2323fb07dbca6e156d7a24397997e54b6da9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540798"
---
# <a name="icordebugfunction2-interface1"></a><span data-ttu-id="fb740-102">ICorDebugFunction2 (Interfaz1)</span><span class="sxs-lookup"><span data-stu-id="fb740-102">ICorDebugFunction2 Interface1</span></span>
<span data-ttu-id="fb740-103">Lógicamente, extiende la interfaz de ICorDebugFunction para proporcionar compatibilidad para la depuración solo mi código paso a paso, que omite el código de no usuario.</span><span class="sxs-lookup"><span data-stu-id="fb740-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb740-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fb740-104">Methods</span></span>  
  
|<span data-ttu-id="fb740-105">Método</span><span class="sxs-lookup"><span data-stu-id="fb740-105">Method</span></span>|<span data-ttu-id="fb740-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb740-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb740-107">EnumerateNativeCode (método)</span><span class="sxs-lookup"><span data-stu-id="fb740-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="fb740-108">(Aún no implementado). Obtiene un puntero de interfaz a un ICorDebugCodeEnum que contiene las instrucciones de código nativo en la función al que hace referencia este objeto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="fb740-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="fb740-109">GetJMCStatus (método)</span><span class="sxs-lookup"><span data-stu-id="fb740-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="fb740-110">Obtiene un valor que indica si esta función está marcada como código de usuario.</span><span class="sxs-lookup"><span data-stu-id="fb740-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="fb740-111">GetVersionNumber (método)</span><span class="sxs-lookup"><span data-stu-id="fb740-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="fb740-112">Obtiene la versión de editar y continuar de esta función.</span><span class="sxs-lookup"><span data-stu-id="fb740-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="fb740-113">SetJMCStatus (método)</span><span class="sxs-lookup"><span data-stu-id="fb740-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="fb740-114">Marca esta función solo mi código para la ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="fb740-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb740-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb740-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb740-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="fb740-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb740-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb740-117">Requirements</span></span>  
 <span data-ttu-id="fb740-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb740-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb740-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb740-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb740-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb740-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb740-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb740-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb740-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb740-122">See also</span></span>
- [<span data-ttu-id="fb740-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fb740-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
