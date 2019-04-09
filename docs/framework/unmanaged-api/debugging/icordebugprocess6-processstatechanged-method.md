---
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4dcee3b396d9533f3169db1ea54a6cdc6086c8c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166151"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="9c4e0-102">Método ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="9c4e0-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="9c4e0-103">Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="9c4e0-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c4e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c4e0-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c4e0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c4e0-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="9c4e0-106">[in] Un miembro de la [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) (enumeración)</span><span class="sxs-lookup"><span data-stu-id="9c4e0-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c4e0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c4e0-107">Remarks</span></span>  
 <span data-ttu-id="9c4e0-108">El depurador llama a este método para notificar a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que se está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="9c4e0-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c4e0-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9c4e0-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c4e0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c4e0-110">Requirements</span></span>  
 <span data-ttu-id="9c4e0-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c4e0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c4e0-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c4e0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c4e0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c4e0-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9c4e0-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9c4e0-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9c4e0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c4e0-115">See also</span></span>

- [<span data-ttu-id="9c4e0-116">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="9c4e0-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="9c4e0-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9c4e0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
