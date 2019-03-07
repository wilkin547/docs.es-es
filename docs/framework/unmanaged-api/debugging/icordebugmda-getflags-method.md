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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48a08261d3ed17fbbb1a040f356ed341ca863a53
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468941"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="9a107-102">ICorDebugMDA::GetFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="9a107-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="9a107-103">Obtiene los marcadores asociados con el Asistente para depuración administrada (MDA) representado por [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9a107-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a107-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a107-104">Syntax</span></span>  
  
```  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a107-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a107-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="9a107-106">[in] Una combinación bit a bit de los [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) valores de enumeración que especifican los valores de las marcas para este MDA.</span><span class="sxs-lookup"><span data-stu-id="9a107-106">[in] A bitwise combination of the [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a107-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a107-107">Requirements</span></span>  
 <span data-ttu-id="9a107-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a107-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a107-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a107-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a107-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a107-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a107-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a107-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a107-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a107-112">See also</span></span>
- [<span data-ttu-id="9a107-113">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a107-113">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="9a107-114">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="9a107-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
