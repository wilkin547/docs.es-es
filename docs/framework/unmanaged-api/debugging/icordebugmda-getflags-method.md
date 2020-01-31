---
title: ICorDebugMDA::GetFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 0c7b8dae756fbb9ab27ff187eeb83a931b016b7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793287"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="52574-102">ICorDebugMDA::GetFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="52574-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="52574-103">Obtiene las marcas asociadas al Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="52574-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52574-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52574-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52574-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="52574-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="52574-106">de Combinación bit a bit de los valores de enumeración de [CorDebugMDAFlags (](cordebugmdaflags-enumeration.md) que especifican los valores de las marcas para este MDA.</span><span class="sxs-lookup"><span data-stu-id="52574-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52574-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="52574-107">Requirements</span></span>  
 <span data-ttu-id="52574-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52574-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52574-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52574-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52574-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52574-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52574-111">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52574-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52574-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="52574-112">See also</span></span>

- [<span data-ttu-id="52574-113">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52574-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="52574-114">Diagnóstico de errores con asistentes para la depuración administrada</span><span class="sxs-lookup"><span data-stu-id="52574-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
