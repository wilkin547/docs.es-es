---
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5861762242412d7ab6f0c02f2b8f5c149f9453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420184"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="d6b05-102">Método ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="d6b05-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="d6b05-103">Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="d6b05-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6b05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6b05-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6b05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6b05-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="d6b05-106">[in] Un miembro de la [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) (enumeración)</span><span class="sxs-lookup"><span data-stu-id="d6b05-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6b05-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6b05-107">Remarks</span></span>  
 <span data-ttu-id="d6b05-108">El depurador llama a este método para notificar a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="d6b05-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6b05-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d6b05-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6b05-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6b05-110">Requirements</span></span>  
 <span data-ttu-id="d6b05-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6b05-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6b05-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6b05-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6b05-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6b05-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6b05-114">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6b05-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b05-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6b05-115">See Also</span></span>  
 [<span data-ttu-id="d6b05-116">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6b05-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="d6b05-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d6b05-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
