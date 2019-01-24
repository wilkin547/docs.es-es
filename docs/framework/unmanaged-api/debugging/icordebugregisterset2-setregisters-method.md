---
title: ICorDebugRegisterSet2::SetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f7ba8228ae47508e3aa3ac79cf635fcf4eba329
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604436"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="4da78-102">ICorDebugRegisterSet2::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="4da78-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="4da78-103">`SetRegisters` no se implementa en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4da78-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4da78-104">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="4da78-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4da78-105">Use las operaciones de nivel superior como [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o [ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="4da78-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da78-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4da78-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4da78-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4da78-107">Requirements</span></span>  
 <span data-ttu-id="4da78-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4da78-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4da78-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4da78-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4da78-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4da78-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4da78-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4da78-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da78-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4da78-112">See also</span></span>
- [<span data-ttu-id="4da78-113">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4da78-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="4da78-114">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4da78-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
