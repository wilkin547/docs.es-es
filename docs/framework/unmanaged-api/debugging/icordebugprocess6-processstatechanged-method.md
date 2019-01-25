---
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb134b7d188c2fb966b53e4520a7fb825f11e428
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612052"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="a8da8-102">Método ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="a8da8-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="a8da8-103">Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="a8da8-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8da8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8da8-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8da8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8da8-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="a8da8-106">[in] Un miembro de la [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) (enumeración)</span><span class="sxs-lookup"><span data-stu-id="a8da8-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8da8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8da8-107">Remarks</span></span>  
 <span data-ttu-id="a8da8-108">El depurador llama a este método para notificar a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="a8da8-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8da8-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a8da8-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8da8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8da8-110">Requirements</span></span>  
 <span data-ttu-id="a8da8-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8da8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8da8-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8da8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8da8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8da8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8da8-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8da8-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8da8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8da8-115">See also</span></span>
- [<span data-ttu-id="a8da8-116">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8da8-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="a8da8-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a8da8-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
