---
title: "ICorDebugRegisterSet2::SetRegisters (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.SetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35535ab909a4f2f113058a922fe777eafa74755b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="d0724-102">ICorDebugRegisterSet2::SetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="d0724-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="d0724-103">`SetRegisters`no se implementa en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0724-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="d0724-104">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="d0724-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0724-105">Utilice las operaciones de nivel superiores como [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="d0724-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0724-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0724-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d0724-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0724-107">Requirements</span></span>  
 <span data-ttu-id="d0724-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0724-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0724-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0724-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0724-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0724-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0724-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0724-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0724-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0724-112">See Also</span></span>  
 [<span data-ttu-id="d0724-113">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0724-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="d0724-114">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0724-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
