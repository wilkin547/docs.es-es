---
title: ICorDebugNativeFrame::GetRegisterSet (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: 945a398d32b50efc81ba45e705ed9d4161ed1524
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709276"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="6d713-102">ICorDebugNativeFrame::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="6d713-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>

<span data-ttu-id="6d713-103">Obtiene el conjunto de registros para este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="6d713-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d713-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d713-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d713-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d713-105">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="6d713-106">enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="6d713-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d713-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d713-107">Requirements</span></span>  

 <span data-ttu-id="6d713-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d713-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d713-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d713-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d713-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d713-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d713-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d713-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d713-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d713-112">See also</span></span>
