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
ms.openlocfilehash: d28c130e55cbebf29348752780c03b03c1b8f358
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716998"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="2a757-102">ICorDebugRegisterSet::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="2a757-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>

<span data-ttu-id="2a757-103">Obtiene una máscara de bits que indica qué registros de la [ICorDebugRegisterSet](icordebugregisterset-interface.md) están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="2a757-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a757-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a757-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a757-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a757-105">Parameters</span></span>  

 `pAvailable`  
 <span data-ttu-id="2a757-106">enuncia Máscara de bits que indica qué registros están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="2a757-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a757-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a757-107">Remarks</span></span>  

 <span data-ttu-id="2a757-108">Un registro puede no estar disponible si su valor no se puede determinar para la situación determinada.</span><span class="sxs-lookup"><span data-stu-id="2a757-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="2a757-109">La máscara devuelta contiene un bit por cada registro (1 << el índice de registro).</span><span class="sxs-lookup"><span data-stu-id="2a757-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="2a757-110">El valor de bit es 1 si el registro está disponible, o 0 si no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2a757-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a757-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a757-111">Requirements</span></span>  

 <span data-ttu-id="2a757-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a757-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a757-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a757-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a757-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a757-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a757-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a757-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a757-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a757-116">See also</span></span>

- [<span data-ttu-id="2a757-117">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a757-117">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="2a757-118">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a757-118">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
