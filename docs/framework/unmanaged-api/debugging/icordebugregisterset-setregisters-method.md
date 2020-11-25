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
ms.openlocfilehash: 4be5d2d9d891010e68cd6eb96cd4456e04d8c8b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712292"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="e3ed9-102">ICorDebugRegisterSet::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="e3ed9-102">ICorDebugRegisterSet::SetRegisters Method</span></span>

<span data-ttu-id="e3ed9-103">`SetRegisters` no se implementa en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e3ed9-104">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="e3ed9-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3ed9-105">Use las operaciones de nivel superior como [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="e3ed9-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ed9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3ed9-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e3ed9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3ed9-107">Requirements</span></span>  

 <span data-ttu-id="e3ed9-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3ed9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3ed9-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3ed9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3ed9-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3ed9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3ed9-111">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="e3ed9-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ed9-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3ed9-112">See also</span></span>

- [<span data-ttu-id="e3ed9-113">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3ed9-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="e3ed9-114">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3ed9-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
