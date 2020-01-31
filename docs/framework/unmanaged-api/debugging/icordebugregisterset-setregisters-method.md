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
ms.openlocfilehash: d61d37448930d451b519c93909165e5e16f92765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792049"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="5443b-102">ICorDebugRegisterSet::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="5443b-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="5443b-103">`SetRegisters` no se implementa en la versión 2,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5443b-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="5443b-104">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="5443b-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5443b-105">Use las operaciones de nivel superior como [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="5443b-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5443b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5443b-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5443b-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5443b-107">Requirements</span></span>  
 <span data-ttu-id="5443b-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5443b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5443b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5443b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5443b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5443b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5443b-111">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="5443b-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5443b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5443b-112">See also</span></span>

- [<span data-ttu-id="5443b-113">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5443b-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="5443b-114">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5443b-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
