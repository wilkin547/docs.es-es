---
description: 'Más información acerca de: ICorDebugRegisterSet:: Getregistersavailable ((método)'
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
ms.openlocfilehash: a1727c594733fe6529fe1e78f341723623b68be2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690826"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="2170b-103">ICorDebugRegisterSet::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="2170b-103">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>

<span data-ttu-id="2170b-104">Obtiene una máscara de bits que indica qué registros de la [ICorDebugRegisterSet](icordebugregisterset-interface.md) están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="2170b-104">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2170b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2170b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2170b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2170b-106">Parameters</span></span>  

 `pAvailable`  
 <span data-ttu-id="2170b-107">enuncia Máscara de bits que indica qué registros están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="2170b-107">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2170b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2170b-108">Remarks</span></span>  

 <span data-ttu-id="2170b-109">Un registro puede no estar disponible si su valor no se puede determinar para la situación determinada.</span><span class="sxs-lookup"><span data-stu-id="2170b-109">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="2170b-110">La máscara devuelta contiene un bit por cada registro (1 << el índice de registro).</span><span class="sxs-lookup"><span data-stu-id="2170b-110">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="2170b-111">El valor de bit es 1 si el registro está disponible, o 0 si no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2170b-111">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2170b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2170b-112">Requirements</span></span>  

 <span data-ttu-id="2170b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2170b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2170b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2170b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2170b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2170b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2170b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2170b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2170b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2170b-117">See also</span></span>

- [<span data-ttu-id="2170b-118">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2170b-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="2170b-119">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2170b-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
