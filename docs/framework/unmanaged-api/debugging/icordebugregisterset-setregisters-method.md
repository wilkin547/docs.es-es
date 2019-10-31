---
title: ICorDebugRegisterSet::SetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
ms.openlocfilehash: 7af3109c822dfe945a60c16d4bd3b764f7550492
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131342"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="ba137-102">ICorDebugRegisterSet::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="ba137-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="ba137-103">`SetRegisters` no se implementa en la versión 2,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ba137-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ba137-104">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="ba137-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba137-105">Use las operaciones de nivel superior como [ICorDebugILFrame:: setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="ba137-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba137-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba137-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ba137-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba137-107">Requirements</span></span>  
 <span data-ttu-id="ba137-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba137-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba137-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba137-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba137-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba137-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba137-111">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="ba137-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba137-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba137-112">See also</span></span>

- [<span data-ttu-id="ba137-113">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba137-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="ba137-114">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba137-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
