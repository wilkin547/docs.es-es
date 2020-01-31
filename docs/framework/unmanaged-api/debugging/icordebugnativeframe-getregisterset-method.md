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
ms.openlocfilehash: affab7ae99dbdf85e7eadc89bfd24c42408626ac
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792820"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="9fad5-102">ICorDebugNativeFrame::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="9fad5-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="9fad5-103">Obtiene el conjunto de registros para este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="9fad5-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fad5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fad5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fad5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9fad5-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="9fad5-106">enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="9fad5-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fad5-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="9fad5-107">Requirements</span></span>  
 <span data-ttu-id="9fad5-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fad5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fad5-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fad5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fad5-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fad5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fad5-111">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fad5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fad5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fad5-112">See also</span></span>
