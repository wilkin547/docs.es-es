---
title: 'ICorDebugVirtualUnwinder:: Next (método)'
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a3d4bac42731bc94ecef7a0756392c8c0882fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967931"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="08e07-102">ICorDebugVirtualUnwinder:: Next (método)</span><span class="sxs-lookup"><span data-stu-id="08e07-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="08e07-103">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="08e07-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08e07-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08e07-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="08e07-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08e07-105">Parameters</span></span>  
 <span data-ttu-id="08e07-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="08e07-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08e07-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="08e07-107">Return Value</span></span>  
 <span data-ttu-id="08e07-108">`S_OK` Si el desenredado se realizó correctamente o `CORDBG_S_AT_END_OF_STACK` si el desenredado no se puede completar porque no hay más marcos.</span><span class="sxs-lookup"><span data-stu-id="08e07-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="08e07-109">Si se devuelve un error HRESULT, las API ICorDebug devolverán `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="08e07-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08e07-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="08e07-110">Remarks</span></span>  
 <span data-ttu-id="08e07-111">El rastreador de pila debe garantizar que permite avanzar, de manera que una posible llamada a `Next` devuelva un error HRESULT o `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="08e07-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="08e07-112">Devolver `S_OK` indefinidamente puede producir un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="08e07-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08e07-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="08e07-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08e07-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08e07-114">Requirements</span></span>  
 <span data-ttu-id="08e07-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08e07-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08e07-116">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="08e07-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08e07-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08e07-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08e07-118">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08e07-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e07-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="08e07-119">See also</span></span>

- [<span data-ttu-id="08e07-120">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08e07-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="08e07-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="08e07-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
