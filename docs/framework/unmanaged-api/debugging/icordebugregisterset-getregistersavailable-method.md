---
title: ICorDebugRegisterSet::GetRegistersAvailable (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d600b4687b86f5872f94a60ad3422be764cf5307
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747210"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="ba4a3-102">ICorDebugRegisterSet::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="ba4a3-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="ba4a3-103">Obtiene un poco de máscara que indica que se registra en este [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="ba4a3-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba4a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba4a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba4a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba4a3-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="ba4a3-106">[out] Una máscara de bits que indica qué registros están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="ba4a3-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba4a3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba4a3-107">Remarks</span></span>  
 <span data-ttu-id="ba4a3-108">Un registro no esté disponible si no se puede determinar su valor para la situación determinada.</span><span class="sxs-lookup"><span data-stu-id="ba4a3-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="ba4a3-109">La máscara devuelta contiene un bit por cada registro (1 << el índice del registro).</span><span class="sxs-lookup"><span data-stu-id="ba4a3-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="ba4a3-110">El valor de bit es 1 si el registro está disponible, o 0 si no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ba4a3-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba4a3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba4a3-111">Requirements</span></span>  
 <span data-ttu-id="ba4a3-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba4a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba4a3-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba4a3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba4a3-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba4a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba4a3-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba4a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4a3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba4a3-116">See also</span></span>

- [<span data-ttu-id="ba4a3-117">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba4a3-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="ba4a3-118">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba4a3-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
