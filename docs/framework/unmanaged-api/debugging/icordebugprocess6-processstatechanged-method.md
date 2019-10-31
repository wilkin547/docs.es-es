---
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 3927e57883ebe282b262cb03ececc3b2cd96fd46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123414"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="4dd51-102">Método ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="4dd51-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="4dd51-103">Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4dd51-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dd51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dd51-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dd51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4dd51-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="4dd51-106">de Un miembro de la enumeración [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="4dd51-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dd51-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4dd51-107">Remarks</span></span>  
 <span data-ttu-id="4dd51-108">El depurador llama a este método para notificar a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que el proceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4dd51-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4dd51-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4dd51-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dd51-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dd51-110">Requirements</span></span>  
 <span data-ttu-id="4dd51-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dd51-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dd51-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dd51-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dd51-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dd51-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dd51-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dd51-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd51-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dd51-115">See also</span></span>

- [<span data-ttu-id="4dd51-116">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4dd51-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="4dd51-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4dd51-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
